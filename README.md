# directory-bruteforce
directory Bruteforcing Attack Any Web Page 
---
///////////////////////////////////////////////////////////////////////////////////////////////<br/>
<br/>
<br/>
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
gobuster dir -u https://www.example.org/
```
```
gobuster dir -u https://www.example.com
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
gobuster dir -u https://www.example.org/ -w /usr/share/wordlists/big.txt
```

Enumerating Files
----

Gobuster Tool can enumerate hidden files along with the remote directories. Gobuster allows us to use the “-x” option followed by the file extensions you’d like to search for.

Consider the example below:
```
gobuster dir -u https://www.example.com w /usr/share/wordlists/big.txt -x php,html,htm
```
In this command, we are specifically searching for files that have php,htm or html extensions.

Obtaining Full Path for a directory or file
----

Option “-e” is used for completing printing URL when extracting any hidden file or hidden directories
```
gobuster dir -e -u example.org -w /usr/share/wordlists/dirb/common.txt –wildcard
```

Hide Status Code
----

Using -n Option “no status” mode prints the results’ output without presenting the status code.
```
gobuster dir -u example.org -w /usr/share/wordlists/dirb/common.txt -n –wildcard
```

Disable Banner
----

Gobuster tool constantly adds the banner to define the brief introduction of applied options while launching a brute force attack. By using the -q option, we can disable the flag to hide extra data.
```
gobuster dir  -u example.org -w /usr/share/wordlists/dirb/common.txt -q –wildcard
```

Set Threads Number
----

Using the -t option enables the number of thread parameters to be implemented while brute-forcing sub-domain names or directories.
```
gobuster  dns -d example.org -t 100 -w /usr/share/wordlists/dirb/common.txt –wildcard
```

Obtain Sub Domain IPs
----

Using the -i option allows the IP parameter, which should show the IPs of selected sub-domains.
```
gobuster  dns -d example.org -t 100 -w /usr/share/wordlists/dirb/common.txt -i –wildcard
```
<p1/>DNS mode is covered in this command<p1/>

Timeout
----

Using the –timeout option allows the timeout parameter for HTTP requests, and 5 seconds is the default time limit for the HTTP request.
```
gobuster dir –timeout 5s -u example.org -t 100 -w /usr/share/wordlists/dirb/common.txt –wildcard
```

Appending Forward Slash
----

I am using the -f option here for appending the forward-slash while making a brute-force attack on the target URL.
```
gobuster dir -u example.org -w /usr/share/wordlists/dirb/common.txt -f –wildcard
```

Enumerating Directory with Specific Extension List
----

There are many scenarios where we need to extract the directories of a specific extension over the victim server, and then we can use the -X parameter of this scan. This parameter allows the file extension name and then explores the given extension files over the victim server or computer.
```
gobuster dir -u example.org -w /usr/share/wordlists/dirb/common.txt -x .php –wildcard
```

Follow Redirect
----

Using -r options allows redirecting the parameters, redirecting HTTP requests to another, and changing the Status code for a directory or file.
```
gobuster dir -u example.org -w /usr/share/wordlists/dirb/common.txt -q –wildcard
```
```
gobuster dir -u example.org -r -w /usr/share/wordlists/dirb/common.txt -q –wildcard
```

HTTP AUTHORIZATION (-u username: password)
----

HTTP Authentication/Authentication mechanisms are all based on the use of 401-status code and WWW-Authenticate response header. The most generally used HTTP authentication mechanisms are Primary. The client sends the user name and password un-encrypted base64 encoded data.

So, to avoid this kind of authentication with the help of Gobuster, we have used the command below:
```
gobuster dir -u http://testphp.vulnweb.com/login.php -w /usr/share/wordlists/dirb/common.txt -U test -P test –wildcard
```

Force Processing Brute Force
----

It ends by obtaining the sub-domain name if it meets any Wildcard DNS, which is a non-existing domain. Therefore, it uses the –wildcard option to allow parameters to continue the attack even if there is any Wildcard Domain.
```
gobuster dir -u example.org -w /usr/share/wordlists/dirb/common.txt  –wildcard
```

Hide Process of Extracting
----

Using the -z option covers the process of obtaining sub-domains names while making brute force attacks.
```
gobuster dns -d example.org -t 100 -w /usr/share/wordlists/dirb/common.txt -z –wildcard
```

Extracting CNAME Records
----

Using the –cn option enables the CNAME Records parameter of the obtained sub-domains and their CNAME records.
```
gobuster dns -d example.org -t 100 -w /usr/share/wordlists/dirb/common.txt -c –wildcard
```

Proxy URL
----

Using the –p option allows proxy URL to be used for all requests; by default, it works on port 1080. As you can see, on examining the victim’s network IP in the web browser, it put up an “Access forbidden error”, which means this web page is operating backwards by some proxy.
```
gobuster dir -p ‘https://18.172.30:3128’ -u ‘http://18.192.172.30/’ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt –wildcard
```

Example :
----

Now that everything is set up and installed, we’re ready to go and use Gobuster. Let’s run it against our victim with the default parameters.
```
Target for Scanning : https://testphp.vulnweb.com
```
