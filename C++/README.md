
# C/C++ related stuff  
- [How to write UserFirendly C++](#how-to-write-userfriendly-c)
- [With OpenVG](#with-openvg)
- [Libs](#libs)  
  - [JSON++](#json)
  - [cURL](#curl)
  - [CPR](#cpr)
- [List of useful functions  ](#list-of-useful-functions)  
  - [Get Image Size](#get-image-size)
  - [Button press detection](#button-press-detection)
- [Sources](#sources)  
## How to write Userfriendly C++
Read through and bookmark the[C++ Standard Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)  
[Годные Видео уроки по С++](https://www.youtube.com/watch?v=kRcbYLK3OnQ&list=PLQOaTSbfxUtCrKs0nicOg2npJQYSPGO9r) от #SimpleCode  
[C++ The complete reference 4th | book](http://160592857366.free.fr/joe/ebooks/ShareData/C++%20-%20The%20Complete%20Reference%204e.pdf)
## With OpenVG
How to install & configure OpenVG you can find [here](https://github.com/RazdolbayOne/GuidesPull/tree/master/OpenVG).    
Part to add into OpenVG project to work with C++
```cpp
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <iostream>
extern "C" {   //this  allows you to use OpenVG in C++ code;
#include "VG/openvg.h"
#include "VG/vgu.h"
#include "fontinfo.h"
#include "shapes.h"
}// this end par that allows you to use in C++
```
[Here](https://github.com/RazdolbayOne/GuidesPull/blob/master/C%2B%2B/Simple_Hello_world_with_OpenVG) you can find Hello world on OpenVG with Makefile.
## Libs  
Here are stored list of a11y libs for Smart.RTU project
### JSON++  
Allows you to ***parse/create jsons*** in c++ project.
Where can donwload single header for json [ТЫК](https://github.com/RazdolbayOne/GuidesPull/tree/master/C%2B%2B/JSON%2B%2B) or you can download full project from [here](https://github.com/nlohmann/json)
* You only need to add this to project 
```cpp
#include <nlohmann/json.hpp>

// for convenience
using json = nlohmann::json;
```
[Here are list of methods what json++ can do](https://github.com/nlohmann/json)
### cURL  
This lib allows you to use in your project ***RESTapi*** [stuff](https://flaviocopes.com/http-curl/). Lib is without methods and is also function programming C lib.
cURL supports this protocols ->***HTTP,FTP,SSH***   
Probably need to move to [C++ wrapper around libcURL ](https://github.com/jpbarrette/curlpp)  
//need to add methods,examples and options what can  cURL  
#### ***Installation & configuration*** 
* For LINUX  
Need to be installed [gcc !!!](https://github.com/RazdolbayOne/GuidesPull/tree/master/Make#how-to-install-make)  
Download [archive](https://curl.haxx.se/download.html) and unzip it or use GIT to get source repo  
```shell  
$ git clone https://github.com/curl/curl.git
```
A normal Unix installation is made in three or four steps (after you've unpacked the source archive if you downloaded zip if had been used git skip that) commands must be exe ***inside  unziped curl folder*** and need to be ***root*** :  
```shell
$ ./configure
$ make
$ make test 
$ make install
```
***#Include*** for project  
```
#include <curl/curl.h>  
```
***lib*** what must be added to Makefile  
```Makefile  
-lcurl
```  
If this error appiers then launching you exe what uses cURL  
```text  
./(Your exe name): error while loading shared libraries: libcurl.so.4: cannot open shared object file: No such file or directory 
```
then type this in console:  
```shell  
$ sudo apt-get install libcurl3 -y
```
* For Windows  
//сдесь должен быть варик бес vcpkg   

Alternatively you can use vcpkg to install curl:    
Works on Visual Studio 2017 -> windows7  
Works on VS 2019 ->Win10  
1.Get [vcpkg](https://github.com/microsoft/vcpkg/archive/2019.08.zip) and extract it to a folder of your choice (e.g. C:\vcpkg\)  
2.Open ***Developer Command Prompt for VS***  for me(I have VS 2017) it is in path 
```shell  
C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build
```  
and RUN(from console obviusly)
```shell  
vcvarsall.bat amd64
```
and ***cd*** to ***C:\vcpkg\***  
3.Run  
```
bootstrap-vcpkg.bat
```
4.RUN  
```  
vcpkg.exe integrate install
```
5.RUN  
```  
vcpkg.exe install curl
```
6.Create a new C++ project in Visual Studio and you're ready to go - try it with the example above. There's no need to modify project settings.  
```cpp  
#define CURL_STATICLIB
#include <curl\curl.h>

int main()
{
    CURL *curl;

    curl = curl_easy_init();
    curl_easy_cleanup(curl);

    return 0;
}
```

[MainPage of cURL | ](https://curl.haxx.se/)
[Downloand | ](https://curl.haxx.se/download.html)
[Installation | ](https://curl.haxx.se/docs/install.html)
[Tutorial | ](https://curl.haxx.se/libcurl/c/libcurl-tutorial.html)
[Examples | ](https://curl.haxx.se/libcurl/c/example.html)
[Работаем в сети с помощью libcurl | ](https://www.programmersforum.ru/showthread.php?t=60338)
[Установка для шминдоуса | ](https://stackoverflow.com/questions/53861300/how-do-you-properly-install-libcurl-for-use-in-visual-studio-2017)  
### CPR  
CPR is OOP wrapper around cURL lib. Can do REST HTTP requests asynchronos too. and other stuff like authentication.. ***WORKS ONLY ON CMAKE PROJECTS!!!***   
## How to install into existing project  

## Documentation  
[its here | ](https://whoshuu.github.io/cpr/)[or in its github ](https://github.com/whoshuu/cpr)  
## List of useful functions  
Functions/Methods for project and most common tasks.  
### Get Image Size
Code what auto finds out image size works with ***JPEG,PNG***  
You can find it [here.](https://github.com/RazdolbayOne/GuidesPull/blob/master/C%2B%2B/Usefull_functions/Get_Image_Size_func.txt)
### Button press detection
Function what detects if user pressed key on keyboard or not .and what kind of kay it had pressed.. 
Code is [here.](https://github.com/RazdolbayOne/GuidesPull/blob/master/C%2B%2B/Usefull_functions/Button_press_detection_check_func)
## Sources
