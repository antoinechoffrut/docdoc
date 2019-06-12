---
layout: post
title:  "Creating image datasets with Google and fastai"
date:   2019-06-10 14:16:00 +0100
categories: datasets
---


This post very closely follows [this fastai
lesson][fastai-lesson2-download] and a post by [Adrian
Rosebrock][adrian-rosebrock-post].  It only deals with the creation of
datasets and in particular imports minimal libraries.  

# Setup
I am using Safari on a Mac and I am using the [fastai v1][fastai-v1-docs] library.  

# Imports
```python
import os
import shutil
from pathlib import Path
from fastai.vision.data import download_images, verify_images
```

# The master folder
Create the folder which will contain the folders with the datasets:
```python
path = Path(os.path.join(os.path.expanduser('~'), 'Data', 'image-datasets'))
try:
    path.mkdir(parents=True, exist_ok=False)
except OSError as e:
    print(e)

```

# The url file
We will run `javascript` on our browser to generate a file containing the urls for the
images that later will be downloaded.  This file will be named
`urls.txt` and it is assumed that it will be saved under the `Downloads` folder
by the browser.
```pyhon
url_download = os.path.join(os.path.expanduser('~'), 'Downloads', 'urls.txt')
```
**Important.**  
If a file `urls.txt` already exists, the browser will choose a
different name (namely `urls2.txt`) and in turn we run risk of using
the wrong set of urls when downloading images.  To avoid this
situation, delete first the file `urls.txt` before proceeding.  
```python
try:
    os.remove(url_download)
    print(f'File {url_download} already existed, has been deleted.')
except OSError as e:
    print(e)
```

# Obtaining ruls for the images from Google
_Note._ The instructions on [fastai][fastai-lesson2-download] didn't
quite work for me.  I haven't investigated the issue but
`window.open()` seems to have no effect and no file gets downloaded.
I suspect it may have to do with the browser that I am using.
Instead, I follow [Adrian Rosebrock's post][adrian-rosebrock-post]

1. Close the javascript console if it is already open (for instance if
you have already generated one set of images and wish to generate
another one), and (re-) open it.  (I have had issues with the console
still generating the list of urls for the previous query, and it
appeared to be resolved when closing the javascript console, but I
haven't investigated this issue seriously.)  
2. Search for the desired images on `https://images.google.com`.  
3. Scroll down the page and click on `Show more results` until you are
   satisfied with the number of images that appeared on the browser.  
4. Run the following three blocks of javascript, one at a time:
```javascript
var script = document.createElement('script');
script.src = "https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js";
document.getElementsByTagName('head')[0].appendChild(script);
```
```javascript
var urls = $('.rg_di .rg_meta').map(function() { return JSON.parse($(this).text()).ou; });
```
```javascript
var textToSave = urls.toArray().join('\n');
var hiddenElement = document.createElement('a');
hiddenElement.href = 'data:attachment/text,' + encodeURI(textToSave);
hiddenElement.target = '_blank';
hiddenElement.download = 'urls.txt';
hiddenElement.click();
```  

At this point, a file `urls.txt` should have downloaded automatically
into the `Downloads` folder.  

Let's say that the images are of the Eiffel tower:
```python
img_tag = 'eiffel_tower'
```

Move and rename the url file:  

```python
file = f'urls_{img_tag}.txt'
shutil.copy(url_download, os.path.join(str(path), file))
with open(os.path.join(str(path), file)) as f:
    nb_lines = len(list(f))
    print(f'File {file} contains {nb_lines} lines.\n')
```

# Download and verify images with fastai
Let fastai's [`download_images`][fastai-building-your-own-dataset-doc] do the work:  
```python
dest = path/img_tag
print(f'Downloading images to {str(dest)}...')
download_images(path/file, dest, max_pics=110, max_workers=0)
```

The [`verify_images`][fastai-building-your-own-dataset-doc] will delete images that are not suitable:  
```python
print(f'Verifying images in {str(dest)}\n\n')
verify_images(dest)

nb_images = len([iq for iq in os.scandir(str(dest))])
print(f'\nThere are {nb_images} image files in {str(dest)} after verification.')
```

[fastai-lesson2-download]: https://github.com/fastai/course-v3/blob/master/nbs/dl1/lesson2-download.ipynb
[fastai-v1-docs]: https://docs.fast.ai
[adrian-rosebrock-post]: https://www.pyimagesearch.com/2017/12/04/how-to-create-a-deep-learning-dataset-using-google-images
[fastai-building-your-own-dataset-doc]: https://docs.fast.ai/vision.data.html#Building-your-own-dataset
