# MAKE Me Baby  
***or You Never Forget The First Time You Got Made***  
An introductory guide of make, and how to write a simple makefile,  
- [What is Make? And Why Should I Care?](#what-is-make-and-why-should-i-care)
- [How to install Make](#how-to-install-make)

## What is Make? And Why Should I Care?  
The tool called Make is a build dependency manager. That is, it takes care of knowing what commands need to be executed in what order to take your software project from a collection of source files, object files, libraries, headers, etc., etc.---some of which may have changed recently---and turning them into a correct up-to-date version of the program.  
## How to install Make  
A way to install gcc compiler is to install it as part of build-essential package. ***Build-essential package*** will also install additional libraries as well as ***g++*** compiler for Makefile. In most cases or if unsure this is exactly what you need: 
```shell  
$ sudo apt install build-essential
```  
Confirm your installation by checking for GCC version: 
```shell  
$ gcc --version
```
