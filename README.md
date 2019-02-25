# Django Internal Certification | First Steps

**Pre-requisite**

* Have basic knowledge in Python

* Have installed Python 3

For the first steps of this course, it is necessary to setup your own python virtual environment.

**What is a Python Virtual Environment?**

Took from https://realpython.com/python-virtual-environments-a-primer/

Python, like most other modern programming languages, has its own unique way of downloading, storing, and resolving packages (or modules). While this has its advantages, there were some interesting decisions made about package storage and resolution, which has lead to some problems—particularly with how and where packages are stored.

There are a few different locations where these packages can be installed on your system. 

Thus, packages installed using easy_install or pip are typically placed in one of the directories pointed to by site.getsitepackages

import site

print(site.getsitepackages())

Consider the following scenario where you have two projects: ProjectA and ProjectB, both of which have a dependency on the same library, ProjectC. The problem becomes apparent when we start requiring different versions of ProjectC. Maybe ProjectA needs v1.0.0, while ProjectB requires the newer v2.0.0, for example.

This is a real problem for Python since it can’t differentiate between versions in the site-packages directory. So both v1.0.0 and v2.0.0 would reside in the same directory with the same name

Since projects are stored according to just their name, there is no differentiation between versions. Thus, both projects, ProjectA and ProjectB, would be required to use the same version, which is unacceptable in many cases.

This is why virtual environments are needed.

**How to setup your own Python Virtual Environment?**

As we will be using Python 3 for this course, we only will show the way as virtual environments works on it.

To create a virtual environment you should run the next command:

python -m venv <env_folder>

NOTE: Use python3 instead of python if you have both python versions installed. it is very common to call ".env" or "env" to the folder, for this example we will use ".env". Depending of your OS, the folders that will be created inside .env can change.

To activate your virtual environment you should run:

source .env/bin/activate

or for Windows:

source .env/Scripts/activate

You will see (.env) at the beginning of your prompt if you success. That means your virtual environment is active.

NOTE: use "deactivate" command to deactivate your virtual environment.

**How does Python Virtual Environment work?**

After activating the environment, you are now getting a different path for the python executable because, in an active environment, the $PATH environment variable is slightly modified.

**Installing django in your virtual environment**

Once you have your virtual environment active, you should be able to install django on it (without touching your python system packages installations)

To install packages you should be able to run: "pip install <package list>", for this specific course we already have a requirements.txt file with the packages needed. To install files from a requirements file, you should run:

pip install -r requirements.txt

After installation is completed you should be able to run "pip freeze" to check all the packages installed. For now you should only see:

Django==2.1.7 and pytz==2018.9

**Django first project**