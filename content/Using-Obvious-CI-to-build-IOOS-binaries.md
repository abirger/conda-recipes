+++
weight = "50"
type = "post"
draft = false
sidebar = true
Title = "Using Obvious CI to Build IOOS Binaries"
date = 2015-08-04T07:56:39Z

+++




[Obvious-CI](https://github.com/pelson/Obvious-CI) is a collection of tools that help with continuous integration like [travis-ci](https://travis-ci.org/ioos/conda-recipes/builds) and [AppVeyor](https://ci.appveyor.com/project/comtbot/conda-recipes/history).
<!--more-->


Using Obvious-CI, the single script `obvci_conda_build_dir.py` can build all binaries in the repository, ordered by their dependency.  Note that `obvci_conda_build_dir.py` reads the packages that are already on the channels and does not build if they are the same.

# Instructions

* Type `conda info` to see what channels you have.  Remove any channels from your conda config that are not from continuum.  For example, if you see a channel called `rsignell`, remove it like this:

```bash
conda config --remove channels rsignell -f
```
 
* Add the channel you are trying to install packages to.  This was the build process will have access to the requirements as they are built.  If building packages to upload to `ioos`, then do:

```bash
conda config --add channels ioos -f
```

* Remove everything from the cache, in order to force the build process to download packages from the locations specified in the conda-recipes:

```bash
conda clean --tarballs --index-cache --packages --source-cache -y
```

* Remove the source code from the build directory.  This will be system dependent, but for example:

```bash
rm /home/testbed/anaconda/conda-bld/linux-64/*
```

* Install obvious-ci

```bash
conda install -c ioos obvious-ci
```

* Download the conda-recipes

```bash
git clone https://github.com/ioos/conda-recipes.git
```

* If you are an IOOS anaconda admin, or you are building for your own personal repository, you may want to upload the packages as you build.  The `obvci_conda_build_dir.py` script will do that for you if you set a `BINSTAR_TOKEN`:

```bash
TOKEN=$(binstar auth -n NAME-OF-YOUR-TOKEN --max-age 22896000 -c --scopes api)
export BINSTAR_TOKEN=$TOKEN
```

* Build all the packages in conda-recipes (and upload to `ioos` channel if `BINSTAR_TOKEN` is set):  

```bash
obvci_conda_build_dir.py ./conda-recipes ioos --channel main
```