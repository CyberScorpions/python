# Setting up a Python ENV

Notes to setup a python environment.

I opted to use Anaconda to install python on the system.

However I am using `virtualenvwrapper` from within conda to create specific build environments.

## Anaconda

[Installation Instructions](http://conda.pydata.org/docs/installation.html)

### Docs

<http://conda.pydata.org/docs/>

<http://conda.pydata.org/docs/py2or3.html>

<https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/>


### Setup and environment

Once conda is installed. Commands to create and environemnt

    conda search "^python$"

    # python 2.7
    conda create -n py27 python=2.7 anaconda
    source activate py27
    source deactivate py27

    # python 3.6
    conda create -n py36 python=3.6 anaconda
    source activate py36
    source deactivate py36


### Update

##### conda

<https://conda.io/docs/user-guide/tasks/manage-conda.html>

    conda update --prefix $HOME/anaconda anaconda
    conda upgrade --prefix $HOME/anaconda anaconda

##### python
<https://conda.io/docs/user-guide/tasks/manage-python.html>

    conda update python

## virtualenvwrapper

[virtualenvwrapper docs](https://virtualenvwrapper.readthedocs.io/en/latest/install.html)

    source activate py36
    pip install virtualenvwrapper

Add to ~/.bashrc

    export WORKON_HOME=$HOME/.virtualenvs
    export PROJECT_HOME=$HOME/virtualenvwrapper_project_home
    source $HOME/anaconda/bin/virtualenvwrapper.sh

Continue

    mkvirtualenv py3.6.3 -p $(which python)
    workon py3.6.3

Delete

    deactivate
    rmvirtualenv py3.6.3
