# Python virtual environment setup <!-- omit from toc -->

**Table of Contents**
- [Virtual Environment using CMD](#virtual-environment-using-cmd)
  - [`where python`](#where-python)
  - [Basic pip](#basic-pip)
    - [`pip help`](#pip-help)
    - [`pip help [specific-command]`](#pip-help-specific-command)
    - [`pip list`](#pip-list)
  - [Creating virtual environment](#creating-virtual-environment)
  - [With specific python version](#with-specific-python-version)
- [Virtual Environment using VS Code](#virtual-environment-using-vs-code)
- [References](#references)



## Virtual Environment using CMD

### `where python`
-   Gives the path of the python installation 

### Basic pip
#### `pip help`
-	Displays a summary of pip commands
#### `pip help [specific-command]`
-	Displays details for the command
#### `pip list` 
-	Displays list of all python packages installed 

### Creating virtual environment
1. Step 01: Change directory to project folder
2. Step 02: Create virtual environment
3. Step 03: Activate it
4. Step 04: Install required packages
5. Step 05: Save installed packages or deactivate it


Using **cmd** commands, go to the project folder, where you need to create virtual environment and then write the following
```
python -m venv env-name
python -m venv env-name --system-site-packages	
```
`--system-site-packages` gives access to the system site-packages directory [all system packages] 


Then, you need to activate the newly created virtual environment **env-name** by
```
env-name\Scripts\activate.bat
```

Update the `pip` in the virtual environment:
```
python -m pip install --upgrade pip
```

Now, if you install packages using `pip`, all the packages will be installed only in the virtual environment **env-name**.

To deactivate the current virtual environment, just write the following
```
deactivate
```
	
`pip freeze` prints the list of all python packages installed with their version

You can manually copy the output and make a *requirements.txt* file. So that you can recreate the same environment on a different location or another device.

You can automate the task by the following command
```
pip freeze > requirements.txt	
```

To recreate the same environment, at first create a new virtual environment, activate it and run the following
```
pip install -r requirements.txt
```
  
### With specific python version

Run venv with a specific python version. You can run using the full path where python is installed.

```
"C:\Program Files\Python38\python.exe" -m venv venv38
```

## Virtual Environment using VS Code
  
We can create a virtual environment similar way explained above using **cmd**.

To select a specific python interpreter, 
1. We need to click **Ctrl** + **P** and then type **>** or **Ctrl** + **Shift**+ **P**
2. Click **Python: Select Interpreter**
3. Select an interpreter displayed or click **+ Enter interpreter path...** and nagivate to the **python.exe** file of a specific virtual environment

## References


[Python Tutorial: VENV (Windows) - How to Use Virtual Environments with the Built-In venv Module](https://www.youtube.com/watch?v=APOPm01BVrk)
