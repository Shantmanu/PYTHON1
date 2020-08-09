
## Virtualenv

### Introduction

In the process of using `Python` to develop, if there are many projects, it is inevitable that different projects rely on different versions of libraries; or in the development process, you don’t want to flood the physical environment with a variety of libraries. Future dependent disasters.

Therefore, we need to use different virtual environments for different projects to keep the development environment and host environment clean. And `virtualenv` is an excellent tool that can help us manage different `Python` environments. `virtualenv` can create multiple different virtual environments in the system that do not interfere with each other.

### Installation

```
 pip3 install virtualenv
```

So it succeeded

### Use

#### Create

If we want to use `scrapy` to crawl information of a certain website, and we don't want to install scrapy and requests packages in the host environment, then we can use virtualenv.

Suppose we put this virtual environment in the `~/workspaces/project_env/spider/` directory

```
 virtualenv ~/workspaces/project_env/spider/
```

In this way, the virtual environment is created, and we can see that three directories are created under this directory

* bin: contains some commands available in this virtual environment, and the script `activate` to open the virtual environment
* include: include header files in the virtual environment, including `Python` header files
* lib: there are some dependent libraries

#### Activate

```
 source ~/workspaces/project_env/spider/bin/activate
```

At this point we are already in the virtual environment

You can install the requests module

```
 pip install requests
```

You can see that it will succeed soon

#### Exit the virtual environment

```
 deactivate
```

## virtualenvwrapper

### Introduction

We just learned about `virtualenv`, I think it is more troublesome, every time you open the virtual environment, you have to go to the `source` under the `bin` directory under the directory where the virtual environment is located and click `activate`, which requires us to remember each virtual environment The directory where it is located.

A feasible solution is to centralize all virtual environment directories, for example, put them in `~/virtualenvs/`, and use different directories to manage different virtual environments. `virtualenvwrapper` does exactly this. Moreover, it saves the `source` operation every time the virtual environment is turned on, making the virtual environment more usable.

### Installation

```
 pip install virtualwrapper
```

In this way, we have installed the artifact that can manage the virtual environment

### Use

#### Configuration

First you need to configure `virtualenvwrapper`:

* Need to specify an environment variable called `WORKON_HOME`, which is used to store various virtual environment directories
* Need to export vitualenvwrapper this module storage location
* Need to run its initialization tool `virtualenvwrapper.sh`, you can check the location through `which virtualenvwrapper.sh`, mine is in `/usr/local/bin/`

Since these two steps need to be performed each time, we can write them into the configuration file of the terminal.

If you use `bash`, add it to `~/.bashrc`

If you use `zsh`, add it to `~/.zshrc`

In this way, it will run automatically every time you start the terminal. After the terminal is started, `virtualenvwrapper` can be used.

```
 export WORKON_HOME='~/Workspaces/Envs'

 export VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3

 source /usr/local/bin/virtualenvwrapper.sh
```


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
