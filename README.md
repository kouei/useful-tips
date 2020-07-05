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

