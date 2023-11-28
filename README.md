# README - blog

nbdev and quarto are great tools for creating a blog. both were used to create this blog.

The first step is to install nbdev. I used the following guide [nbdev.fast.ai/tutorials](https://nbdev.fast.ai/tutorials/tutorial.html).

i'm using micromamba to manage my conda environments. in my jupyter environment i ran the following commands:

`micromamba install -c fastai -y nbdev`

`nbdev_install_quarto`

I then created a new repository on github and cloned it to my local machine.

the next step is to create a new nbdev project, and quarto docs.

Folder structure

Below is an overview of the general folder structure for a blog within a nbdev site 📁:
```markdown
nbs/blog
├── index.qmd
└── posts
    ├── 2022-07-28-nbdev2
    │   ├── cover.png
    │   ├── index.qmd
    │   ├── ...
    └── 2022-08-25-jupyter-git
        ├── friendly-conflict.png
        ├── index.qmd
        └── ...
    ...
```

to exclude README.md from the blog posts, i change the following line in MANIFEST.in

include README.md -> exclude README.md

every blog post could be written in a notebook, or markdown file.

when using a notebook, the notebook should be converted to qmd before committing to git., and publishing to the blog.

for example:

`quarto convert blog/posts/2023-11-22-RNA-seq-RSV/RNA-seq.ipynb`

important to note that in the settings.ini file, ichanged the following lines:

doc_path = _docs  -> doc_path = _proc/_docs

lib_path = blog -> lib_path = nbs/blog

to publish the site with gh-pages, i used the following command from nbs folder:

`nbdev_proc_nbs && cd _proc/ && quarto publish gh-pages --no-browser`
 
 the following command can be used to publish the site from nbs folder:

`cd nbs/`

`quarto publish gh-pages`

quatro publsih gh-pages will create a new branch called gh-pages, and push the site to that branch.

on github, i changed the settings to use gh-pages as the source for the site.

to update files on github still have to use git push main as the main branch is still the default branch and pointed to the remote main branch.

`git push`



# Links:
- 🌐 blog website is hosted at *[avivleemann.github.io/blog](https://avivleemann.github.io/blog/)*
- 📦 package volcanoPlot github repository *[github.com/avivleemann/volcanoPlot](https://avivleemann.github.io/volcanoPlot/)*

