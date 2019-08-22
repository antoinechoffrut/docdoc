---
layout: post
title:  "Creating image datasets with Google and FastAI"
date:   2019-06-10 14:16:00 +0100
categories: datasets
---


This post very closely follows [this fastai
lesson][fastai-lesson2-download] and a post by [Adrian
Rosebrock][adrian-rosebrock-post].  It only deals with the creation of
datasets and in particular imports minimal libraries.  

For purpose of illustration, we will create a dataset consisting of
images of the Eiffel tower and the Tokyo tower.  The images will be
saved in two separate subfolders.

# Setup
- macOS Mojave (no GPU)
- Safari 12.1.1
- Python 3.7.1
- [FastAI][fastai-v1-docs] 1.0.42 


# Imports
```python
import shutil
from pathlib import Path
from fastai.vision.data import download_images, verify_images
```

# The master folder
Create the folder which will contain the folders with the datasets:
```python
path = Path.home() / 'Data' / 'image-datasets' / 'eiffel-tokyo'
try:
    path.mkdir(parents=True, exist_ok=False)
except OSError as e:
    print(e)

```

For **each** image, do the following.  

1. Set image tag `img_tag`:
   ```python
   img_tag = 'eiffel_tower'
   ```
2. **Important:**  delete any existing download file to avoid loading wrong urls
   from previous searches (if a file `urls.txt` already exists, the
   browser will save the new file as `urls2.txt`):
   ```python
   try:
     url_download.unlink()
     print(f'File {url_download.name} already existed, has been deleted.')
   except OSError as e:
     print(e)
	```

1.   Open browser or close javascript console if already open.  
1.  Search for desired images on google (corresponding to `img_tag`).  
1.  Scroll down to view as many results as desired.  
1.  Run following (one block at a time) in browser's javascript
    console:  
    - block 1:
    	 ```javascript
    	 var script = document.createElement('script');
    	 script.src =
    	 "https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js";
    	 document.getElementsByTagName('head')[0].appendChild(script);
    	 ```
    - block 2:
    	 ```javascript
    	 var urls = $('.rg_di .rg_meta').map(function() { return JSON.parse($(this).text()).ou; });
    	 ```
    - block 3: 
    	 ```javascript
    	 var textToSave = urls.toArray().join('\n');
		 var hiddenElement = document.createElement('a');
		 hiddenElement.href = 'data:attachment/text,' + encodeURI(textToSave);
		 hiddenElement.target = '_blank';
		 hiddenElement.download = 'urls.txt';
		 hiddenElement.click();
		 ```
 
    The last step should download a text file `urls.txt` into the
 	 `Downloads` folder with the list of URLs of the images from the
 	 Google search.    
1.  Move and rename URL file.  
    ```python
    urls = path/f'urls_{img_tag}.txt'
    shutil.copy(url_download, urls)
    with urls.open() as f:
      nb_lines = len(list(f))
      print(f"File '{urls.name}' contains {nb_lines} lines.\n")
    ```
	
1.  Let [fastai][fastai-building-your-own-dataset-doc] download images with provided URLs.  
    ```python
    dest = path/img_tag
    print(f"Downloading images to {dest.absolute()}...")
    download_images(urls, dest, max_pics=110, max_workers=0)
	```
1.  Let [fastai verify images][fastai-building-your-own-dataset-doc]
    (will delete images that are not suitable):  
    ```python
    print(f'Verifying images in {dest.absolute()}\n\n')
    verify_images(dest)
    nb_images = sum(1 for img in dest.glob('*.*'))
    print(f"\nThere are {nb_images} image files in folder '{dest.name}' after verification.")
    ```

	 



[fastai-lesson2-download]: https://github.com/fastai/course-v3/blob/master/nbs/dl1/lesson2-download.ipynb
[fastai-v1-docs]: https://docs.fast.ai
[adrian-rosebrock-post]: https://www.pyimagesearch.com/2017/12/04/how-to-create-a-deep-learning-dataset-using-google-images
[fastai-building-your-own-dataset-doc]: https://docs.fast.ai/vision.data.html#Building-your-own-dataset
