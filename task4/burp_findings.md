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

---
## **Steps to Capture and Attack Login Requests Using Burp Suite**  

### **1. Set Up FoxyProxy** (for easy proxy switching)  
- Install **FoxyProxy** in your browser.  
- Configure it to use **Burp's Proxy** (`127.0.0.1:8080`).  
- Enable **FoxyProxy** to route traffic through Burp.  

### **2. Capture Login Requests**  
- Open **Burp Suite** and ensure **Intercept** is **ON** (`Proxy → Intercept`).  
- Go to the **target site** and enter **any username and password** on the login page.  
- **Burp captures the request** before it reaches the server.  

### **3. Analyze the Captured Request**  
- Navigate to **Proxy → HTTP history**.  
- Locate the request and look for **username and password fields**.  
- Send the request to **Intruder** for further testing.  

### **4. Configure Intruder for Brute Force Attack**  

#### **Select the Attack Type**  
- Choose **"Cluster Bomb"** (so Burp tests each username with each password).
- 
#### **Set Payload Positions**  
- In Burp Suite’s **Intruder** module, set the **Payload Positions**.  
- Replace the **username and password** with **placeholders** (Click **"Add §"**).  
[example setting username payload](https://github.com/deepthiii33/futureintern_projects/blob/main/setting%20username%20payload..png)

#### **Set Payloads**  
- **Payload Set [1] (Usernames)**:  
  - Select **"Simple List"** as the payload type.  
  - Load a **wordlist of usernames** or manually enter **common usernames**.  
- **Payload Set [2] (Passwords)**:  
  - Same process as **Payload Set [1]**, but this time enter or load passwords.  

### **5. Start the Attack**  
- Click **Start Attack** in Burp’s **Intruder**.  

### **6. Identify Valid Credentials**  
- Monitor **HTTP Response Codes** and **Content Length**.  
- A **different response length** may indicate a **successful login**.  


  ## Once the attack is done, look at the length of responses:

* Failed logins might return a consistent response length (e.g., 302 Redirect or Invalid Login message).
* Successful logins will have different response lengths or status codes (200 OK)








