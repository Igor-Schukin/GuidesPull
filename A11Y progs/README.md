# Here are stored additionall programs/Guides for SmartRTU  
Programs what are used in smartRTU project how to install them,how to configure them and how to use them......
<img src="https://imgur.com/WNjwgTJ.png"></img>   
- [CutyCapt](#cutycapt)
  - [What do we know about CutyCapt](#цhat-do-we-know-about-cutycapt)
  - [Installation](#installation)
  - [How to use it](#how-to-use-it)
  - [How to use CutyCapt on a Headless server](#how-to-use-cutycapt-on-a-headless-server)
- [VSCode](#vscode)
  - [Installation](#installation)
  - [Configuration](#configuration)
  - [How to start](#how-to-start)
  - [Debuging Makefile Project](#how-to-debug-makefile-project)
  - [BLACK SCREEN FIX](#if-you-have-black-screen-when-you-are-opening-vscode-a-k-a-doomscreen)
- [Midnight Commander](#midnight-commander)
- [FTP_SERVER](#midnight-commander)
  - [Server installation on Linux](#server-installation-on-linux)
  - [Client installation on Linux](#client-on-linux)
  - [Server installation on Windows](#server-installation-on-win)
  - [Client installation on Windows](#client-on-windows)
- [Sources](#sources)
## CutyCapt  
CutyCapt is comand line converter from ***HTML to image.***  
Support formats for img ->***SVG, PDF, PS, PNG, JPEG, TIFF, GIF***  
btw have support of javascript. 
### What do we know about CutyCapt  
* Support formats for output img ->***SVG, PDF, PS, PNG, JPEG, TIFF, GIF***  
* Can transform html page using url to web page on distant server  
* Can transform html page using url on local html file in system  
* Can't set output image const size, but it can be changed if in source html file (inside style tag )  create container tag and set to const size,
wraping all of webpage content in it :   
```html  
#container{
          /*Styling for any element with the id="container" */
          /*Output image will be 1920x1080 */

					 width:1912px;  /* -8 px from neede width */
           height:1032px; /*-48px from needed height*/
            }
```  
Example of webpage  
```html  
<!Doctype HTML>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<title>fixed layout</title>
		<style>
			
			/* This is a comment it is not read by any browser
			This is where the css styling goes */
		
			body{
			color:#000;
			background-image: url('img/seaEdgeHD.png');
			}
			
      /*Styling for any element with the id="container" */
			#container{
			width:1912px; /* -8 px from neede width */
			height:1032px ;/*-48px from needed height*/
            }
			h1 {text-align: center;}
			p {text-align: center;}
		</style>
	</head>
	<body>
    /* Cutycapt output image will be 1920x1080 if content is wrapped around id="container", otherwise undefined sizes*/
		<div id="container">
			<h1 style="font-size:60px">Sveiciens visiem no karantīna atnākušiem  </h1>
			<p id="content" style="font-size:80px"> ESMU ES Kaut kads teksts kuram nav jēgas</p>
			<img src="img/LermDoneBB2.png" alt="SlinkisStudents"  style='position:absolute; bottom:0; left:0;' width='450' height='450' alt='' />
		</div>
	</body>
</html>
```  
* More info about what command args are for CutyCapt are :  
```shell  
$ cutycapt --help
```  
  
Kinda have version of [cutycapt with transperent background](https://github.com/RazdolbayOne/GuidesPull/blob/master/A11Y%20progs/CutyCapt/CutyCapt-master.7z) but it must be compiled and tested  
### Installation     
```shell  
$ sudo apt-get update -y
$ sudo apt-get upgrade -y
$ sudo apt-get install cutycapt
```  
### How to use it  
Output image will be placed in working directory and THE MOST important CutyCapt by some mean "squeezes" output image better use like that (output image will be 1920x1080)  
```shell  
$ cutycapt --url=http://www.google.com --out=google.png --min-width=1920 --min-height=1080
```
* ***local html page into image***  
(--url=file:${FULL_PATH}/${FILE_FULL_NAME} --out=${FULL_PATH_TO_DEST}/${FILES_NAME}.${EXTENSION})   
```shell  
$ cutycapt --url=file:/home/pi/Desktop/WebPage.html --out=tempPage.png  
```  
Be aware what if now full path do not given to output cutycapt will "dump" output into dir where console is currently is.
  
### How to use CutyCapt on a Headless server  
Headless server means what no monitor attachet to it or no X-window also!!!  
#### Install Xvfb  
```shell  
$ sudo apt-get install xvfb
```  
It will first launch the Xvfb server then use CutyCapt to screen capture of the webpage. 
So it may take longer. If you want to take multiple screenshots 
then you start can Xvfb server as a background daemon beforehand.  
After installing Xvfb change the command to run  cutycapt as:  
```shell  
$ xvfb-run -a --server-args="-screen 0, 1280x1200x24" cutycapt --url=http://www.demo.com --out=demo.png
```  
***--server-args and dimension*** are optional here.  

### Sources  
```shell
$ cutycapt --help
```  
[main Source | ](http://xmodulo.com/convert-html-web-page-png-image-linux.html) [Potential fix(not tested) of libraries | ](http://edwinhernandez.com/2013/05/26/installing-cutycapt-on-ubuntu-12-0-4/)[ CutyCapt and HEADLESS SERVER | ](https://www.oodlestechnologies.com/blogs/How-to-use-CutyCapt-on-a-headless-server/)

## VSCode
MS notepad but with extensions IDE. On Raspbian without Intelsens and debugger..  
***BE AWARE WHAT THIS IS INSTALLATION FOR VSCODE ON RASPBERRY PI BETTER USE [REMOTE_IDE](https://github.com/RazdolbayOne/GuidesPull/blob/master/Remote_Linux_IDE/README.md#why) 
ITS BETTER AT ANY CIRCUMSTANCES!!!***  
### Installation  
```shell  
1) $ wget https://packagecloud.io/headmelted/codebuilds/gpgkey -O - | sudo apt-key add -
2) $ curl -L https://code.headmelted.com/installers/apt.sh | sudo bash
3)??????
4)PROFIT!
```  
### IF YOU HAVE BLACK SCREEN WHEN YOU ARE OPENING VSCODE A-K-A DOOMSCREEN  
Problem source is in the version of your VScode or in linux.Here is two ways how to fix it
downgrade your vscode to stable version or turn off gpu(personally it did not helped me)  
```shell
$ apt-get install code-oss=1.29.0-1539702286 
```  
### Configuration  
Open VSCode and in extension tab in search box find C/c++ extension download it! Dats all you have working C/C++ IDE  
### How to start  
Create folder of your project and open that folder using VSCODE  
### How to debug Makefile project  
This works on version 0.2.0 of vs jsons   
In Makefile  you need add option ***-g*** flag to  compiler to use, “ ***-g*** ”: Generates debugginginformation that is used by gdb-baseddebuggers  
Adding a flag example
```
CC=g++ -g -Wall 
``` 

 Just in case rebuild your project with the added flag  before continue;      
 <br>
 First you need to change task.json in your project     
  To create a ***launch.json*** file, open your project folder in VS Code (***File > Open Folder***) and then select the Configure gear icon on the Debug view top bar. Chose gdb(for LInux) then launch.json will be generated but you need to change it like so:  
```launchJSON  
 {
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [

    
        {
            "name": "Pusk", //I named it Pusk because i can 
            "type": "cppdbg",
            "request": "launch",
            "program": "${workspaceFolder}/Pusk", //path to your programs exe and exe name
            "args": [],
            "stopAtEntry": false,
            "cwd": "${workspaceFolder}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "setupCommands": [
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ]
        }
    ]
}
 ```  
Second we must configure ***task.json***(basicly its kinda script to launch our programm using Makefile instead the default compiler).  
To create task.json
```  
    1)Open a folder with vscode
    2)Hit F1
    3)Select "Tasks: Configure Task Runner"
    4)Hit Enter and vscode will create a sample task.json for you
``` 
Change ***task.json*** like so(probably do not need so complicated one but  ¯\\_(ツ)_/¯ )  
```taskjson  
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
      {
        "label": "Build",
        "type": "shell",
        "command": "make", //its like writing in console make
        "group": {
          "kind": "build",
          "isDefault": true
        },
        "problemMatcher": {
          "owner": "cpp",
          "fileLocation": ["relative", "${workspaceFolder}"],
          "pattern": {
            "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
            "file": 1,
            "line": 2,
            "column": 3,
            "severity": 4,
            "message": 5
          }
        }
      }
    ]
  }
```
Rebuild project if you are not using ***Ctrl+Shift+B***(its like make in console now, because we changed task.json)  
DATS ALL!! YOU CAN NOW USE DEBUGER!!!  
[see "debug in vs code" article | ](https://github.com/LambdaSchool/CS-Wiki/wiki/C-and-Cpp-Debugging-in-VS-Code)[g++ in PDF | ](https://web.stanford.edu/class/cs193d/handouts/make.pdf)[MSD debuging in VSCODE | ](https://code.visualstudio.com/docs/editor/debugging) 

## Midnight Commander    
One tool that can help both Linux newbies and veterans is Midnight Commander, a Text User Interface (TUI) file manager.  
### Installation  
```shell  
$ sudo apt-get install mc
```
## Ftp server  
I exisist because transfering file from remote system to Pi is so hedius what I chose ftp to transfer crap from my PC to Pi;    
### Server installation on Linux  
1) Install ftp server:
```shell  
$ sudo apt-get install vsftpd
```  
2) ***Configuring FTP server*** Most VSFTPD’s configuration takes place in ***/etc/vsftpd.conf*** need to be root btw to edit it :  
2.1) Enable Uploading to the FTP server by uncommenting thw line :
```  
write_enable=YES
```  
2.2) Allow Local Users to Login uncomment if it is commented:  
```  
local_enable=YES
```  
3) Restart your FTP server:  
```shell
$ sudo systemctl restart vsftpd
```  
[Source](https://itsfoss.com/set-ftp-server-linux/)  
### Server installation on Win  
The Awesome Emptiness Of What Is In Front Of YOU  
### Client on Linux  
The Awesome Emptiness Of What Is In Front Of YOU  
## Client on Windows   
Just download and install [FileZilla](https://filezilla-project.org/)  
<img src="https://imgur.com/w6uryw7.png"></img>  
ХОСТ ->hostname to connect to your server  
Имя пользовотеля ->PIs name a.k.a username  
Пароль -> password to remote server  
Кнапка Быстрое соединения -> after filling previous editboxes and pressing this button your will connect to ftp server   
### Sources  
Here is sored all resources where data was found   
[ISSUES | ](https://github.com/headmelted/codebuilds/issues/43>)[Another installation Guide | ](https://medium.com/@melzoghbi/install-visual-studio-code-on-raspbian-eedc566c616d)
