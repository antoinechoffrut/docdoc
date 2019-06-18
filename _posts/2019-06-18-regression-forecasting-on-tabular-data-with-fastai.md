---
layout: post
title:  "Regression/forecasting on tabular data with fastai"
date:   2019-06-18 10:48:00 +0100
categories: fastai
---

This post shows a workflow to do forecasting with regression using the
[`fastai`][fastai-docs] library.  I did not find this process
straightforward and neither did other users, so this post should
hopefully be of some use to others.  

_Note._ Some of the parameters have been chosen somewhat arbitrarily
and no effort has been made to optimize them.  

## Environment
I am working on a mac and the version of fastai is `1.0.42` (so not
the version which is the most up to date). FastAI doesn't prioritize
support for macos, so it was not clear from the outset that the
process would work and the fact that working without a GPU does not
cause any issue.

## Data
For illustration I am using data that I have been collected and which
is available on [kaggle][kaggle-la-permanence].  This dataset contains
two timeseries.  

After some processing, we obtain a `pandas` dataframe `df` that will
be used for **training** and **validation**:
<p align="center">
<img src="{{site.baseurl}}/assets/regression-tab-data-fastai/df-output.png" alt="Output of dataframe df"/>
</p>
and a dataframe `test` that will be used for inference:
<p align="center">
<img src="{{site.baseurl}}/assets/regression-tab-data-fastai/df-output.png" alt="Output of dataframe df"/>
</p>

## Imports
As far as the code that is shown in this post is concerned, the necessary imports
are as follows:
```python
from fastai.tabular import Categorify, TabularList, TabularModel
from fastai.basic_train import Learner, load_learner, DatasetType
from fastai.data_block import FloatList
import torch.nn.functional as F
```


## The main ingredients
For training, 
the `Learner` requires the following ingredients:
- a `TabularDataBunch` and   
- a `TabularMoel`.  
For inference, we will need a `TabularList`.  


## The tabular databunch: `data`
The next paragraphs set the parameters needed to create the
`TabularDataBunch`.  

# Categorical, continuous, and dependent variables
They are chosen as follows:
```python
cat_names = ['Minute', 'Hour', 'DayOfWeek']
cont_names = ['DayOfYear']
dep_var = 'y'
```

# Transformations
The categorical variables will be categorified, the continuous
variable will be left untouched:
```python
procs = [Categorify]
```
# Validation indices
We specify the index range for the validation set.  Since we are
working with a timeseries, we choose the last two weeks for
validation (there is one record for every minute):
```python
ONE_WEEK = 7*24*60
valid_idx = slice(len(df) - 2*ONE_WEEK, len(df))
```
# The path
This is [used internally][fastai-databunch-doc] for temporary files:
```python
path = '.'
```

## Create the databunch
For this we use `fastai`'s [data block API][fastai-data-block-api]
```python
data = (TabularList.from_df(df,
                            path=path,
                            cat_names=cat_names,
                            cont_names=cont_names,
                            procs=procs)
                           .split_by_idx(valid_idx)
                           .label_from_df(cols=dep_var, label_cls=FloatList)
#                            .add_test(test)
                           .databunch()
       )
```
_Remarks._
- When we create our `Learner`, we will need the embedding
  and the ouput sizes of our data.  These are the attributes `emb_szs`
  and `c` (although they can also be calculated directly by hand).  
  
  Creating a `TabularDataBunch` directly from the class's
  `from_df` method generates the attribute `c` but not `emb_szs`.  On
  the other hand, the `TabularList` generates the attribute `emb_szs`
  but not `c`.  Using the data block API as above allows to generate
  both attributes.  
- Setting `label_cls` with [`FloatList`][fastai-floatlist-doc] is
  needed since we want to do
  regresssion rather than classification.  
- I did not use `.add_test(test)`.  Somehow I ran into issues and I
  found other ways to do inference, see below.  

## Additional `data`-dependent parameters
The following parameters will be needed to construct the `Learner`:  

```python
y_range = [df[dep_var].min() - 1, df[dep_var].max() + 1]
emb_szs = data.get_emb_szs()
n_cont = len(data.cont_names)
out_sz = data.c
```

