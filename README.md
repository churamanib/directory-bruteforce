# directory-bruteforce

directory brutefprce all website using many tools
----
<h1/>1. gobuster how we use this tool<h1/>
installation gobuster
----
  
We need to install Gobuster Tool since it is not included on Kali Linux by default

```
apt-get install gobuster
```
<p1/>Then, simply type gobuster into the terminal to run the tool for use.<p1/>
```
gobuster -h
```
<p1/>Note that these examples will not work if the mandatory option “-u” is not specified.Wordlist Specification

<p1/>
```
gobuster dir -u https://www.exampale.org/ -w /usr/share/wordlists/big.txt
```
<p1/>Obtaining Full Path for a directory or file<br/>
Option “-e” is used for completing printing URL when extracting any hidden file or hidden directories
<p1/>

```
gobuster dir -e -u geeksforgeeks.org -w /usr/share/wordlists/dirb/common.txt –wildcard
```
<p1/>
