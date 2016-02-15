+++
weight = "0"
type = "post"
draft = false
sidebar = true
Title = "About IOOS Conda Packages & Python Environment"
date = 2015-08-04T07:56:39Z
Url = "index.html"
+++

<!-- For a single homepage put in FrontMatter url = "index.html"; for a summary of multiple documents on one page do not put url parameter there at all -->

<!-- PUT SUMMARY CONTENT HERE BEFORE "MORE" COMMENT-->
This site contains the instructions on how to setup and run the IOOS Python Virtual Environment in order to use the conda packages that are useful to the IOOS community. These conda packages were created with the [conda recipes](https://github.com/ioos/conda-recipes/), and shared with the community at [Anaconda.org](https://anaconda.org/ioos).
<!--more-->

<!-- ADDITIONAL CONTENT MAY BE PLACED AFTER "MORE" FOR A SINGLE PAGE -->



[![build status](https://travis-ci.org/ioos/conda-recipes.svg)](https://travis-ci.org/ioos/conda-recipes)&nbsp;[![Build status](https://ci.appveyor.com/api/projects/status/behpiwxfraxcruv3?svg=true)](https://ci.appveyor.com/project/comtbot/conda-recipes)&nbsp;[![Circle CI](https://circleci.com/gh/ioos/conda-recipes/tree/master.svg?style=svg)](https://circleci.com/gh/ioos/conda-recipes/tree/master)&nbsp;[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org/repo/ioos/conda-recipes)

## The IOOS Python Environment
For IOOS python users, we recommend the [Anaconda Scientific Python Distribution](https://store.continuum.io/cshop/anaconda/) as the easiest way to get all the custom packages needed to run the IOOS system tests.  [more info](https://github.com/ioos/conda-recipes/wiki/Why-we-use-and-recommend-Anaconda)

### Why we use and recommend Anaconda

Anaconda users can just `conda install`, which installs not only binary packages for their platform, but the binary libraries they depend on.  So it's easier than `pip install` and, thanks to binary relocation, more powerful than python wheels.  System-level installation of libraries and admin
privileges are not required.  Check out [Travis Oliphant's blog piece](http://technicaldiscovery.blogspot.com/2013/12/why-i-promote-conda.html) for more info.

### Install & Configure
* [Setting up the IOOS Python environment](https://github.com/ioos/conda-recipes/wiki/Setting-up-the-IOOS-Python-environment)

### Test
* [Testing the IOOS environment](https://github.com/ioos/conda-recipes/wiki/Testing-the-IOOS-environment)

### Customize 
* [Customizing the notebook settings](https://github.com/ioos/conda-recipes/wiki/Customizing-the-notebook-settings)

### Get Help

Some bugs, like hard-coded paths, might surface when using these packages. If you encounter this or other problems, [raise an issue](https://github.com/ioos/conda-recipes/issues).

**Acknowledgement**: The recipes here are automatically built using [Travis-CI](https://travis-ci.org/ioos/conda-recipes) with the assistance of [Obvious-CI](https://github.com/pelson/Obvious-CI/https://github.com/ioos/conda-recipes/blob/master/.travis.yml#L14-L31).




