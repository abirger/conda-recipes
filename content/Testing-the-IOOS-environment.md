+++
weight = "30"
type = "post"
draft = false
sidebar = true
Title = "Testing the IOOS Environment"
date = 2015-08-04T07:56:39Z

+++


You may run your iPython notebook without testing; however, a simple procedure allows verifying that the environment and notebook were set up properly.
<!--more-->


1. Grab and use any of the notebooks available [here](http://nbviewer.ipython.org/github/ioos/conda-recipes/blob/master/index.ipynb). Once you located a notebook that interests you you can download it using the upper right icon.  

2. If you don't have the Anaconda launcher installed, type `conda install launcher` to install it.

3. Click on the launcher icon to start the launcher application, or just type 'launcher' from the terminal (linux or mac) or Anaconda Command Prompt (windows).

4. From the Launcher, make sure that the `ioos` environment is selected, and then click the `launch"`button to the right of the `ipython-notebook` app.  If you don't see the `launch` button, you need to click on `install` to install the app.  

5. Once the Notebook is launched, you should see a list of directories and files, and near the top, instructions for importing a notebook.  Note that the `Ipython Notebook` has now changed it's name to `Jupyter`. 

6. Import the downloaded notebooks.  You can drag the downloaded notebook onto the Notebook list, and then click "upload", or click on . 

7. In the Notebook, click on `Cell=>All Output=>Clear` to clear the existing output, and then `Cell=>Run all` to see if the output is recreated.


If you just want to test the environment click on the icon below:

[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org/repo/ioos/conda-recipes)