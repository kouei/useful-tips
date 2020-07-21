# Useful Tips
Some useful tips collected from the Internet.

## Use aptitude to solve version conflict
If version conflict happens when you are installing something through:  
  
`$ sudo apt install xxx`  
  
you can use `aptitude` to substitute `apt`:  
  
`$ sudo aptitude install xxx`  

## Setup SOCKS5 proxy for apt
Add the following content:  
  
`Acquire::socks::http "socks5h://127.0.0.1:1080";`  
`Acquire::socks::https "socks5h://127.0.0.1:1080";`  
`Acquire::socks::ftp "socks5h://127.0.0.1:1080";`  
  
to /etc/apt/apt.conf.d/proxy.conf  

## Setup SOCKS5 proxy for git
`$ git config --global http.proxy "socks5://127.0.0.1:1080"`  
`$ git config --global https.proxy "socks5://127.0.0.1:1080"`  

## Tools for creating boot USB drive
1. For windows, use 微PE.
2. For Linux, use Rufus.

## Print web page in WYSIWYG style (Save Page WE)
**Save Page WE** is an awesome Google Chrome Extension that can print a web page into a single html in a WYSIWYG (What you see is what you get) style.

## Check Linux Version (Neofetch)
The **neofetch** command can display your linux version with its logo drawn in ascii art.
on Ubuntu, simply install it with **apt**.  


## Game-based Git Tutorial
[Learning Git Branching](https://learngitbranching.js.org) is an awesome game-based git tutorial




# CMD Script Tips

## Turn off the echo mode
When running a cmd script, before every line is executed, the cmd echoes the actual
command line it is going to execute. To turn off this feature, add following to the
top of the cmd script:

`@echo off`

or if you just want to turn of the echo mode of a single command, simply add a **@** to your command:  

`@[Your Command]`  

## Arithmetic Operation
It is better to use quotation mark in the arithmetic operation:

`set /a num="(2+4)*5"`

## :eof
**:eof** is a special label, which always point to the end of the current cmd script file.
So `goto :eof` actually ends the running script.

## setlocal
When used in a batch file, makes all further changes to environment variables local to the current batch file. When used outside of a batch file, does nothing. Can be ended using  
**endlocal**. Exiting a batch file automatically calls **endlocal**.  
  
Furthermore, can be used to enable delayed expansion like this: "setlocal EnableDelayedExpansion". Delayed expansion consists in the names of variables enclosed in exclamation marks  
being replaced with their values only after the execution reaches the location of their use rather than at an earlier point.  

## Delayed Expansion

The following script will output **4** instead of **5**  
  
```
@echo off 
set a=4 
set a=5 & echo %a% 
```
  
This is because when CMD load `set a=5 & echo %a% `, it will load all occurrences of %a% in a whole, before `set a=5` had a chance to execute.  
To solve this problem you need Delayed Expansion which will make CMD load environment variables each time it executes a sub-statement.  
To set Delayed Expansion:  

`setlocal enabledelayedexpansion`  
  
Then, you have to change %a% to !a! in order to use Delayed Expansion.  

Now the following script will output **5** as expected:  
  
```
setlocal enabledelayedexpansion
@echo off 
set a=4 
set a=5 & echo !a!
```


# Docker Tips
## Change Storage Driver
1. Create the following file if it does not exist:  
`/etc/docker/daemon.json`

2. Add the following content to it:
```
{
    "storage-driver":"aufs"
}
```
This will change the storage driver from "overlay2" (default) to "aufs"



## Semantic Versioning
[Semantic Versioning](https://semver.org/) is a good tool for solving the [Dependency Hell](https://en.wikipedia.org/wiki/Dependency_hell#:~:text=Dependency%20hell%20is%20a%20colloquial,versions%20of%20other%20software%20packages.) issue.

## Choose License for a Project
[Choose an open source license](https://choosealicense.com/) is a good place to help you choose a suitable license for your project.

## py versus python3
Use Command `py` Instead of Command `python3` on Windows (CMD/PowerShell)  
See https://stackoverflow.com/questions/61058298/why-does-python-use-py-to-run-programs-on-windows  

## Packaging Python Projects
See [Packaging Python Projects](https://packaging.python.org/tutorials/packaging-projects/) for how to package python project, so that you can install it with `pip`.
