# All about CMake  
<img src="https://imgur.com/9tM2lUn.png"></img> 

## About  
CMake is an open-source, cross-platform family of tools designed to build, test and package software. CMake is used to control the software compilation process using simple platform and compiler independent configuration files, and generate native makefiles and workspaces that can be used in the compiler environment of your choice. The suite of CMake tools were created by Kitware in response to the need for a powerful, cross-platform build environment for open-source projects such as ITK and VTK.  
  

## Installation Under Linux and  VSCode  
A way to install gcc compiler is to install it as part of build-essential package. ***Build-essential package*** will also install additional libraries as well as ***g++*** compiler for Makefile. In most cases or if unsure this is exactly what you need: 
```shell  
$ sudo apt install build-essential
```  
Confirm your installation by checking for GCC version: 
```shell  
$ gcc --version
```  
Well one of the methods are to run sudo-apt(btw repository can be not updated to newest version of CMake) or use [alternative method](https://cmake.org/install/) 

```shell  
$ sudo apt-get install cmake
```
After the software is successfully installed, you can verify its installation and also if the correct version is installed, through the following command:  
```shell  
$ cmake --version
```
### VSCODE part 
VSCODE->extensions-> install extensions "CMake(from Microsoft)" and "CMake tools(for intelsens in )"   

## Installation Under Windows and MVS  
in VS installer  
<img src="https://imgur.com/E8mP68t.jpeg" width="90%"></img>   
1)Start->Visual Studio installer  
    
	2)"in Installed page"   
		  more->modify  
        
	3)in "WORKLOADS"  
		scroll down and press on "Linux development with C++"  
      
	4)press "modify" button
    
	5)???  
    
	6)PROFIT!!!    
  
## How to use in VSCode  
***For new project***              
Create new folder(where project will be stored) and open that folder with VSCode/  
Press ***Ctrl+Shift+p*** and chose Quick Cmake
## How to use in MVS  
***How to create new project***  
MVS->New Project
<img src="https://imgur.com/uymWV3r.jpeg" width="90%"></img>   
## How to delete/update CMake  
Uninstall just cmake:  
```shell  
$ sudo apt-get remove cmake
```
Uninstall cmake and its dependencies  
```shell  
$ sudo apt-get remove --auto-remove cmake
```
Caution! Purged config/data can not be restored by reinstalling the package.
Purging your config/data(not needed):  
```shell  
$ sudo apt-get purge --auto-remove cmake
```
[Check this article for update and delete CMake](https://askubuntu.com/questions/355565/how-do-i-install-the-latest-version-of-cmake-from-the-command-line)  
## Sources
[Instalaltion/updating/purging CMake | ](https://askubuntu.com/questions/355565/how-do-i-install-the-latest-version-of-cmake-from-the-command-line)  
