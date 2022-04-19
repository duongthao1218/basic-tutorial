## View a list of all Python binaries installed on your system
```
ls -l /usr/bin/python*
```
## Check location installed
```
which python3.5
```
## Uninstall
```
rm -Rf /usr/local/bin/python3.5 
```

## Steps to install Python3.7 and configure it as the default interpreter.

- step1: `sudo apt-get install python3.7 && sudo apt-get install python3-pip` 

- step2: Add Python3.6 & Python 3.7 to update-alternatives
```
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.6 1
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.7 2
```
- step3: Update Python 3 to point to Python 3.7

- step4: `sudo update-alternatives --config python3` Enter 2 for Python 3.7

- step5: check `python3 --version`

