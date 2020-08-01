# 'Smag Grotto' box writeup
## Smag Grotto is a CTF box written by JakeDoesSec and available on the [TryHackMe platform](https://tryhackme.com).
# ![bg](images/background.png?raw=true "Title")

+ **We deploy the machine and start with an nmap scan for open ports**

``nmap -sV -sC -oN scan1 10.10.163.139``

+ **There are 2 services running on default ports: ssh and http**

![1](images/nmap_scan.jpg?raw=true "Title")
