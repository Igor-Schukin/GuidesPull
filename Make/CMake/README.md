# All about CMake  
<img src="https://imgur.com/9tM2lUn.png"></img> 

## About  

Система сборки CMake представляет из себя оболочку над другими платформенно зависимыми утилитами (например, Ninja или Make). Таким образом, в самом процессе сборки, как бы парадоксально это ни звучало, она непосредственного участия не принимает.  
  
Система сборки CMake принимает на вход файл CMakeLists.txt с описанием правил сборки на формальном языке CMake, а затем генерирует промежуточные и нативные файлы сборки в том же каталоге, принятых на Вашей платформе.  

Сгенерированные файлы будут содержать конкретные названия системных утилит, директорий и компиляторов, в то время как команды CMake орудуют лишь абстрактным понятием компилятора и не привязаны к платформенно зависимым инструментам, сильно различающихся на разных операционных системах.  

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
Create in project dir ***build*** and ***cd*** into it. After use this commands:    
This command is  for configuring cmake to your system(compilator version, linker,cXX standart ETC)(Only need do it once)(***NEED TO BE IN "BUILD" DIR!!!***)  
```shell
$ cmake ..
```  
  To build/rebuild your project(again you must be inside ***build*** dir)(this commands build your project and "drops" cmake files(dependecnies. makefile e.tc) into build dir)  
```shell  
$ cmake build .
```  
After you can just use this command if you added new stuff into project(again must be inside ***build*** dir of your project)  
```shell  
$ make
```

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
[Instalaltion/updating/purging CMake | ](https://askubuntu.com/questions/355565/how-do-i-install-the-latest-version-of-cmake-from-the-command-line)[Сыль на Хабр о CMake | ](https://habr.com/ru/post/432096/)  
