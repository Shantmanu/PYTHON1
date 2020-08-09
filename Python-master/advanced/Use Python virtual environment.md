The virtual environment of python can provide an independent interpretation environment, dependent packages and other resources for a python project, which can well isolate the conflicts caused by different projects using different python versions, and it can also facilitate the release of the project.

# virtualenv #

[virtualenv](http://pypi.python.org/pypi/virtualenv) can be used to create an independent Python environment, which will create an executable file that contains the necessary requirements for the project.

**Install virtualenv**

```
$ pip install virtualenv
```


**Configure pip to install the mirror source address of the third-party library**

We all know that connecting domestic servers to foreign servers is slow, and sometimes settings downloads often time out. At this time, you can try to use the domestic excellent [douban source] (https://pypi.douban.com/simple) mirror to install.

Install virtualenv using Douban source

```
pip install -i https://pypi.douban.com/simple virtualenv
```

**How ​​to use virtualenv**

The following command means to create a directory (virtual environment) named env in the current directory, which contains an independent Python running program, and a copy of pip to install other packge

```
virtualenv env
```


Of course, you can choose the Python interpreter when creating env, for example:

```
virtualenv -p /usr/local/bin/python3 venv
```

By default, the virtual environment will depend on the site packages in the system environment, which means that third-party packages already installed in the system will also be installed in the virtual environment. If you don’t want to rely on these packages, you can add the parameter `--no- site-packages` establish a virtual environment

```
virtualenv --no-site-packages [virtual environment name]
```

**Start virtual environment**

```
cd ENV
source ./bin/activate
```

Note that there will be an additional `(ENV)` on the command line at this time, ENV is the name of the virtual environment, and all modules will only be installed in this virtual environment.

**Exit the virtual environment**

```
deactivate
```

If you want to delete the virtual environment, just run the `rm -rf venv/` command.

**Install Python packages in a virtual environment**

Virtualenv comes with a pip installation tool, so the packages that need to be installed can be run directly:

```
pip install [package name]
```

# Virtualenvwrapper

Virtualenvwrapper is a virtual environment management tool, it can manage the location of the created virtual environment, and can easily view the name of the virtual environment and switch to the specified virtual environment.


**Install (make sure virtualenv is installed)**

```
pip install virtualenvwrapper
```

Or use Doubanyuan

```
pip install -i https://pypi.douban.com/simple virtualenvwrapper-win
```

Note:

Installation needs to be performed in a non-virtual environment

**Create a virtual machine**

```
mkvirtualenv env
```

After the virtual environment is created, it will automatically switch to the created virtual environment

Of course, you can also specify the python version of the virtual machine

```
mkvirtualenv env -p C:\python27\python.exe
```

**List a list of virtual environments**

```
workon or lsvirtualenv
```

**Start/switch virtual environment**

Use workon [virtual-name] to switch to the corresponding virtual environment

```
workon [virtual environment name]
```


**Delete virtual environment**

```
rmvirtualenv [virtual environment name]
```

**Leave the virtual environment, the same command as virutalenv**

```
deactivate
```
