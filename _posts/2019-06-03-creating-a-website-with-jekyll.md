---
layout: post
title:  "Creating a website with jekyll"
date:   2019-06-03 13:37:48 +0100
categories: jekyll
---

These are instructions to create the simplest possible (static)
website with Jekyll and publish it on GitHub.  

## Jekyll
# Jekyll install
Follow the [instructions][jekyll-install-instructions].


# Jekyll tutorial
I have followed [Mike Dane/Giraffe
Academy][giraffe-academy-videos]'s walkthrough videos, recommended on
[jekyll][jekyll-walkthrough-videos].  
See also the [README][minima-readme] file for the theme minima.


## Creating a website locally
# Generate the basic structure
Move into the directory where you want to create the website's
directory, then run 
{% highlight jekyll %}
jekyll new github-page
{%endhighlight%}
where `github-page` will be the name for the website's folder.  

At this point jekyll has already scaffolded a basic website with the
default theme [minima][minima].

Edit your `_config.yml` file (located in the website's folder
`github-page`) and set:
```
baseurl: "/github"
```


# View the website
Let's view the website before making any changes.
Run

{%highlight bash%}
cd github-page
bundle exec jekyll serve
{%endhighlight%}


_Note._  I have had an error message prompting me to run:
{%highlight bash%}
bundle update --bundler
{%endhighlight%}

The terminal should show give you information about the website, and in
particular
```
    Server address: http://127.0.0.1:4000/github-page/
  Server running... press ctrl-c to stop.
```


Open then your browser and enter the server address,
**including** the slash `/` at the end.  


# Making changes to your files
Whenever a file such as an `html` file or `markdown` file is modified,
saving it and refreshing the browser will update the page.  On the
other hand, if the `_config.yml` file is modified, then the command
`bundle exec jekyll serve` must also be run in order to take into
account these changes.

If making changes to your files seem to have no effect on the webpage,
then return to the terminal and read the `ERROR` messages.  The page
itself will not tell you about these errors.   

# Create a new post
Create a new file under `_posts`, making sure that its name begins
with a date (whichever you choose) in the format
`YYYY-MM-DD-name-of-your-post.ext` (replacing `ext` with the extension
that makes sense for the type of your file, e.g. `html` or `md`).

## Hosting your website on GitHub

# On your browser
- Log in to your GitHub account.  
- Create a **new repository** and name it `github-page`.  
- Leave it as **public**.  
- Do _not_ initialize the repository with a README.  
- Click on **Create repository**.  

Next we need to create a repository for the website.  


# At the terminal
From your website's folder `.../github-page`, run
```bash
git init
git checkout -b gh-pages  # create branch "gh-pages" and switch to it
git status -s  # to see what git sees
```
At this point you should probably only want to let git know about the
following:  
```
.gitignore
404.html
Gemfile
Gemfile.lock
_config.yml
_includes/
_layouts/
_posts/
about.md
index.md
```
Edit the `.gitignore` with the files you don't want to include in the
repository.  

Add and commit:
```bash
git add .
git commit -m "Initial commit"
```
Provided you have setup SSH keys to securely connect with GitHub, run
```
git remote add origin git@https://github.com/username/github-page.git
git push origin gh-pages
```

# Back to the browser
Refresh the web page on your new repository on GitHub, or enter again
```
https://github.com/username/github-page
```
to verify that it got updated correctly.  

Click on **Settings** and scroll down to **"GithHub Pages"** to read
that 
> Your site is published at
> https://username.github.io./github-page/




___  

## Going a little bit beyond


# Locating the theme files
That I am using the default theme minima can be verified by looking
into `_config.yml` which is in the website's main folder.  The default
files for the theme `minima` (which is used by default) are not
located in the website's folder.  To locate the theme's gem, run

{%highlight bash%}
bundle show minima
{%endhighlight%}

which may return something like

{%highlight bash%}
/usr/local/lib/ruby/gems/2.6.0/gems/minima-2.5.0
{%endhighlight%}

# Editing layouts

To customize layouts, create a subfolder
`_layouts`:

{%highlight bash%}
mkdir _layouts
{%endhighlight%}

and either create a layout from scratch and save it there, or else
[override an existing layout][jekyll-override-themes] which are found
with `bundle show minima` as indicated above.  Then, copy whatever you
wish to edit into your website's folder.

# Making changes to the default settings
The settings are somewhat split in various places.  For example, 
- to edit the navigation links, see
  [here][minima-edit-navigation-links];  
- to edit the links to your social media, edit the `social.hml` file
  under `_includes`.


[jekyll-install-instructions]: https://jekyllrb.com/docs/
[giraffe-academy-videos]: https://www.youtube.com/watch?v=T1itpPvFWHI&list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB
[jekyll-walkthrough-videos]: https://jekyllrb.com/tutorials/video-walkthroughs/
[minima-readme]: https://github.com/jekyll/minima
[jekyll-override-themes]: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
[minima]: https://github.com/jekyll/minima
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
[minima-edit-navigation-links]: https://github.com/jekyll/minima#customize-navigation-links
