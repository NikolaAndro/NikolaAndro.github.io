---
layout: post
title:  "Python Virtual Environment"
date:   2021-11-01 09:29:20 +0700
categories: post
---

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Python virtual environment is a self-contained directory tree that includes a Python installation and number of additional packages.

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
The main purpose of Python virtual environments is to create an isolated environment for different Python projects. 
This way you can install a specific version of a module on a per project basis without worrying that it will affect your other Python projects.


### Steps"

1. Install the package that provides the venv module

        sudo apt install python3-venv
        
2. Switch to the directory where you want to create your virtual environment and execute the following command that will create a virual environment called my_project_venv that
will contain a copy of the Python binary, the pip package manager, the standard Python library and other packets:

        python3 -m venv my_project_venv

3. To start using this environment, run the activate script:

        source my_project_venv/bin/activate
        
4. Once you are done with your work to deactivate the environment, simply type deactivate and you will return to your normal shell.

        deactivate

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andrić
 