# cv-ai4all-michigan
Computer Vision Project for AI4All at Michigan, 2019.
Adapted from [Computer Vision Project for AI4All at Princeton](https://github.com/lujonathanh/cv-ai4all-pton).

# Installation

## Macbook
```BASH
#IF VIRTUALENV NEEDED: make a virtualenv (https://packaging.python.org/guides/installing-using-pip-and-virtualenv/)
alias python=python3; PYTHONPATH=""
python3 -m pip install --user virtualenv

#IF VIRTUALENV NEEDED:  create the environment in folder "p3env"; change p3env to any path you'd like
VPATH=p3env
python3 -m virtualenv $VPATH
echo 'alias python=python3; PYTHONPATH=""' >> $VPATH/bin/activate
source $VPATH/bin/activate

# clone repo into BASEDIR-- set it to be the base directory of the folder
BASEDIR=
cd $BASEDIR
git clone https://github.com/xcyan/cv-ai4all-michigan.git
cd cv-ai4all-michigan

# install requirements
while read f; do brew install $f; done < requirements.txt

# install python requirements
pip install -r python-requirements.txt

#IF VIRTUALENV NEEDED: install the kernel so that jupyter can find the ipykernel
sudo python -m ipykernel install --user

#IF VIRTUALENV NEEDED: if in virtual environment, deactivate the package
deactivate
```

## Linux
### Install Anaconda
The following script downloads and installls [Anaconda 3.7 for Linux](https://repo.anaconda.com/archive/Anaconda3-2019.03-Linux-x86_64.sh) (Press [Enter] and type in [Yes] in the end):
```
wget https://repo.anaconda.com/archive/Anaconda3-2019.03-Linux-x86_64.sh
bash Anaconda3-2019.03-Linux-x86_64.sh
```
Once you've installed the Anaconda3, please double check if the installation is successful or not.
In the terminal, simply type in the following command line and see if you can see a list of installed libraries.
```
conda list
```
Also, please check the installed path by the following command line.
```
which conda
```
Create the ```bash_profile``` and add anaconda installed path (by removing the ```/bin/conda```).
```
vim ~/.bash_profile
```
Here is an example of ```bash_profile``` (please replace $USER_ID$ with the real path on your local machine):
```
ANACONDA_PATH=/home/$USER_ID$/anaconda3
export PATH=$ANACONDA_PATH/bin:$PATH
export LD_LIBRARY_PATH=$ANACONDA_PATH/lib:$LD_LIBRARY_PATH
export LIBRARY_PATH=$ANACONDA_PATH/lib:$LIBRARY_PATH
export C_INCLUDE_PATH=$ANACONDA_PATH/include:$C_INCLUDE_PATH
export CPLUS_INCLUDE_PATH=$ANACONDA_PATH/include:$CPLUS_INCLUDE_PATH
```
In the ```vim``` environment, type ```i``` for the insert mode and type ```:wq``` when you are done.
Please check this link for [detailed usage guide to vim](https://www.howtoforge.com/vim-basics).

As a final step, activate anaconda by typing the following command line in the terminal.
```
source ~/.bash_profile
```

### Install Python Library Dependencies
```BASH
#IF VIRTUALENV NEEDED: make a virtualenv (https://packaging.python.org/guides/installing-using-pip-and-virtualenv/)
python -m pip install --user virtualenv

#IF VIRTUALENV NEEDED:  create the environment in folder "p3env"; change p3env to any path you'd like
VPATH=p3env
python -m virtualenv $VPATH
source $VPATH/bin/activate

# clone repo into BASEDIR-- set it to be the base directory of the folder
BASEDIR=
cd $BASEDIR
git clone https://github.com/xcyan/cv-ai4all-michigan.git
cd cv-ai4all-michigan

# install requirements
while read f; do conda install $f; done < requirements.txt

# install python requirements
pip install -r python-requirements.txt

#IF VIRTUALENV NEEDED: install the kernel so that jupyter can find the ipykernel
python -m ipykernel install --user

#IF VIRTUALENV NEEDED: if in virtual environment, deactivate the package
deactivate
```

## Windows
```
TBD
```

# Jupyter Notebook
## Lanuch Juypter Notebook
Type the following command line in the terminal and you will see the interface in the web browser.
```
jupyter notebook
```
