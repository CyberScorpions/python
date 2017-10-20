# Setting up a Python ENV

## Anaconda

Anaconda: <http://conda.pydata.org/docs/installation.html>

<http://conda.pydata.org/docs/>

<http://conda.pydata.org/docs/py2or3.html>

<https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/>


### Setup and environment

    conda create -n py27 python=2.7 anaconda
    source activate py27
    source deactivate py27

    conda search "^python$"
    conda create -n py36 python=3.6 anaconda
    source activate py36
    source deactivate py36


    conda install -n yourenvname [package]


### Update

##### conda
<https://conda.io/docs/user-guide/tasks/manage-conda.html>

    conda update --prefix /Users/sam/anaconda anaconda
    conda upgrade --prefix /Users/sam/anaconda anaconda

##### python
<https://conda.io/docs/user-guide/tasks/manage-python.html>

    conda update python

### dbus?

If this is your first install of dbus, automatically load on login with:
    mkdir -p ~/Library/LaunchAgents
    cp /Users/sam/anaconda/org.freedesktop.dbus-session.plist ~/Library/LaunchAgents/
    launchctl load -w ~/Library/LaunchAgents/org.freedesktop.dbus-session.plist

If this is an upgrade and you already have the org.freedesktop.dbus-session.plist loaded:
    launchctl unload -w ~/Library/LaunchAgents/org.freedesktop.dbus-session.plist
    cp /Users/sam/anaconda/org.freedesktop.dbus-session.plist ~/Library/LaunchAgents/
    launchctl load -w ~/Library/LaunchAgents/org.freedesktop.dbus-session.plist


## virtualenv

~~<https://virtualenv.pypa.io/en/stable/installation/>~~

~~source activate py36~~

~~pip install virtualenv~~

~~virtualenv virtualenv/py3.6.3 -p python3.6.3~~

**use virtualenvwrapper instead**


## virtualenvwrapper

<https://virtualenvwrapper.readthedocs.io/en/latest/install.html>

    pip install virtualenvwrapper

Add to ~/.bashrc

    export WORKON_HOME=$HOME/.virtualenvs
    export PROJECT_HOME=$HOME/virtualenvwrapper_project_home
    source /Users/sam/anaconda/bin/virtualenvwrapper.sh

Continue

    source activate py36

    mkvirtualenv py3.6.3 -p $(which python)
    workon py3.6.3

Delete

    deactivate
    rmvirtualenv py3.6.3
