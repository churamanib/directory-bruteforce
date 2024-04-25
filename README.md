# directory-bruteforce
directory Bruteforcing Attack Any Web Page 
---

if you want to use another tool click below link
<bir/>
click link [here](https://github.com/churamanib/directory-scanning.git).

<h4/>///////////////////////////////////////////////////////////////////////////////////////////////<h4/>
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

<h4/>///////////////////////////////////////////////////////////////////////////////////////////////<h4/>
<br/>
<br/>
 
Installation of Ffuf Tool on Kali Linux OS
----

Step 1: If you have downloaded Golang in your system, verify the installation by checking the version of Golang, use the following command.
```
go version
```

Get the Ffuf repository or clone the Ffuf tool from GitHub, use the following command.
```
sudo GO111MODULE=on go get -u github.com/ffuf/ffuf
```
Check the version of the Ffuf tool using the following command.
```
ffuf -V
```
Check the help menu page to get a better understanding of the Ffuf tool, use the following command.
```
ffuf -h
```

Configuration files
----

When the execution of the ffuf tool is started the tool firstly checks its default configuration file exits or not. Mostly the path of the configuration file is at ~/.ffufrc /$HOME/.ffufrc or can be at /home/gaurav/.ffufrc. In Windows OS this path can vary and mostly it can be at %USERPROFILE%\.ffufrc. There are configuration options provided on the terminal that override the ones loaded from the ~/.ffufrc file. For example, If you wish to use a bunch of configuration files for various scenarios, then you can define the configuration file path by using the -config tag which takes the file path to the configuration file as its parameter.

Working with Ffuf Tool on Kali Linux OS
----

Typical directory discovery
```
ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u https://example.org/FUZZ
```

Virtual host discovery (without DNS records)
----

In this example, We are filtering out VHOST default port 4242 specified in the -fs tag.
```
ffuf -w /usr/share/wordlists/vhost.txt -u https://example.org -H “Host: FUZZ” -fs 4242
```
```
ffuf -w /usr/share/dirbuster/wordlists/directory-list-1.0.txt -u http://megacorp.com/FUZZ -fc 404 | tee recon/ffuf_initial_directory.log
```

GET parameter fuzzing
----

In this example, We are using the GET method for fuzzing the directories.
```
ffuf -w /usr/share/wordlists/parameters.txt -u http://testphp.vulnweb.com/search.php?FUZZ=test_value -fs 4242
```

Maximum execution time
----

In this example, We are specifying the maximum request time. We have used -maxtime tag for specifying the time.
```
ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u https://example.org/FUZZ -maxtime 60
```

POST Data Fuzzing
---

In this example, We are using the POST method for fuzzing the directories.
```
ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -X POST -d “username=admin\&password=FUZZ” -u https://testphp.vulnweb.com/login.php -fc 401
```

Using an external mutator to produce test cases
----

In this example, We’ll fuzz JSON data that’s sent over POST. Radamsa s used as the mutator.
```
ffuf –input-cmd ‘radamsa –seed $FFUF_NUM example1.txt example2.txt’ -H “Content-Type: application/json” -X POST -u https://testphp.vulnweb.com/ -mc all -fc 400
```

<h4/>///////////////////////////////////////////////////////////////////////////////////////////////<h4/>
<br/>
<br/

ntroduction to Dirb – Kali Linux
----

Dirb is an online directory scanner that searches web servers for hidden files, directories, and pages. It is a free and open-source utility included in the Kali Linux distribution, a popular operating system for penetration testing and ethical hacking. Dirb may be used to detect typical web server folders and files, such as admin pages, backup files, and configuration files. It operates by sending HTTP queries to the server and analyzing the answers to identify the existence of a file or directory.


Working
----

It features an internal word list file with roughly 4000 words for brute force attacks. There are many updated wordlists accessible on the internet that may be utilized as well. Dirb scans every directory or object of a website or server for the terms in its wordlist. There might be an admin panel or a subfolder that is under assault. The trick is to locate the things, which are usually hidden.

Installation of Dirb on Kali Linux
----

Generally, Dirb is pre-installed in Kali Linux but in case you are using some different Linux distro other than Kali Linux then use the following command in the terminal (Command Line Interface):
```
sudo apt-get install dirb
```
After using the above command, the output will look similar to as shown in the below screenshot.
```
dirb
```
The output will contain the version information and the help menu.

Usage of Dirb Scanning single domain
----

Once installed, you can start using Dirb by opening a terminal window and typing the following command:
```
dirb http://example.com
```
At the place of http://example.com, you can use the URL (Uniform Resource Locator) of your choice of target. With its default wordlist, it will start brute forcing directories with around 4600 words.

If you want to scan a target with a different wordlist, then it can be done easily using the following command:
----

You can also specify the path of the wordlist instead of the direct filename in case you are in a different directory.
```
dirb http://www.example.com -w wordlist.txt
```

Using multiple wordlists
---

The usual wordlist_files common.txt is used by the aforementioned attack, but we are able to alter this word list and can choose a different wordlist for directory traversal. To examine all of the accessible wordlists, you must take the following route.
```
cd /usr/share/wordlists/dirb && ls -la
cd /usr/share/wordlists/dirb/vulns && ls -la
```

 Default Working
 ----

 By default, Dirb uses common.txt as a wordlist which we can find in below mentioned directory.
 ```
dirb http://www.example.com -w /usr/share/wordlists/dirb
```
And there’s no need to mention this default wordlist while using Dirb in default mode. Dirb can be used in default mode by using the below snippet:
```
dirb http://example.com
```

Saving Output to a file
----

We save the result of the dirb scan onto a file for the purpose of record management, improved reading, and future references. To do this, we’ll use the dirb scan option -o, which allows us to save the results as a text file.
This will simply create a new file output.txt and will save the results of the scan in it.
```
dirb http://example.com -o result.txt
```
 

As the -o switch is used, the output will get saved in the results.txt file. Let’s check on that file:
----

```
cat result.txt
```

Limiting enumeration with specific extensions
----

The -X option of the dirb scan can be used in a variety of circumstances where we need to retrieve the directories on the target server that have a particular suffix. This parameter takes the file extension name and then scans the target server or computer for files with the specified extension.
```
dirb http://example.com -X .php
```

 Ignoring specific status codes
 ----

The Status-Code element is a three-digit integer whose first digit designates the answer class and who’s last two digits serve no classification purpose. As shown below, we are using the -N option on code 302 in this assault. This can be achieved by using a flag -N with desired value to ignore the status code.
```
dirb http://example.com -N 302
```

Speed Delaying
----

When working in various situations, there are some environments that we encounter that cannot manage the flood caused by the dirb scan; it is crucial that we postpone the scan for a while in these environments. Using the dirb scan’s -z option makes this simple to accomplish. The duration is given in milliseconds for this parameter. We have given dirb a 100-second delay, just as in the sample we’ve provided.
```
dirb://example.com -z 100
```
As mentioned, it will delay by 100 milliseconds.

Without recursiveness
----

By default, the dirb search traverses all folders. It entails scanning a path and then moving around within it to look for additional subcategories. However, we configured the dirb to not search recursively in some circumstances where there is not enough time. The -r option can be used to accomplish this.
```
dirb http://example.com -r
```

Showing non-existing pages
----

An HTTP response number of 404 indicates that a website’s server was unable to locate the page you were attempting to access. Individual websites frequently alter the 404 Not Found error notices. In some cases, we also need to locate the 404 sites, which dirb by default ignores. We will use the -v option to locate those sites.
It will show the output in a verbose mode which means it will show all the requests that dirb is sending to the target web.
```
dirb http://example.com -v
```

HTTP AUTHORIZATION (-u user: pass)
----

The 401-status code and WWW-Authenticate answer header are the foundation of all HTTP authentication/authentication methods. Basic HTTP security methods are the most popular. User name and password are sent by the client in base64-encoded, plaintext form.

So, using dirb, we used the instruction below to get around this type of authentication:
```
dirb http://testphp.vulnweb.com/login.php -u test:test
```
The outcome is that the target URL displays Status-code 200 for the test: test and authorized identity.

Custom User-Agent
----

Scanning a website using a custom user-agent:
```
dirb http://www.example.com -a “Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36 Edge/16.16299”
```

This will send requests using the custom user-agent which is provided in the instruction. For more information regarding user agents, read this article user-agents.

Conclusion
----

Overall, Dirb is a strong tool for locating hidden directories and files on web servers. Yet, it is critical to utilize it ethically and with the website owner’s consent. Unethical usage of Dirb may result in legal ramifications. The primary goal is to support expert online application monitoring. Particularly in testing that involves security. It plugs some gaps that conventional online vulnerability analyzers do not. Dirb searches for particular web items that other general CGI analyzers are unable to search for. It neither searches for flaws nor looks for potentially vulnerable online material.
