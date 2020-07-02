
# All about Linux & shell
Topic where all abut Linux shell  is stored  
<img src="https://imgur.com/ej7mp6Y.png" width="60%"></img>   
- [Linux Interactive sources](#interactive-source)  
- [Linux Readable sources](#readable)  
- [Redirection output in Linux](#redirection-output-in-linux)
  - [Intro and Basics](#going-down-the-rabbit-hole-of-redirection)
  - [Redirect all output to file](#syntax-to-redirect-all-output-to-file)
  - [Redirect all error to file](#syntax-to-redirect-all-error-to-file)
  - [Redirect both output (stdout) and errors (stderr) to different files](#syntax-to-redirect-both-output-and-errors-to-different-files)
  - [table of 10 most commonly used ways](#table-of-signs)
## Interactive source  
[BEST OF THE BEST | ](https://linuxsurvival.com/linux-tutorial-introduction/)[linux.org | ](http://linuxcommand.org/)[BEST OF THE BEST 2(multiple tasks with linux shell) | ](https://www.hackerrank.com/domains/shell)[Kinda OK | ](https://commandlinepoweruser.com/)[Configuring Linux Web Servers | ](https://www.udacity.com/course/configuring-linux-web-servers--ud299)  
## Readable  
[Advanced Bash-Scripting Guide. An in-depth exploration of the art of shell scripting | ](http://www.tldp.org/LDP/abs/html/index.html)[A Guide to 100 (ish) Useful Unix Commands | ](http://oliverelliott.org/article/computing/ref_unix/)  

## Redirection output in Linux  
Before redirection your output programm must be in [specific manner...](https://github.com/RazdolbayOne/GuidesPull/blob/master/C++/README.md#stderr-and-stdout) otherwise redirection would not happen.  
### going down the rabbit hole of redirection  
Before that need to create(probably do not needed but I did not tested) two txt files(where errors and output will be printed).  
Btw  three file descriptors(bassicaly cods using them you can output specific data(errors or normal outputs for example)):
* white-space/nothing mean all descriptors  
* stdin (0) - standart input   
* stdout (1)- standart output 
* stderr (2)- standart error output  
Base syntax is:  
```shell  
$ ${your_EXE_NAME} ${descriptor} > ${out_put_file.txt}
```  
### Syntax To redirect all output to file  
```shell  
$ command-name >  output.txt
```  
### Syntax To redirect all error to file  
```shell  
$ command-name 2> errors.txt
```  
### Syntax to redirect both output and errors to different files  
```shell  
$ command-name 1> output.txt 2> errors.txt
```  
### Table of signs  
<img src="https://imgur.com/9phBUso.png" ></img>  
<img src="https://imgur.com/ju7PZZP.png" ></img>  
[Source one | ](https://askubuntu.com/questions/420981/how-do-i-save-terminal-output-to-a-file)[source two](https://www.cyberciti.biz/faq/linux-redirect-error-output-to-file/)
