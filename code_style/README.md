# This topic stands for coding style of C++ in project.  
* avoid "using namespace " keep clean project from namespacing chaos   
* variables_in_lower_snake_style     
* geters and setters will be like so -> get_my_beloved_variable() and set_it_to_the_hights()  
* private methods/variables have prefix ***" m_ "***  
* methods naming style is like so MyClass->MySmoothMethod();    
* if method only have one word then it is like so MyClass->Method();   

* example of class struct and code style. file foo/src/bar/baz.h in project foo  
```C++  
//class template
#pragma once
//<PROJECT>_<PATH>_<FILE>_H_
#ifndef FOO_BAR_BAZ_H_
#define FOO_BAR_BAZ_H_

//C system headers 

//C++ standard library headers (without file extension)

//Other libraries' .h files 

//Your project's .h files

class MyClass{
public:
  void MySmoothMethod();
  void Derp();
  
  int get_my_variable();
  void set_my_variable(int new_variable);
private:
  void m_MyHidedMethod();
  int m_my_variable;
};
#endif /*FOO_BAR_BAZ_H_*/
```  
[SOURCE C++ GuideLines from Stroustrup](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)  
[Guglec a.k.a fundementals of project style code with some exceptions](https://google.github.io/styleguide/cppguide.html#Variable_Names)  
