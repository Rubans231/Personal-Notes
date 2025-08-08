
2025-08-08 11:46

Status:

Tags: [[coding]] [[python]] 


## Important note

>- Make sure to update source control to prevent committing your virtual environment since virtual environments are not portable 

# Virtual environments in VScode

>- venv allows to manage separate package installations for different projects(can also be done with conda)
>- installed by default with python3(Debian-based OS requires a manual install)
>- Press Ctrl+shift+P and search "Python: Create environment"
>- Then it presents a list of interpreters
>- if venv, choose a specific python interpreter version
>- conda presents a similar list to venv mentioned above

# Virtual environments in the terminal:

>- use the command (where ".venv") to find name of the environment folder
>- 
`# macOS/Linux
`# may need to run sudo apt-get install python3-venv first on Debian based OS
`python3 -m venv .venv`
>
>`# Windows`
>`You can use py -3 -m venv .venv`
>`python -m venv .venv`

# Conda environment in the terminal

>- python extension auto detects existing conda environments
>- `coonda create -n env-01 python=3.9 scipy=0.15.0 numpy`
>- the above code creates a conda environment with a python 3.9 interpreter and several libraries
>- Though there is no direct integration in VS code for environment.yml files, VS code itself is a great YAML editor







# References