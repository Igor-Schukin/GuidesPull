
# C/C++ related stuff  
- [How to write UserFirendly C++](#how-to-write-userfriendly-c)
- [With OpenVG](#with-openvg)
- [Libs](#libs)  
  - [JSON++](#json)
  - [cURL](#curl)
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
This lib allows you to use in your project ***RESTapi*** stuff. Lib is without methods and is also function programming C lib.
cURL supports this protocols ->***HTTP,FTP,SSH***   
Probably need to move to [C++ wrapper around libcURL ](https://github.com/jpbarrette/curlpp)  
//need to add methods,examples and options what can  cURL  
[MainPage of cURL](https://curl.haxx.se/)  
[Tutorial](https://curl.haxx.se/libcurl/c/libcurl-tutorial.html)
[Работаем в сети с помощью libcurl](https://www.programmersforum.ru/showthread.php?t=60338)
## List of useful functions  
### Get Image Size
Code what auto finds out image size works with ***JPEG,PNG***  
You can find it [here.](https://github.com/RazdolbayOne/GuidesPull/blob/master/C%2B%2B/Usefull_functions/Get_Image_Size_func.txt)
### Button press detection
Function what detects if user pressed key on keyboard or not .and what kind of kay it had pressed.. 
Code is [here.](https://github.com/RazdolbayOne/GuidesPull/blob/master/C%2B%2B/Usefull_functions/Button_press_detection_check_func)
## Sources
