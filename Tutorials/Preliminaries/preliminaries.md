# Preliminaries

In order to do the practical assignments of this course, you need to install some tools on your machine.

## 1. Text Editor for Coding
*(needed from Week 1)*

A good text editor is essential for coding, writing queries and reading files. Since we will be editing in this course RDF files and writing SPARQL queries, it helps if this text editor also supports syntax highlighting for **Turtle** and **SPARQL**.

Example of good text editors: [Notepad++](https://notepad-plus-plus.org), [Sublime](https://sublimetext.com), or [ViM](https://www.vim.org).


## 2. Python
*(needed from Week 1)*

A working version of Python is needed for this course, preferably somewhat close to version 3.10 for your platform of choice.

### - *How to install Python?*

We provide some installation instructions for the three major operating systems: Linux, OS X, and Windows. This short tutorial is copied from the [Python-Installation-Tutorial](https://github.com/purcellconsult/Python-Installation-Tutorial) by [purcellconsult](https://github.com/purcellconsult).


#### 2.1. Install Python on Linux (Ubuntu)

To see if Python is installed on your machine open up the terminal and type in the following:

    python

The output should look something like the following:

    Python X.XX |Anaconda, Inc.| (default, ...)
    [GCC 7.2.0] on linux
    Type "help", "copyright", "credits" or "license" for more information.

Look at this line of output:

    Python X.XX |Anaconda, Inc.| (default, ...)

If you got something like this then Python is installed on your machine. If Python 2.7 or later is installed then it's OK, you don't need to uninstall it, you just need to get Python3 running. Luckily this process is super easy with Ubuntu:

 - Step one: Open up the terminal by pressing `ctr + alt + t`
 - Step two: Type `sudo apt-get update`
 - Step three: Type `sudo apt-get install python3`

The word sudo is abbreviation for "super user do" and it allows programs to be executed as a super user, aka the root user. The apt command means Advanced Package Tool, which is a package manager for Debian based operating systems like Ubuntu. The apt-get command is the APT package handling utility. You can see a list of the commands that's available for it by typing apt-get into the terminal.

#### 2.2. Install Python on OS X (Mac)

Like Linux, Python is already installed on a variety of OS X systems. You can confirm that Python is installed by going to: *Applications → Utilities → Terminal*.  Next, type the following into the terminal:

    python -V

The command will output the version of Python, e.g.:

    Python 2.7.3

Any version between 2.7.0 and 2.7.10 is common. The next step is to test if you have Python3 on your computer. You can do this by typing the following into the terminal:

    python3

If the output shows that Python 3 is installed then you're safe... for now. If you get an error then that's not cool and you have some work to do. You can fix this by downloading and installing Python with the [appropriate Mac OS X installer](https://www.python.org/downloads) that matches your system.

#### 2.3. Install Python on Windows

It's a high probability that if you're running a Windows operating system then Python won't be there by default. To discover if Python is installed on your machine you can open the terminal and then type python. If it's installed then that command will run *python.exe* and reveal the version number. If you get a rude message like the following:

    'python' is not recognized as an internal or external command, operable program or batch file

This tells you that Python is not installed and you have to set it up. Follow the steps below to install and setup Python on your computer.

**Step one**: Download the [latest version of Python](https://www.python.org/downloads) on your machine:  

**Step two**: Open and start the Windows installer that matches your system. If you click "Install Now" then Python is installed in the "user" directory, but if you change its location then make a note of where it's installed.

**Step three**: You'll have an option to add Python to PATH. In layman terms, the PATH is where the computer searches for Python when you type it via command prompt. If you check this box then Python will be available via this option, if not then when you type *python* in the console an error will occur. Therefore, it's a good idea to check this option so that you can type in python commands via command prompt. If you installed Python without selecting this option then no biggie as you have to manually add the path to your system. Here are the steps on how to add Python to the PATH:

  - In the Windows menu search for advanced system settings and select   
   view advanced system settings.
  - In the window that displays click *Environment Variables*.
  - In the next window, find and select the user variable called path and click *Edit*.
  - Scroll to the end of the value and add a semicolon (;) followed by the location of *python.exe*. If you didn't change the default installation location it should be located in your user directory.    
  - Click OK to save the settings

If you don't know the location of python.exe then don't panic, just search for *python.exe* in the Windows menu. Once located, right click the file, select properties, and view the Location. Right click to copy the full path and then paste it at the end of the Path user variable. If you don't have a Path user variable then click the new button, add a variable named Path, and then add the value which is the location or "path" of the python.exe file. Once done type "python" into the terminal to ensure that everything was set up properly and that it runs.

### - *How to run your first Python program?*

Once Python is installed we can test a simple *Hello World* program. Open up a text editor on your operating system (check Section 1.1 of this document). Open up a blank text file and add the following snippet:

    print("Hello World!")

Go ahead and save the file as `HelloWorld.py` to a location of your choice. It can be anywhere, just don't forget where you put it.. The next step is to fire up the terminal or command prompt (if using Windows) and then change into the directory where `HelloWorld.py` is located. To change directories use the cd command. So, if `HelloWorld.py` is in a Programs folder on your Desktop in Ubuntu then it should look something like this:

    cd Desktop/Programs

Once you’re in the directory where your Python file is located the next step is to run the program by using the following command:

    python HelloWorld.py

Python is called an **interpreted language** because the programs can be run directly. The file is still compiled; it's just done internally or behind the scenes and is an implementation detail of the language. This is different from Java which if run through the terminal must be explicitly compiled first, and then the byte code is interpreted by the Java Virtual Machine.

You can also run Python code directly through the shell so that it doesn't have to be added to a file and then run – this is convenient when you want quick feedback and feeling too lazy to type code into a text editor. This is officially known as the *Python Shell* and is what we'll be using to learn the fundamental concepts about Python. You can access the Python Shell by opening up the terminal and typing *python3*.

If all is good then simply type the following into the terminal:

    >>> print("Hello World!")

The output will be:

    Hello World!

### - *How to install packages with Pip? (example: JupyterLab and RDFLib packages)*

Once you got Python installed and tested on your machine then great, you're one step closer to coding in Python. However, this is not the end to all of your installation drama, in matter of fact it's more like the beginning. In the course of your Python learning experience there will be plenty of resources that you'll need to install that's not included with Python by default.

This can be kind of annoying, but the good thing is there's software that helps you install other software. What you'll need is the help of a package manager, and one popular tool for this is *pip*. Depending on what flavor of Python you're running pip should be preinstalled. More specifically, it comes preinstalled on Python 2.7.9 and later, and Python 3.4 and later (pip3).

If you're using an older version of Python I would highly recommend against that as the code crafted in this book is for Python version 3.6+. However, if you insist of using an older version of Python you can follow these two simple steps to installing pip:

1) Download [get-pip.py](https://bootstrap.pypa.io/get-pip.py). Or, you can use curl to download pip by using the following command:  
`curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py`

2) Run `get-pip.py`. You can do this by using the following command:
`python get-pip.py`

That's it! Below are the steps on how you can install pip on OS X and various Linux environments.

### OS X

    sudo easy_install pip

### Debian/Linux

    apt install python3-pip

### Fedora

    dnf install python3

### CentOS

    yum install python-pip

### Pip

Pip is a command line tool, so to install a package for example you just type a command into the terminal. One of the packages you will need in this course is [RDFLib](https://rdflib.readthedocs.io/en/stable/). Here's a quick rundown of some of the key functionality of pip, and how to install these two packages:

    $ pip install rdflib

To uninstall a package use the following command:

    $ pip uninstall rdflib

To upgrade a package do:

    $ pip install --upgrade rdflib

To see a list of packages that's outdated use the following command:

    $ pip list --outdated


## 3. JupyterLab
*(needed starting Week 1)*

Interactive notebooks are simple and effective tools for testing small bits of your code before you integrate it in a larger application. We will use [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html) in this course.

### - *How to install JupyterLab?*

To install JupyterLab using pip, run the following command in a Terminal or the Command Prompt:

    $ pip install jupyterlab


### - *How to open JupyterLab?*

To open JupyterLab, run the following command in a Terminal or the Command Prompt:

    $ jupyter lab

JupyterLab will open automatically in your browser.


## 4. The GraphDB Triple Store
*(needed starting Week 3)*

GraphDB is a reasoning-enabled database for Linked Data and ontologies.

There are two ways to install GraphBB on your machine: either by 1) downloading the software and installing it on your device, or 2) by downloading a Docker image and running the software from a container.

#### Docker Container

Please follow these steps to run GraphDB from a container:

1. Download the tar file with the build script [here](https://surfdrive.surf.nl/files/index.php/s/jtoL0nnuox3Jjpv).
2. Extract the tar file in a new directory with `tar xf myTarFile.tar` or using a tool such as [7zip](https://www.7-zip.org/download.html).
3. Generate the GraphDB image as described in the supplied README file.
4. Start the container.

#### Manual Installation

Please follow these 5 simple steps to download and install GraphDB directly on your machine:

1. Open <https://ontotext.com/products/graphdb/graphdb-free/> in your browser
2. Fill in your information and provide a valid email address (e.g. your VU email address)
3. In less than 5 minutes, you should receive an email from the GraphDB team with a link for download (it is very probable that this email will end up in your SPAM/JUNK folder)
4. Choose the Operating System of your choice (Windows, Mac, deb based Linux, rpm based Linux)
5. Install GraphDB

## 5. The Protégé Ontology Editor
*(needed starting Week 4)*

There are several RDF and OWL editors that you could use (apart from your favourite text-based editor). The main contenders are [Protégé](http://protege.stanford.edu) and [TopBraid Composer](http://www.topquadrant.com/downloads/topbraid-composer-install/).

We advise you to use Protégé for the assignments in Week 3.

* Protégé is a stand-alone editor that is very much tailored towards OWL ontology editing.
* It allows you to define OWL axioms using an abstract syntax (Manchester Syntax),
* But it is less transparent if you're interested in knowing what the syntactic RDF representation looks like. This may lead to confusing situations where it is unclear e.g. in what namespace you have defined your classes, instances, etc.  
* Protégé does support all major OWL2 DL reasoners (Fact++, Hermit and Pellet) and is thus quite powerful with respect to inferencing.

### - *How to install Protégé?*

Depending on your operating system, check the [installation tutorial](http://protegeproject.github.io/protege/installation/) on the Protégé website.
