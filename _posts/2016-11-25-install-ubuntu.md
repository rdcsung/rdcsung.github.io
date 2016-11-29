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


# Tensorflow installation
virtualenv, python 2.7

> export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.11.0-cp27-none-linux_x86_64.whl
> pip install --upgrade $TF_BINARY_URL

Anaonda , Python 2.7

> conda create -n tensorflow python=2.7
> source activate tensorflow

> source deactivate
