---
layout: post
title:  "Install New Laptop"
desc: "Describe how to install New laptop"
keywords: "Ubuntu"
date: 2016-11-25
categories: [Linux]
tags: [blog]
icon: fa-bookmark-o
---

# Down load Ubuntu and burn USB
1. Ubuntu [16.04](https://www.ubuntu.com/download/desktop) LTS version is used

2. How to burn .iso on usb in windows. [Link](https://www.ubuntu.com/download/desktop/create-a-usb-stick-on-windows)

# Install Ubuntu
1. BIOS configuration
On DELL, push F2 during start up of the computuer.
Configure the system to boot from USB.

# Install gnome-shell, terminator
gnome-shell

> sudo apt-get update
> sudo apt-get install ubuntu-gnome-desktop

terminator

> sudo apt-get install terminator

# Install Application
1. Install google [chrome](https://www.google.com/chrome/browser/desktop/index.html)

2. Install git  sudo apt-get install git


# Basic Python Configuration

## Vritual Environment
What is Python [virtual environment](https://www.dabapps.com/blog/introduction-to-pip-and-virtualenv-python/)
install virtualenv

> sudo apt-get install virtualenv

create a python virtual environment

> virtualenv -p /usr/bin/python2.6 <path/to/new/virtualenv/

Activate a virtual environment

>source env/bin/activate

Deactive a virtual environment
>deactivate

## pip
Install from a requirement file

> pip install -r requirements.txt

Create a requirement file from current pip installation

> pip freeze > requirements.txt

# Editor
[Atom](https://atom.io/)

# Anaconda
Anaconda is a freemium open source distribution of the Python and R programming languages for large-scale data processing, predictive analytics, and scientific computing, that aims to simplify package management and deployment. Its package management system is conda.
[Download](https://www.continuum.io/downloads)
I used the python 2.7 version. Run the below command to install

> bash Anaconda2-4.2.0-Linux-x86_64.sh

To change the default work environment to normal python, I update .bashrc file

> mv .bashrc .bashrc-anaconda
> mv .bashrc-anaconda.bak . bashrc

Everytime when I need setup anaconda environment, I need to run the following command

> source ~/.bashrc-anaconda

## Tensorflow under anaconda2
Install tensorflow under anaconda2 directly, do not create seperate envionrment

> export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.11.0-cp27-none-linux_x86_64.whl
> pip install --upgrade $TF_BINARY_URL

## Anaconda virtual env

Anaonda , Python 2.7
> conda create -n <virtual env name> python=2.7
> source activate <virtual env name>

> source deactivate

Note: Virtual environment is under anaconda2/envs/
To remove the virtual environment, just remove the folder under anaconda2/envs

# Tensorflow installation
For none-jupyter notebook case use, virtualenv, python 2.7

> export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.11.0-cp27-none-linux_x86_64.whl
> pip install --upgrade $TF_BINARY_URL


# Reference

## About Anaconda and tensorflow environment

[Original Post](http://stackoverflow.com/questions/37061089/trouble-with-tensorflow-in-jupyter-notebook)

To use tensorflow in Ipython and/or Jupyter(Ipython) Notebook, you'll need to install Ipython and Jupyter (after installing tensorflow) under the tensorflow activated environment.

Before install Ipython and Jupyter under tensorflow environment, if you do the following commands in terminal:

username$ source activate tensorflow

(tensorflow)username$ which ipython
(tensorflow)username$ /Users/username/anaconda/bin/ipython

(tensorflow)username$ which jupyter
(tensorflow)username$ /Users/username/anaconda/bin/jupyter

(tensorflow)username$ which python
(tensorflow)username$ /User/username//anaconda/envs/tensorflow/bin/python
This is telling you that when you open python from terminal, it is using the one installed in the "environments" where tensorflow is installed. Therefore you can actually import tensorflow successfully. However, if you are trying to run ipython and/or jupyter notebook, these are not installed under the "environments" equipped with tensorflow, hence it has to go back to use the regular environment which has no tensorflow module, hence you get an import error.

You can verify this by listing out the items under envs/tensorflow/bin directory:

(tensorflow) username$ ls /User/username/anaconda/envs/tensorflow/bin/
You will see that there are no "ipython" and/or "jupyer" listing out.

To use tensorflow with Ipython and/or Jupyter notebook, simply install them into the tensorflow environment:

(tensorflow) username$ conda install ipython
(tensorflow) username$ pip install jupyter #(use pip3 for python3)
After installing them, there should be a "jupyer" and a "ipython" show up in the envs/tensorflow/bin/ directory.

Notes: Before trying to import tensorflow module in jupyter notebook, try close the notebook. And "source deactivate tensorflow" first, and then reactivate it ("source activate tensorflow") to make sure things are "on the same page". Then reopen the notebook and try import tensorflow. It should be import successfully (worked on mine at least).
