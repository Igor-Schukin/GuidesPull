
# Guides for remote Linux Project
- [WHY?!](#why)
- [Remote Linux project from Linux](#remote-linux-project-from-linux)
- [Remote Linux project from Windows(Visual Studio)](#remote-linux-project-from-windows)
  - [What do you need to start:](#what-do-you-need-to-start)
  - [VS configuration part](#vs-configuration-part)
  - [Test project  ](#test-project)
- [Source list](#source-list)

## Why  
 Problem appiered when you start using Raspberry Pi as IDE .Its TOO SLOW!. In Raspbians VScode you do not have Intelsens(auto complite line.shows methodds of the class e.t.c), Debugger. This topic was created to solve this problems using remote build options in Visual studio or in VSCODE in the remote machines. where Raspberry PI will be used as compiler of programm.  
## Remote Linux project from Linux
//here The lone and level sands stretch far away...
## Remote Linux project from Windows
### What do you need to start
* N Straigth arms
* Pluged on Raspbbery and Enabled SSH   
    Start->Preferences->Raspberry Pi Configuration->Interfaces->["Enable SSH."](https://imgur.com/Qtg2m7v)
* Raspberry Pi hostname  
     Use this command in console to [get hostname: ](https://imgur.com/6urxqFa) 
     ```shell
     $ hostname -I
     ```
* crap what must be installed on Linux machine  
    command for installation:  
    ```shell
    $ sudo apt-get install openssh-server g++ gdb gdbserver
    ```
* [Installed Putty](https://www.putty.org/) on Windows  
* Obviosly installed MVS on Windows with Linux package  
in VS installer  
<img src="https://imgur.com/E8mP68t.jpeg" width="90%"></img>   
    	If needed install it  
	1)Start->Visual Studio installer  
    
	2)"in Installed page"   
		  more->modify  
        
	3)in "WORKLOADS"  
		scroll down and press on "Linux development with C++"  
      
	4)press "modify" button
    
	5)???  
    
	6)PROFIT!!!  
    
  

### VS configuration part
  1)Open MVS and chose "***Create new project***"  

 2)Chose "***Makefile Project***" if you havent it back to "***What do you need to start"*** ****punkt 6*** 

3)Write path where to store it on your machine  

  _*MVS migth show you pop out window where you need to enter Linux device info(hostname,user,password etc) fill it with info if it did not appiered its ok!_  
  4)***Connect your Linux machine to MVS:***  
  	In projec:Tools->Options->Cross Platform->press "Add button" fill pop out window with needed info(hostname,username e.t.c)  
	<img src="https://imgur.com/AkqclFk.jpeg" width="90%"></img>  
5)***Configure project to understand make for Make***  
	5.1)***Project type:***  
   		Project->$(Your project name)Properties..->General  
		Configuration Type->Makefile  
		<img src="https://imgur.com/v2Eol9F.jpeg" width="90%"></img>   
	5.2)***For compilator to understand***  
		Project->$(Your project name)Properties..->Remote Build  
		<img src="https://imgur.com/2rZ0yjd.jpeg" width="90%"></img>   
	5.3)***For Debuging***  
		Project->$(Your project name)Properties->Debugging   
		  Program->$(FULL_PATH_TO_EXE)/$(EXE_NAME)  
		<img src="https://imgur.com/49yik2S.jpeg" width="90%"></img> 
### Test project  
Create Source.cpp file in VS (it can be with different name I used this for guides purpose)
	in Source.cpp paste this code:  

```cpp
#include <iostream> 
	
int main(){  
	
	std::cout << "HELLO WORLD I AM ALIVE!@\n";  
	
	return 0;  
}
```
	
Create ***simple Makefile*** in project folder:  
```Makefile
#Something like that
	CC= g++ -g -Wall
	#compiling project and linking
	Hello:Source.o
		$(CC) -o $@ Source.cpp
	#command what allows you to delete obj files by using this command-> make clean
	.PHONY:clean
	clean:
		-rm *.o
```
   
   FINNALY PRESS CTRL+F5 then thru putty open yours project folder in linux machine and type this in console   
   ```
   $ ./$(Your project name.exe)  
   ```  

![wow](https://github.com/RazdolbayOne/GuidesPull/blob/master/Tunning%20MVS%20for%20remote%20linux%20projects/img/udivlenie.jpg)
  
## Source list  
### ENG
[Microsoft blog | ](https://devblogs.microsoft.com/cppblog/linux-development-with-c-in-visual-studio/)
[More MS blog | ](https://docs.microsoft.com/en-us/cpp/linux/download-install-and-setup-the-linux-development-workload?view=vs-2019)
[Even more MS blog | ](https://marketplace.visualstudio.com/items?itemName=VisualCppDevLabs.VisualCforLinuxDevelopment)  

### RUS
 [Habr | ](https://habr.com/ru/company/microsoft/blog/319962/)
 [ТЫК |](https://habr.com/ru/post/321228/)

 
