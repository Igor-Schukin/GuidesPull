# Pull for Raspberry stuff  
INstallation,update,modification e.t.c    
<img src="https://imgur.com/gJXWkhH.png" width="60%"></img>  

- [Installation of Raspbian OS](#installation-of-raspbian-os)
- [Trouble Fix](#trouble-fix)

## Installation of Raspbian OS    
How to install Raspbian OS   
   
 ***Needed stuff for installation:***  
 * Raspberry Pi
* SD card (8+ GB preferable)
* ethernet connection for (for updates ant e.t.c) 
* SD card reader(where to plug sd card)   

***STEPS:***  
1) Download [Noob archive](https://www.raspberrypi.org/downloads/)  
2) set up a blank SD card   
  2.1) Format an SD card.Use [this](https://www.sdcard.org/downloads/formatter/) tool if you are using windows  
3) extract the files from the NOOBS zip file  
4) Copy the extracted files onto the SD card that you just formatted  
5)Plug ethernet cable into Raspberry Pi
6) Plug the sd card into your Raspberry PI ant turn it on Must pop up this 
<img src="https://imgur.com/czQ1rGS.png" width="90%"></img>  
9) Check only what is in the green circle(***it will install Lite version of debian without pre installed python,Wolfram and other useless junk***) or just do not touch anything    
10) Press install button  
11)After installation configure Raspberry(set your username,password e.t.c)  
12)Prepere smiling thru Pain using Raspberry PI as PC where your IDE will be installed and  
<img src="https://imgur.com/j17nYAe.png" width="90%"></img>   

## Trouble Fix  
here are stored ways of fixing some errors what can appier working withPi  
if you have this error:  
```  
oglinit: Assertion `state->surface != EGL_NO_SURFACE' failed 
```  
when it means you need to make Raspberry Pi gpu memmory bigger(be awere rising memory for gpu slows down Pi)  
first of all check how much memory you have for GPU  
```shell  
$ vcgencmd get_mem gpu
```  
second rise it(i rised to 128 MB GPU memory but i had 1gb RAM):  
* using GUI:  
[Menu] --> [Preferences] --> [Raspberry pi config..] --> [Performance]  
* using config.txt.  
By direct edit of /boot/config.txt  
```shell  
$ sudo nano /boot/config.txt
```  
If a gpu_mem command exists then change it to 128 if not there then add the line at the end  
```  
gpu_mem=128
```  

Topic sources  
[about memmory of Raspby official](https://www.raspberrypi.org/documentation/configuration/config-txt/memory.md)[How to fix problem page on forum](https://www.raspberrypi.org/forums/viewtopic.php?t=190182)  

Sources:  
[NOOBS | ](https://www.raspberrypi.org/documentation/installation/noobs.md)[#1 | ](https://www.raspberrypi.org/downloads/)[#2 | ](https://www.raspberrypi.org/downloads/raspbian/)[Forum | ](https://www.raspberrypi.org/forums/)  
[old image](https://imgur.com/7RMisud.png)
