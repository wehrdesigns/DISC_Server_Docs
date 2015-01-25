
Software Installation and Setup
==============================================

Prerequisites - a list of the required software and versions that have been tested. 
-----------------------------------------------------------------------------------
Installation
^^^^^^^^^^^^
*(Other versions may work, but have not been tried.)*

Ask Google how to best install this software on your system.
Pip is a good python tool to install packages.
If you already have other versions installed, consider using a python virtual environment (linux only).

*   Python      2.7.6
*   Django      1.7
*   Tornado     3.1
*   Numpy       1.6.2
*   Matplotlib  1.1.1
*   pySerial    2.5

Check the installation
^^^^^^^^^^^^^^^^^^^^^^
*Run python in a terminal*::
    
    python
    
*Then type or copy/paste (one line at a time) the following into the terminal to see if each item is installed and which version is installed*::

    import sys
    sys.version
    import numpy
    numpy.__version__
    import django
    django.get_version()
    import matplotlib
    matplotlib.__version__
    import tornado
    tornado.version_info
    import serial
    serial.VERSION
    
*To exit python type*::
    
    quit()

DISC Server
-----------
Download
^^^^^^^^
Download the software from github

Installation
^^^^^^^^^^^^
The software can be located on the local drive or a usb flash drive or a network drive

Setup
^^^^^
The software is preconfigured with a simple demo.  You can run the demo to get familiar with the system or you can skip ahead to create a custom configuration.

Custom Configuration
""""""""""""""""""""
The core django app in the disc server is the 'env' app.  In order to build a new database for the env app, follow the directions in the django online tutorial.
