# 'Smag Grotto' box writeup
## Smag Grotto is a CTF box written by JakeDoesSec and available on the [TryHackMe platform](https://tryhackme.com).
# ![bg](images/background.png?raw=true "Title")

+ **We deploy the machine and start with a nmap scan for open ports**

``nmap -sV -sC -oN scan1 10.10.163.139``

+ **There are 2 services running on default ports: ssh and http**

![1](images/nmap_scan_sg.jpg?raw=true "nmap_scan")

+ **Visiting the http site, we are welcomed by a big Smag title with a small announce from the developer of the site**

![2](images/site_sg.png?raw=true "Site")

+ **Let's perform a gobuster to search some directories on the website. I'm using the common.txt wordlist, a default wordlist on kali machines**

``gobuster dir -u http://10.10.163.139/ -w /usr/share/wordlists/dirb/common.txt``


![3](images/dirbuster.jpg?raw=true "gobuster")

+ **We found a mail directory, so let's check it out into the web browser. It seems to be like a mail message left on the website to notify a future migration. The mail was writen with the intention to arrive to the admin of the page**

![4](images/mail_page.png?raw=true "mail_page")

+ **Inside the first Network Migration box of the message, we can spot the dHJhY2Uy.pcap, a linked file which seems to be a packet data of this network. Let's download that file and go into a Wireshark analysis of this packet.**

![5](images/wiresh_packet.png?raw=true "wireshark_analysis")

+ **We can spot a POST login request inside the data packet, so let's follow TCP stream into this packet**

![6](images/tcp_stream.png?raw=true "tcp_stream")

