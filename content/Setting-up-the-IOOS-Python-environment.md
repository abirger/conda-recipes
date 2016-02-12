+++
weight = "10"
type = "post"
draft = false
sidebar = true
Title = "Installing the IOOS Anaconda Environment"
date = 2015-08-04T07:56:39Z

+++

One approach for running Anaconda is to go to https://store.continuum.io/cshop/anaconda/ and download the Anaconda installer, which installs a large number of packages into the root environment.
We prefer to download just a minimal Anaconda (Miniconda) and create our own environment using just the packages we need.  
<!--more-->

In addition, there is currently a [known bug with the full Anaconda installer on Windows] (https://groups.google.com/a/continuum.io/forum/#!topic/anaconda/w8jewHj2T1A) that prevents the full Anaconda distribution from working properly with custom environments, while the Miniconda installation is still working.
If for some reason the full Anaconda is preferred (e.g. the previously installed Anaconda just stopped working properly after update), there is a temporary [workaround](https://github.com/ioos/conda-recipes/issues/581#issuecomment-155606987) for that bug.

# Installing Miniconda

## Windows

Navigate to http://conda.pydata.org/miniconda.html and download the proper installer for you Windows platform (32 or 64 bits).

We recommend to download the Python 2 version of Miniconda as not all packages are Python 3-compliant yet, so the IOOS environment you create below is based on Python 2.   You can still create new Python 3 environments using the Python 2 verson of Miniconda, so you are not limiting yourself. 

When installing you will be asked if you wish to make the Anaconda Python your default Python for Windows. If you do not have any other installation that is a good option.  If you want to keep multiple versions of python on your machine (e.g. ESRI-supplied python, or both 32 and 64 bit versions of Anaconda), then don't select the option to modify your path or modify your windows registry settings.


## Linux and OSX command line

```bash
url=http://repo.continuum.io/miniconda/Miniconda-latest-Linux-x86_64.sh
curl $url -o miniconda.sh
bash miniconda.sh -b
export PATH=$HOME/miniconda/bin:$PATH
conda update --yes --all
```

# Creating the IOOS environment

## Windows

Download the [environment.yml](https://raw.githubusercontent.com/ioos/conda-recipes/master/environment.yml) by right clicking with the mouse and choosing
`save as...`

## Linux and OSX command line

```bash
url=https://raw.githubusercontent.com/ioos/conda-recipes/master/environment.yml
curl $url -o environment.yml
```

## All platforms

The `environment.yml` file is just a text file with the environment name, what channel we want to add,
and the list of the software that will be installed.
To create the file, open a terminal Window where you saved the file and type the following commands to create the environment and to activate it, depending on your OS:

```bash
conda env create environment.yml
source activate IOOS  # OSX and Linux
activate IOOS  # Windows
```

# Exiting the IOOS environment
If you want to leave the IOOS environment and return to the root Anaconda environment, you can type

```bash
source deactivate  # OSX and Linux
deactivate  # Windows
```

Remember to always add miniconda to the path and to activate the IOOS environment when starting a new session.
On Linux and OSX you can add the line below to your `.bashrc` and make the IOOS environment default,
but that is not recommended! You might have other applications that relies on the default system Python.

```bash
export PATH=$HOME/miniconda/bin:$PATH && source activate IOOS
```

On Windows, if you chose to install the Anaconda distribution as your default Python,
all you need to do is to activate the environment `activate IOOS`.
If you chose to **not** add the Anaconda distribution as your default Python you will need to start it using the Anaconda terminal icon.


# Note about the channels

When typing `conda info` you should see the default channel, from Continuum, and the `ioos` channel that was automagically added via the `environment.yml` file.
If you don't see the default continuum channel, add it by typing:

```bash
conda config --add channels defaults --force
```

You can have mix-and-match more channels. However, bare in mind that packages can be inconsistent with each other and you might end up with an unstable environment.
We recommend to keep the default channel + 1 other only.

We also recommend to display where the package is coming from using by setting the config option, as follows:

```bash
conda config --set show_channel_urls True
```

Hopefully that will be the [default behavior](https://github.com/conda/conda/pull/1771) in conda soon.