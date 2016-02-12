+++
weight = "40"
type = "post"
draft = false
sidebar = true
Title = "Customizing the Notebook Settings"
date = 2015-08-04T07:56:39Z

+++


When deploying the notebook, you may want to customize and configure its behavior. You can easily customize it by including a configuration file and making a profile.
<!--more-->

* If the IOOS environment is selected in the launcher, all applications you launch from there will have the IOOS environment.   On a linux or mac terminal window, you can activate the `ioos` environment by typing `source activate ioos` and deactivate it by typing `source deactivate`. On windows, you can open an Anaconda command prompt (in the Anaconda programs folder) and type `activate ioos` to activate the ioos environment, or type `deactivate` to deactivate. 

* If you want to always have the notebook server start in the same location, you can edit the notebook startup configuration. Type `ipython locate profile default` to find out the directory where the configuration file is in.  Go to this directory and edit the file `ipython_notebook_config.py`, setting the value of `c.NotebookApp.notebook_dir`.  (Don't forget to uncomment the lines by removing the leading hashtag character). Note: If the file doesn't exist, type `ipython profile create` (or maybe `ipython profile create default`) to create a default configuration file.

On windows the line will look like this:

```
c.NotebookApp.notebook_dir = u'C:\\users\\rsignell\\documents\\github\\notebook'
```

On Mac and Linux, the line will look like this:

```
c.NotebookApp.notebook_dir = '/home/rsignell/my_notebooks'
```

* If you want to track your notebooks on github, you might want to set up the notebook server to create regular `.py` python versions of your notebooks (in addition to the `.ipynb` format that gets saved by default).  The instructions for this are here: http://stackoverflow.com/a/25765194/2005869

* Another option that allows to create your customized environment is to create your own profile rather than changing the default profile. This can allow users to have multiple environments on a single machine. The steps to edit the configuration file remain similar to ones explained above for the default profile. To create your own profile type

```
ipython create profile "profilename"
``` 

"Profilename" can be selected by the user. 

To find out the directory where the configuration file is in, type

```
ipython locate profile "profilename"
```

Edit the changes in the configuration file as mentioned in the bullet points above. In order for the profile changes to get activated, type in 

```
ipython notebook --profile=taran
```

Detailed instructions for making customized profile to have custom environment are described here: https://ipython.org/ipython-doc/dev/config/intro.html

