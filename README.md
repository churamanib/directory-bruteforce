# directory-bruteforce
directory Bruteforcing Attack Any Web Page 
---

Installation Steps of Gobuster Tool in Linux OS
----


We need to install Gobuster Tool since it is not included on Kali Linux by default
```
apt-get install gobuster
```



Then, simply type gobuster into the terminal to run the tool for use
```
gobuster -h
```


 Installing Additional Seclists for brute-forcing Directories and Files
 ```
apt-get install seclists
```

By default, Wordlists on Kali are located in the /usr/share/wordlists directory.
----


Target Specification
----


So, while using the tool, we need to specify the “-u” followed by a target URL, IP address, or a hostname. This option is compulsory, as there is a target specified for getting results.

Some of the examples show how to use this option
```
gobuster dir -u https://www.geeksforgeeks.org/
```
```
gobuster dir -u https://www.webscantest.com
```
```
gobuster dir -u 192.168.21.154
```


Note that these examples will not work if the mandatory option “-u” is not specified.
----


Wordlist Specification
----


Gobuster Tool enumerates hidden directories and files in the target domain by performing a brute-force attack. A brute-force attack consists of matching a list of words or a combination of words hoping that the correct term is present in the list. So, Gobuster performs a brute attack. To force an attack, we need to specify a collection of words, i.e., wordlist. So to provide this wordlist, you need to type the “-w” option, followed by the path of the wordlist where it is located. We can use a wordlist file that is already present in the system
```
gobuster dir -u https://www.geeksforgeeks.org/ -w /usr/share/wordlists/big.txt
```

