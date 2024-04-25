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


Enumerating Files
----

Gobuster Tool can enumerate hidden files along with the remote directories. Gobuster allows us to use the “-x” option followed by the file extensions you’d like to search for.

Consider the example below:
```
gobuster dir -u https://www.geeksforgeeks.com w /usr/share/wordlists/big.txt -x php,html,htm
```
In this command, we are specifically searching for files that have php,htm or html extensions.


Obtaining Full Path for a directory or file
----



Option “-e” is used for completing printing URL when extracting any hidden file or hidden directories
```
gobuster dir -e -u geeksforgeeks.org -w /usr/share/wordlists/dirb/common.txt –wildcard
```


Hide Status Code
----


Using -n Option “no status” mode prints the results’ output without presenting the status code.
```
gobuster dir -u geeksforgeeks.org -w /usr/share/wordlists/dirb/common.txt -n –wildcard
```



Disable Banner
----


Gobuster tool constantly adds the banner to define the brief introduction of applied options while launching a brute force attack. By using the -q option, we can disable the flag to hide extra data.
```
gobuster dir  -u geeksforgeeks.org -w /usr/share/wordlists/dirb/common.txt -q –wildcard
```


Set Threads Number
----


Using the -t option enables the number of thread parameters to be implemented while brute-forcing sub-domain names or directories.
```
gobuster  dns -d geeksforgeeks.org -t 100 -w /usr/share/wordlists/dirb/common.txt –wildcard
```


Obtain Sub Domain IPs
----


Using the -i option allows the IP parameter, which should show the IPs of selected sub-domains.
```
gobuster  dns -d geeksforgeeks.org -t 100 -w /usr/share/wordlists/dirb/common.txt -i –wildcard
```
<p1/>DNS mode is covered in this command<p1/>
