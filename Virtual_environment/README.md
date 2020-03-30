# Make a Package and pip Install Locally 

To make your code a package you need to follow some steps

1. [Place all files in a main folder](#place-files-in-main-folder)
2. [Create file \_\_init_\_.py ](#create-init-file) 
3. [Create setup file](#create-setup-file)
4. [Create Virtual Environment](#create-virtual-environment)
5. [pip Install Package Locally](#pip-install-package-locally)
6. [Run after installation](#run-after-installation)
## Place files in main folder

```
  |__main_folder
    |__distributions
      |__gaussiandistribution.py
      |__generaldistribution.py
      |__example_code.py
```

Place all the .py files in main folder (in my case I placed distributions folder containing all .py files in it) and Add " . "before import name just like </br>
`from .gaussiandistortion import Gaussian` </br>
**Note : " . " not required for python 2.X**

## Create init File
Create a file name \_\_init_\_.py in the distribution folder. This folder shows that the files in this directory is a package. 
The code inside the \_\_init_\_.py file will run when you import a package inside a python program. 
In  my case the \_\_init_\_.py file is importing the gaussian file from gaussiandistribution.py file. 
It is done to directly import the package such as;
```
From distribution import Gaussian 
```
instead of
```
From distribution.Gaussian distribution import Gaussian
```
after this go back to main_folder

## Create setup File
Create setup.py file in main_folder 
```
  |__main_folder
    |_setup.py
    |__distributions
      |__gaussiandistribution.py
      |__generaldistribution.py
      |__example_code.py
```
now we are almost done. Paste this code


```
from setuptools import setup

setup(name='distributions',
      version='0.1',
      description='Gaussian distributions',
      packages=['distributions'],
      zip_safe=False) 

```
This file contain the metadata in that we have name of the package and version. Change this with respect to you folder name (in my case it is distributions)


## Create Virtual Environment
To create the virtual environment just run these command in the terminal of the main folder. cd to the main folder then use the first command to create virtual environment (change the name as per your choice in my case it is environmentname). 
```
python -m venv environmentname
```
To activate the virtual Env. run the second command

**Note : For windows**

```./environmentname/Scripts/activate```

**Note : For Ubuntu**

```source environmentname/bin/activate```

now if you don't get any errors it means your virtual enviromnent is created successfully.


## pip Install Package Locally 

now run this command in terminal without changing any directory  
```
pip install .
```
(“.” Tells the pip to look for the setup file in the current directory)

if you get some other libraries errors it means these libraries are not installed in your virtual environment, so all you need to do is just pip install all those libraries 

## Run after installation 
To run this first we need to activate the environment from terminal
```
./vironmentname/Scripts/activate

```


