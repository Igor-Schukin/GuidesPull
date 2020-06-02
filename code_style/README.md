# This topic stands for coding style of C++ in project.  
* avoid "using namespace " keep clean project from namespacing chaos   
* variables_in_lower_snake_style     
* geters and setters will be like so -> Getmy_beloved_variable() and Setit_to_the_hights()  
* private methods/variables have prefix ***" m_ "***  
* methods naming style is like so MyClass->MySmoothMethod();    
* if method only have one word then it is like so MyClass->method();   

* example of class struct and code style. file foo/src/bar/baz.h in project foo  
```C++  
//class template
#pragma once
//<PROJECT>_<PATH>_<FILE>_H_
#ifndef FOO_BAR_BAZ_H_
#define FOO_BAR_BAZ_H_

//C system headers(more precisely: headers in angle brackets with the .h extension), e.g. <unistd.h>, <stdlib.h> 

//C++ standard library headers (without file extension), e.g. <algorithm>, <cstddef>.  

//Other libraries' .h files 

//Your project's .h files

class MyClass{
public:
  void MySmoothMethod();
  void derp();
  
  int Getmy_variable();//google style-> get_my_variable();
  void Setmy_variable(int new_variable);//google style ->set_my_variable
private:
  void m_MyHidedMethod();
  int m_my_variable;
};
#endif /*FOO_BAR_BAZ_H_*/
```  
[SOURCE C++ GuideLines from Stroustrup](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)  
[Guglec a.k.a fundementals of project style code with some exceptions](https://google.github.io/styleguide/cppguide.html#Variable_Names)  
