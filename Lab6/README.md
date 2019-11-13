# 00 - Intro to Tools

This tutorial should get you up and running with your Python environment, plus give you the basics of Jupyter notebooks. Please complete part 1 before the exercise session on Friday, September 20. In that exercise session, we will go through the notebook in part 2 together. The OPTIONAL and UNGRADED homework 0 should be completed before the release of the NON-OPTIONAL homework 1 on Thursday, October 3.

## Part 1: Setting up your environment

* Install Anaconda, Python 3.7 version: [Anaconda](https://www.anaconda.com/distribution/#download-section).

*For Linux*: Open a terminal, go to the Downloads folder and execute:

```
bash ./Anaconda3-2019.07-Linux-x86_64.sh -b -p $HOME/Anaconda3
```

Check that `conda` is in your path. If `which conda` returns something like `/home/YOURUSERNAME/Anaconda3/bin/conda`, you are good to go. Otherwise execute
`echo 'export PATH="$HOME/Anaconda3/bin/:$PATH"' >> $HOME/.bashrc`. Next close the terminal and open a new window. Check `which conda` again.

* IF conda is already installed, run `conda update conda`.

* Install Git:

*For Ubuntu/Debian*: `sudo apt-get install git`

*For Fedora*: `sudo dnf install git`

*For Windows*:
Install it following this download link: [Git](https://git-scm.com/downloads). To execute Git commands, use the Git bash: home key - type "git bash" - enter.

[Git cheatsheet](http://rogerdudler.github.io/git-guide/)

* Clone the tutorials repo into a local folder:

```
git clone https://github.com/epfl-ada-2019/Tutorials
```

* or pull new changes if you already have it (from the tutorials local folder):

```
git pull
```

* Create a new environment:

*For Windows*: 
To execute Anaconda commands, use the Anaconda prompt: home key - type "anaconda prompt" - enter.
Also note that while it is possible to use Git commands on Anaconda prompt, we advise against it.

```
conda create -y -n ada python=3.7 scipy pandas numpy matplotlib
```

* Activate it:
    
```
conda activate ada
```

* List your environments:
    
```
conda env list
```

* Deactivate the current environment and remove an environment. (Do not run the remove command, as it will remove the environment you just installed ...)
    
```
conda deactivate
conda remove --name ada --all
```

[more info on managing environments](https://conda.io/docs/user-guide/tasks/manage-environments.html)

* Install [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) using conda (the ada environment needs to be activated):
    
```
conda install jupyterlab bokeh seaborn nb_conda_kernels
```

* Install some extensions using the Python package manager:
    
```
pip install jupyter_nbextensions_configurator
```

* IF you get an error about packages requiring cython and PyHamcrest, try the following:
```
pip install cython PyHamcrest jupyter_nbextensions_configurator
```

* IF you have later problems with widgets (conda version might not be the latest one!):
    
```
pip install --upgrade ipywidgets
    
jupyter nbextension enable --py widgetsnbextension
    
jupyter nbextension enable --py --sys-prefix widgetsnbextension
```

* Run a Jupyter notebook server (be sure to be at the tutorial's folder (`cd path/to/folder/`)). A browser window should open up for you.

```
jupyter lab
```

* IF you have more problems with widgets:

```
jupyter serverextension enable --sys-prefix jupyter_nbextensions_configurator nb_conda nb_anacondacloud nbpresent
```

* To shut down the server, close the window on your browser, then do CTRL+C in the terminal.

* IF you later have warnings about missing fonts, in Ubuntu the missing fonts are in `fonts-humor-sans` (to install them: `sudo apt install fonts-humor-sans`). You may also have to clean `matplotlib`'s font cache (~/.cache/matplotlib/) and restart your current Jupyter session, for matplotlib to take notice of the changes.

## Part 2: Overview of Jupyter notebooks

In [this tutorial](Intro%20to%20Jupyter%20Notebooks.ipynb) we explore the functionalities of the Jupyter notebooks. In this repository you can find the notebook we use during the tutorial.

Credits to [saloot](https://github.com/saloot) and [Michele Catasta](https://github.com/pirroh), on whose material this version is based.

## Part 3: Homework 0

Access Homework 0 (OPTIONAL and UNGRADED) [here](https://github.com/epfl-ada-2019/Homework/tree/master/00%20-%20Optional%20Homework). Clone the repo locally and take the opportunity to freshen up your Python skills, or to acquire them.

On Thursday, October 3, the first graded homework ("Homework 1") will be released.
