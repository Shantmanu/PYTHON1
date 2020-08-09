# 2. Python installation #

Because Python is cross-platform, it can run on Windows, Mac and various Linux/Unix systems. Currently, there are two versions of Python, one is version 2.x and the other is version 3.x, these two versions are incompatible. Bencaogen installs version 3.6.1.

As for where to download, I suggest that you download it directly from the official website, and download the latest version at any time. Official website address: [https://www.python.org/](https://www.python.org/)

## 1. Installation and configuration under windows system##

If it is a windows system, after downloading, install it directly, but remember to check Add Python 3.6 to PATH here, and then click "Install Now" to complete the installation.

Pay attention here. Remember to check "Add Python 3.6 to Path". After you check it, you don't need to configure the environment variables yourself. If you don't check it, you need to configure it manually.

![Pythoninstall.png](http://upload-images.jianshu.io/upload_images/2136918-2bf6591f0a12e80b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

If you are quick and forget to check "Add Python 3.6 to Path", it doesn't matter, you only need to manually configure the environment variables.

Enter on cmd in the command prompt box:

```
path=%path%;C:\Python 
```

Pay special attention to: `C:\Python` is the installation directory of Python. If your installation directory is elsewhere, you have to fill in your corresponding directory.

After the installation is complete, open the command prompt window and type python, the following situation appears, which proves that the Python installation is successful.

![Run python.png](http://upload-images.jianshu.io/upload_images/2136918-817c22f802e8cfce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

And when you see the prompt `>>>`, it means that we are already in the Python interactive environment. You can enter any Python code, and you will get the execution result immediately after pressing Enter.


## 2. Installation and configuration under Mac system##

MAC systems generally have their own Python 2.x version of the environment, but the 2.x version is not used now, so it is recommended that you download the latest version from https://www.python.org/downloads/mac-osx/ and install it .

After installation, how to configure environment variables?

First check the current environment variables:

``` 
echo $PATH
```

Then open ``` ~/.bash_profile (no, please create new) ```

``` 
vi ~/.bash_profile
``` 

I installed Python 3.7, and the Python execution path is: `/Library/Frameworks/Python. Framework/Versions/3.7/bin`. So write

```
export PATH="/Library/Frameworks/Python. Framework/Versions/3.7/bin:$PATH"
```

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-07-22-084149.png)

Finally save and exit, activate and run the following file:

```
source ~/.bash_profile
```
 





