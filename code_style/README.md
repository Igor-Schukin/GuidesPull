# This topic stands for coding style of C++ in project.  
* avoid "using namespace " keep clean project from namespacing chaos   
* variables_in_lower_snake_style     
* geters and setters will be like so -> get_my_beloved_variable() and set_it_to_the_hights()  
* private methods/variables have prefix ***" m_ "***  
* methods naming style is like so MyClass->MySmoothMethod();    
* if method only have one word then it is like so MyClass->Method();   

* example of class struct and code style
```C++  
//class template
class MyClass{
public:
  void MySmoothMethod();
  void Derp();
  
  int get_my_variable();
  void set_my_variable(int aVar);
private:
  void m_MyHidedMethod();
  int m_my_variable;
};
```  
[SOURCE C++ GuideLines from Stroustrup](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)  
[Guglec a.k.a fundementals of project style code with some exceptions](https://google.github.io/styleguide/cppguide.html#Variable_Names)  
