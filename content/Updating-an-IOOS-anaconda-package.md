+++
weight = "20"
type = "post"
draft = false
sidebar = true
Title = "Updating an IOOS Anaconda Package"
date = 2015-08-04T07:56:39Z

+++


If you have a package that you would like to update, a package that already exists on the IOOS anaconda channel (http://conda.anaconda.org/ioos), you can try going to the `meta.yaml` file for that package, clicking on `edit` and changing the version number.  
<!--more-->

Example:  Let's say a new version of [pyoos](https://github.com/ioos/pyoos/releases) is released, changing the version number from `0.6.2` to `0.6.3`.   To get this updated version on the anaconda ioos channel, you just change the version number in the pyoos `meta.yaml` file by going [here](https://github.com/ioos/conda-recipes/blob/master/pyoos/meta.yaml#L3-L7) and clicking on the pen icon to edit.  When you are done making the edit, select `Create a new branch for this commit and start a pull request`.   The pull request will automatically test to see if the new version builds on linux and windows (and hopefully soon on mac).
