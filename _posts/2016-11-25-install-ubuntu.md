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


