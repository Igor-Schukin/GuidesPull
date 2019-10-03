# Here are stored additionall programs/Guides for SmartRTU
- [CutyCapt](#cutycapt)
- [VSCode](#vscode)
- [Sources](#sources)
## CutyCapt  
CutyCapt is comand line converter from ***HTML to image.***  
Support formats for img ->***SVG, PDF, PS, PNG, JPEG, TIFF, GIF***  
btw have support of javascript.
### Installation     
```shell  
$ sudo apt-get update upgrade
$ sudo apt-get install cutycapt
```  
### How to use it  
Output image will be placed in working directory and THE MOST important CutyCapt by some mean "squeezes" output image better use like that (output image will be 1920x1080)  
```shell  
$ cutycapt --url=http://www.google.com --out=google.png --min-width=1920 --min-height=1080
```
* ***local html page into image***  
(--url=file:$(FULL_PATH)/$(FILE_FULL_NAME) --out=$(FILES_NAME).$(EXTENSION))   
```shell  
$ cutycapt --url=file:/hone/pi/Desktop/WebPage.html --out=tempPage.png  
```

### How to use CutyCapt on a Headless server  
Headless server means what no monitor attachet to it!!!  
#### Install Xvfb  
```shell  
$ sudo apt-get install xvfb
```  
It will first launch the Xvfb server then use CutyCapt to screen capture of the webpage. 
So it may take longer. If you want to take multiple screenshots 
then you start can Xvfb server as a background daemon beforehand.  
After installing Xvfb change the command to run  cutycapt as:  
```shell  
$ xvfb-run --server-args="-screen 0, 1280x1200x24" cutycapt --url=http://www.demo.com --out=demo.png
```  
***--server-args and dimension*** are optional here.  

### Sources  
```shell
$ cutycapt --help
```  
[main Source | ](http://xmodulo.com/convert-html-web-page-png-image-linux.html) [Potential fix(not tested) of libraries | ](http://edwinhernandez.com/2013/05/26/installing-cutycapt-on-ubuntu-12-0-4/)[ CutyCapt and HEADLESS SERVER | ](https://www.oodlestechnologies.com/blogs/How-to-use-CutyCapt-on-a-headless-server/)

## VSCode
MS notepad but with extensions IDE. On Raspbian without Intelsens and debugger..
### Installation  
```shell  
1) $ wget https://packagecloud.io/headmelted/codebuilds/gpgkey -O - | sudo apt-key add -
2) $ curl -L https://code.headmelted.com/installers/apt.sh | sudo bash
3)??????
4)PROFIT!
```  
### IF YOU HAVE BLACK SCREEN WHEN YOU ARE OPENING VSCODE A.K.A DOOMSCREEN  
Problem source is in the version of your VScode or in linux.Here is two ways how to fix it
downgrade your vscode to stable version or turn off gpu(personally it did not helped me)  
```shell
$ apt-get install code-oss=1.29.0-1539702286 
```  
### Configuration  
Open VSCode and in extension tab in search box find C/c++ extension download it! Dats all you have working C/C++ IDE  
### How to start  
Create folder of your project and open that folder using VSCODE  
### Sources  
[ISSUES | ](https://github.com/headmelted/codebuilds/issues/43>)[Another installation Guide | ](https://medium.com/@melzoghbi/install-visual-studio-code-on-raspbian-eedc566c616d)
