# This topic stands for coding style of C++ in project.  
* avoid "using namespace " keep clean project from namespacing chaos   
* variables_in_lower_snake_style   //*  
* except geters and setters they starts with lower get or set word like so -> getSmile(); setX() etc  //*  
* private methods/variables have prefix "m_"  
* methods naming style is like so MyClass->MySmoothMethod(); //*   
* if method only have one word then it i like so MyClass->Method(); //*  
  
*PROBABLY NEED TO GO FULL ON INTO PYTHON STYLE
* class template
```C++  
//class template
class MyClass{
public:
  //methods
private:
  //methods
  //variables
};
```  
[SOURCE C++ GuideLines from Stroustrup](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)  
[Guglec a.k.a fundementals of project style code with some exceptions](https://google.github.io/styleguide/cppguide.html#Variable_Names)  
