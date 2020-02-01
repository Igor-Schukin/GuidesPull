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

### VSCODE part 
VSCODE->extensions-> install extensions "CMake(from Microsoft)" and "CMake tools(for intelsens in )"   

## Installation Under Windows and MVS  
## How to use in VSCode  
## How to use in MVS  
## How to delete/update CMake
## Sources
[Instalaltion/updating/purging CMake | ](https://askubuntu.com/questions/355565/how-do-i-install-the-latest-version-of-cmake-from-the-command-line)  
