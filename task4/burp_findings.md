## 🛠 Burp Suite Overview

Burp Suite is a powerful web vulnerability scanner and penetration testing tool. 
It helps security testers identify security flaws in web applications by intercepting and analyzing HTTP/S requests.

##  Key Features:
* Intercept Requests – Modify web traffic between client and server.
* Scanner – Automatically detect common vulnerabilities.
* Intruder – Perform automated attacks for security testing.
* Repeater – Manually test web requests with modifications.
* Extender – Add custom plugins to extend functionality.

## To download  burp 

Burp Suite comes pre-installed on Kali Linux by default. It is part of the standard toolset used for penetration testing and web security assessments
You can also download the latest version directly from https://portswigger.net/burp

**Our traget site:** http://testphp.vulnweb.com/login.php 
**Our Goal:** To find the username and password of the target site. *(Here, the site already has a default username and password set as "test", but we will use Burp Suite to discover the credentials as if we don’t know them.)*

## Steps

* Set Up FoxyProxy (for easy switching):
    * Install FoxyProxy in your browser -> Configure it to use Burp's Proxy (127.0.0.1:8080) -> Enable FoxyProxy to route traffic through Burp.
* Open Burp Suite and ensure Intercept is ON (Proxy → Intercept)
* Go to the target site and enter any username and password on the login page
* Burp captures the request before it reaches the server
* Analyze the request in Burp’s HTTP history (Proxy → HTTP history), Look for the username and password fields in the request
* then sent to intruder 


