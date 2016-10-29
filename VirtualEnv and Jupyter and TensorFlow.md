# TensorFlow in iPython Notebook in VirtualEnv

How to setup your computer with a virtual environment, within which you can run tensorflow in interactive iPython Jupyter notebooks.

*Note: These instructions are specific to Mac users*

--

### Pre-setup

Make sure you have [Python](https://www.python.org/downloads/) installed on your computer.

Make sure you have [Python's package manager](https://pip.pypa.io/en/stable/installing/), pip, installed.

Upgrade pip to its latest version.
You can do this from the terminal with `sudo pip install --upgrade pip`.


### Install iPython Jupyter Notebook

This is most simply done from the terminal with `sudo pip install jupyter`.

[See here for full instructions.](http://jupyter.readthedocs.io/en/latest/install.html)


### Install virtual environments. 

These are isolated environments on your computer within which you can install software that runs independently of other software on your computer.

This is most simply done from the terminal with `sudo pip install virtualenv`.

[See here for full instructions.](https://virtualenv.pypa.io/en/stable/installation/)

### Create a virtual environment called TensorFlow to run tensorflow in

This is most simply done by (in terminal) navigating to the directory you want this environment's folder to be in (for example, your home directory) and typing `virtualenv tensorflow`

*Note: to install this environment with a specific version of Python, use `virtualenv --python=myPythonVersion tensorflow` where `myPythonVersion` could be, for example, `python2.7`*

*Note: to navigate to your home directory, type `~` in terminal*


### Create an easy alias to activate your environment with

To enter (or activate) your environment, you must be in the directory you installed it in, and type `source tensorflow/bin/activate`. Since this is so long to write, we'll create an alias that stands for this phrase. Our alias will be `tensorflow`. Therefore, whenever you type `tensorflow` in terminal, your virtual env will start. In other words, writing `tensorflow` will be analogous to writing `source tensorflow/bin/activate`.

In your home directory in terminal, type `vim .bashrc`. A text file will open. Press `i`. You will enter insert mode.
In a new line, enter `alias tensorflow="source ~/tensorflow/bin/activate"`. Press the escape key. Then, type in `wq` and press enter. You will exit the text editor and be redirected to the regular terminal window. To apply the changes you just made, type in `source .bashrc` in terminal.

### Install tensor flow

First, open our virtual env using the alias we just created by typing `tensorflow` in terminal. You should see `(tensorflow)` appear before your terminal name, for example `(tensorflow) Bens-MBP-2:~ bensnell$`.

[Use the tensorflow installation instructions for pip to install tensorflow.](https://www.tensorflow.org/versions/r0.11/get_started/os_setup.html#pip-installation) You must first download a binary with a command that looks something like this: `export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-0.11.0rc1-py2-none-any.whl`. Then, you will compile the binary with a command that looks like this: `pip install --upgrade $TF_BINARY_URL`. 

*Note: don't include `sudo` before your second command. There is no need to install for all users of the computer because this installation of tensorflow is specific to our virtual environment.*

### Install matplotlib to plot graphs

In terminal in the virtual environment, type in `pip install matplotlib`.


### Demo iPython Jupyter notebook

In terminal, type in `jupyter notebook`. An interactive python notebook will start up in your browser. To import all necessary libraries, type in:

	import tensorflow as tf
	import numpy as np
	import matplotlib.pyplot as plt.

To ensure all plots draw with matplotlib don't open in a new window (this is very annoying), also type in:

	%matplotlib inline

To run a piece of code in an iPython notebook, press `SHIFT` + `RETURN`.

Make sure to save the notebook with `COMMAND` + `S` to a location of your choosing.

To exit the notebook, in terminal, simply type `CONTROL` + `C`.

### Exit your virtual env

To exit out of the tensorflow virtual environment, type `deactivate` in terminal. You should see `tensorflow` be removed from the running line in terminal.

--

Many thanks to Aman Tiwari