_Remark._ We take `y_range` a little larger than the actual range of
the dependent variable `y`, see the [video for lesson
5][fastai-lesson-5-2019-y-range-explanations] (Deep
Learning 2019) for explanations by Jeremy Howard.  

## The model
We set further parameters to define the architecture:
```python
layers = [200, 100]
ps = [0.01, 0.01]
emb_drop = 0.04
```
Construct the model:
```python
model = TabularModel(emb_szs=emb_szs,
                     n_cont=n_cont,
                     out_sz=data.c,
                     layers=layers,
                     ps=ps,
                     emb_drop=emb_drop,
                     y_range=y_range)
```

## The loss function

There remains to define the loss function.  Since we are doing
regression, we use the mean squared error.  We will also use this for
our metric.  
```python
loss_fn = F.mse_loss
```

## The learner
With the `data`, `model`, and `loss_fn`, we can now create the
learner:

```python
learn = Learner(data, model)
learn.loss_fn = loss_fn
learn.metrics = [loss_fn]
```

## Training
```python
learn.fit_one_cycle(4, 1e-3)
```

## Inference
Now we wish to make predictions on our `test` dataframe.  To this end
we will create a tabular [inference
learner][fastai-inference-learner-doc].  The test data, which is a
dataframe will be passed
as an `ItemList`:  
```python
test_list = TabularList.from_df(test,
                                cat_names=cat_names,
                                cont_names=cont_names,
                                procs=procs)
```
The [`export()`][fastai-learner-export-doc] method will export the state of `learn` to
`path/export.pkl`. 
```python
learn.export()
```

We now create a _new_ learner, for inference, with our test data:  
```python
learner = load_learner(path, test=test_list)
```

We can now invoke the learner's [`get_preds()`][fastai-get-preds-doc]
method, not omitting to set `ds_type` to `DatasetType.Test`:  
```python
test_preds, test_targs = learner.get_preds(ds_type=DatasetType.Test)
```

## References
The following proved extremely useful in developing the above
workflow.  
- A [question from Josh Varty][josh-varty-github-issue-1623] on github.
- `fastai`'s forum thread [How can i treat the dependent variable of a
  TabularDataBunch as
  continuous?][fastai-forum-continuous-dependent-variables-for-tabular-data]
- `fastai`'s [tabular inference learner
  documentation][fastai-tabular-inference-learner-doc]  and how to
  [Create a learner for inference][fastai-how-to-create-a-learner-for-inference]
- `fastai`'s forum thread [Making predictions in
  v1][fastai-forum-making-predictions-in-v1]



[fastai-docs]: https://docs.fast.ai
[kaggle-la-permanence]: https://www.kaggle.com/antoinechoffrut/la-permanence
[fastai-databunch-doc]: https://docs.fast.ai/basic_data.html#DataBunch
[fastai-data-block-api]: https://docs.fast.ai/data_block.html
[fastai-lesson-5-2019-y-range-explanations]: https://www.youtube.com/watch?v=CJKnDu2dxOE&feature=youtu.be&t=00h43m15s
[fastai-floatlist-doc]: https://docs.fast.ai/data_block.html#FloatList
[fastai-tabular-inference-learner-doc]: https://docs.fast.ai/tutorial.inference.html#Tabular
[fastai-inference-learner-doc]: https://docs.fast.ai/tutorial.inference.html
[fastai-how-to-create-a-learner-for-inference]: https://docs.fast.ai/tutorial.inference.html#Create-a-Learner-for-inference
[fastai-forum-making-predictions-in-v1]: https://forums.fast.ai/t/making-predictions-in-v1/24888
[josh-varty-github-issue-1623]:  https://github.com/fastai/fastai/issues/1623
[fastai-learner-export-doc]: https://docs.fast.ai/basic_train.html#Learner.export
[fastai-get-preds-doc]: https://docs.fast.ai/basic_train.html#Learner.get_preds
[fastai-forum-continuous-dependent-variables-for-tabular-data]: https://forums.fast.ai/t/how-can-i-treat-the-dependent-variable-of-a-tabulardatabunch-as-continuous/31670
