# PYTHON

## VENV
###### Create
`$ python3 -m venv ~/.virtualenvs/resize_photo`

####

## PIP
###### Install
for python3.xx:
`$ sudo apt-get install python3-pip`

###### BROKEN PIP, SOLUTION LINK:
https://stackoverflow.com/questions/28917534/pip-broken-on-ubuntu-14-4-after-package-upgrade/28919613#28919613

`$ sudo apt-get remove --purge python-pip`
`$ curl https://bootstrap.pypa.io/get-pip.py | sudo python3`

###### PIP LIST down all installed libraries
`$ pip list`

`$ pip freeze`
##

## INSTALL AND SETUP LATEST PYTHON 

https://opensource.com/article/20/4/install-python-linux

###### LINK
https://www.itsupportwale.com/blog/how-to-upgrade-to-python-3-10-on-ubuntu-18-04-and-20-04-lts/


###### To see what current used version:
`$ python3 -V`

###### Adding repo:
```
$ sudo add-apt-repository ppa:deadsnakes/ppa
$ sudo apt-get update
```

###### Checking available package:
`$ sudo apt list | grep python3.10`

###### Install:
`$ sudo apt-get install python3.10`

###### Setting up versions:
```
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 2
```

###### Setting default version to be use:
`$ sudo update-alternatives --config python3`

###### To check if succesfully configured
` $ python3 -V`


## 

## Manual Installation
###### Installation Ubuntu
`$ sudo apt-get install python3-venv`

###### Error
```
uls1-user@ubuntu-live-server-1:~/Downloads/Python-3.10.6$ ./configure
checking build system type... x86_64-pc-linux-gnu
checking host system type... x86_64-pc-linux-gnu
checking for python3.10... no
checking for python3... python3
checking for --enable-universalsdk... no
checking for --with-universal-archs... no
checking MACHDEP... "linux"
checking for gcc... no
checking for cc... no
checking for cl.exe... no
configure: error: in `/home/uls1-user/Downloads/Python-3.10.6':
configure: error: no acceptable C compiler found in $PATH
See `config.log' for more details
```
Solution
https://opensource.com/article/20/4/install-python-linux

Use this:
`$ apt-get install build-essential`

dpkg error? do this: 
https://itsfoss.com/could-not-get-lock-error/
`$ sudo dpkg --configure -a`

##

## No module named apt_pkg
On Ubuntu 18.04, 
use this 
$ cd /usr/lib/python3/dist-packages
$ sudo cp apt_pkg.cpython-36m-x86_64-linux-gnu.so apt_pkg.so

Naren Yellavula
 May 13, 2019 at 14:31

##

## 
######
ERROR: This script does not work on Python 3.6 The minimum supported Python version is 3.7. Please use https://bootstrap.pypa.io/pip/3.6/get-pip.py instead.

##

## Workflow: From history on how to set up an updated python version:
###### The link: 
https://cloudbytes.dev/snippets/upgrade-python-to-latest-version-on-ubuntu-linux

###### 1 Update
`$ sudo apt-get upgrade && sudo apt-get update`

###### 2 Check Version
```
$ python -V
$ python3 -V
```

###### 3 Installation
```
$ sudo apt-get install software-properties-common
$ sudo add-apt-repository ppa:deadsnakes/ppa
$ sudo apt-get install python3.10
```

###### 4 Uninstall current Pip
`$ sudo apt-get remove python3-pip`

###### 5 To see all current installed python versions
`$ ls /usr/bin/ | grep python`

###### 6 Adding each versions to use python3 command
```
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
$ sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 2
```

###### 7 To pick which version will be used
`$ sudo update-alternatives --config python3` 

Then check version:
`$ python3 -V`

###### 8 Adding each versions to use python command
`$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.10 1`

###### 9 To pick which version will be used
`$ sudo update-alternatives --config python`

Then check the version:
`$ python -V`

###### 10 To make sure all pip and it's dependecies are cleared from the system
```
sudo apt-get remove --purge python3-apt python3-pip 
sudo apt-get autoclean 
```

better not to use this:
`$ sudo apt-get autoremove`

###### 11 Install pip
```
$ sudo apt-get install python3-apt
$ sudo apt-get install python3.10-distutils 
$ cd ~/Downloads/

$ curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
$ sudo python3 get-pip.py 
```

To test:
`$ pip`

###### 12 To see if the setup is correct 
```
which pip
which python
which python3
```

###### 13 Install venv
`$ sudo apt-get install python3.10-venv`

###### 14 Also test creating virtual environment if it using the correct versions
```
$ python3 -m venv path/of/dir/alpha-venv/
$ source path/of/dir/alpha-venv/bin/activate
```

Then test:
```
$ which pip
$ which python
$ which python3
```

##

## Youtube Downloader
######  Alternative Installation for UBUNTU
```
sudo apt purge youtube-dl 
sudo pip3 install youtube-dl
hash youtube-dl
```

##
