 
 # All info about OpenVG and Libshape  
 OpenVG is an API designed for hardware-accelerated 2D vector graphics.
<img src="https://imgur.com/7mp02Wr.png" ></img>   
- [Installation & Confuguration  ](#installation-and-confuguration)
- [First Program](#first-program)
- [LibShape](#libshape)
- [Sources](#sources)
## Installation and Confuguration  
Here is List of commands/steps what must be done in console and changes what must to be done in openvg files to work in Raspberry PI(Raspbian OS)  
Before what [gcc/make](https://github.com/RazdolbayOne/GuidesPull/tree/master/Make/Makefile) must be installed!
* ***In console:***  
```shell  
0)$ cd ~
1)$ sudo apt-get install libjpeg8-dev indent libfreetype6-dev ttf-dejavu-core
2)$ git clone git://github.com/ajstarks/openvg
3)$ cd openvg
4)$ sudo make
```  
* ***IN FOLDERS OF YOUR RASPBERRY PI***  
5)Open MakeFile in  /home/pi/openvg/client  
6)Change lines in MakeFile from :  
```  
-lEGL -lGLESv2  (whatever laters was there)

to:

-lbrcmEGL -lbrcmGLESv2

```  
* ***in console***  
```shell  
7)$ cd client   
8)$ sudo make test  
```  
After this command must be some kind of slideshow what shows what OpenVG can do if not well check this-> *  
9)To install the shapes library as a system-wide shared library type this in console(***not in /client but in /openvg folder***)  
```shell  
9.1)$ make library
9.2)$ sudo make install
```  
10)Install libpng lib to use png images  
```shell  
$ sudo apt-get install libpng-dev 
```
## First program  
```cpp  
//==============================================================================================================================================================================================================================================
//							HELLO WORLD USING OPENVG IN C++ 
//==============================================================================================================================================================================================================================================
// first OpenVG program
// Anthony Starks (ajstarks@gmail.com)
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <iostream>
extern "C" {   //this  allows you to use OpenVG in C++ code;
#include "VG/openvg.h"
#include "VG/vgu.h"
#include "fontinfo.h"
#include "shapes.h"
}


using namespace std;

int main() {
	int width, height;
	char s[3];

	init(&width, &height);								// Graphics initialization //how big  wigth and heigth are screen
for(int i=0;i<100;i++){									//10 second apearing Loop of hello world on your screen 
	Start(width, height);								// Start the picture
	Background(0+(i*2), 0+(i*2), 0+(i*2));						// From black to white background using RGB system
	Fill(44, 77, 232, 1);								// Big blue marble
	Circle(width / 2, 0, width);							// The "world"
	Fill(255, 255, 255, 1);								// White text
	TextMid(width / 2, height / 2, "hello, world", SerifTypeface, width / 10);	// Greetings 
	End();		// End the picture
	}										//End of 10 second apearing Loop
	fgets(s, 2, stdin);				   				// look at the pic, end with [RETURN]
	finish();					           			// Graphics cleanup
	exit(0);
}




//==============================================================================================================================================================================================================================================
//								MAKEFILE
//==============================================================================================================================================================================================================================================
/*
#NOT IDEAL MAKEFILE BUT WORKING!!!!!
#ALSO MAKEFILE MUST BE IN THE SAME FOLDER AS MAIN PROJECT FILE/FILES
INCLUDEFLAGS = -I/opt/vc/include -I/opt/vc/include/interface/vmcs_host/linux -I/opt/vc/include/interface/vcos/pthreads -I/home/pi/openvg
LIBFLAGS = -L/opt/vc/lib -lbrcmEGL -lbrcmGLESv2 -lbcm_host -lpthread  -ljpeg
main:main.cpp 
		g++ -Wall $(INCLUDEFLAGS) -o main  main.cpp $(LIBFLAGS) /home/pi/openvg/libshapes.o /home/pi/openvg/oglinit.o
*/

``` 
<a href="http://www.flickr.com/photos/ajstarks/7828969180/" title="hellovg by ajstarks, on Flickr"><img src="http://farm9.staticflickr.com/8436/7828969180_b73db3bf19.jpg" width="500" height="281" alt="hellovg"></a>  
## Libshape
 Сдесь должны быть функции либшейпа но  автор не смог побороть лень 
<img src="https://imgur.com/AUY3JQX.gif" width="90%"></img>  
## Sources  
[Functions of libshape | ](https://github.com/ajstarks/openvg)[OLDversion on installation & OpenVG repo | ](https://github.com/ajstarks/openvg)  
*if after doing these steps or you have other problems with installation of OpenVG then welcome to the club buddy...
Start dancing with tambourine.......
