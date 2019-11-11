---
layout: post
title:  "Interacting with kaggle datasets"
date:   2019-11-11 09:30:00 +0000
categories: unix
---


This post contains mostly excerpts from:  
- [the kaggle API documentation](https://www.kaggle.com/docs/api)
  - [subsection "Interacting with
    Datasets"](https://www.kaggle.com/docs/api#interacting-with-datasets) 
- [the kaggle GitHub repository
  documentation](https://github.com/Kaggle/kaggle-api)
  -  [subsection "Datasets"](https://github.com/Kaggle/kaggle-api#datasets)

---

# Installation  
Install the `kaggle` API with  
```bash
pip install kaggle
```

# Authentication  
From [My Account](https://www.kaggle.com/account), scroll down and
click on **Create New API Token**, which will download a new
authentication token in a file `kaggle.json`.  Save this token in
`~/.kaggle`, and change permissions:  
```bash
chmod 600 ~/.kaggle/kaggle.json
```

# Generate a metadata file  
With a folder created for the dataset,  
```bash
kaggle datasets init -p /path/to/dataset
```
The metadata is saved in a file `dataset-metadata.json`  with:  
```json
{
  "title": "INSERT_TITLE_HERE",
  "id": "kaggleusername/INSERT_SLUG_HERE",
  "licenses": [
    {
      "name": "CC0-1.0"
    }
  ]
}
```
Replace `INSERT_SLUG_HERE` with the name of the dataset as it appears
on the kaggle account.  
*Note.*  The kaggle API documentation (concerning kernels, but
presumably this should for datasets as well) states:  
>As you add your title and slug, please be aware that Kernel titles
>and slugs are linked to each other. A Kernel slug is always the title
>lowercased with dashes (-) replacing spaces and removing special
>characters.  

There seems to be an ambiguity.  By "title" in the above description,
it seems to mean the name of the name of dataset on the kaggle
account, not the title as in the JSON file.  


Enter any additional field in `kaggle.json` as desired: subtitle,
description, etc.  See the [documentation on dataset
metadata](https://github.com/Kaggle/kaggle-api/wiki/Dataset-Metadata). 


# Create dataset
```bash
kaggle datasets create -p /path/to/dataset
```


# Upload a new version of the dataset onto kaggle  
```bash
kaggle datasets version -p /path/to/dataset -m "Your message here"
```
Add `-d` to delete old versions of the dataset in the kaggle account:  
```bash
kaggle datasets version -p /path/to/dataset -m "Your message here" -d
```

# Download dataset from kaggle account  
```bash
kaggle datasets download -p PATH
```
where `PATH` is the path to the folder where files are to be
downloaded.  
Download specific files:  
```bash
kaggle datasets download -p PATH -f FILENAME
```
Force file download:  
```bash
kaggle datasets download -p PATH -o
```

Note that files may be downloaded as `zip` files.  They can be unzip
automatically with:  
```bash
kaggle datasets download -p PATH --unzip
```
(the zip file will be deleted upon completion).
