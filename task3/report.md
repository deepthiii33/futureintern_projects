#  Wireshark Packet Analysis Report

### Packet Capture & Filtering

- The target site for this analysis is: **[http://testphp.vulnweb.com](http://testphp.vulnweb.com)**.  
- Open Wireshark and select the appropriate network interface (**eg: eth0, wlan0**).
  - In this case, I chose **eth0** as my interface.
- Start exploring the target site (eg: login page,Profile,Cart,Guestbook,...)
- Click Start Capture to begin capturing packets.
- Stop the capture once enough network packets have been collected.
  
  - [**Target site and Wireshark**](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/target_wireshark.png)
   - **Captured Packets:**![View Example](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/captured_traffic.png)

###   Applying Filters

- You can apply filters such as http, http.request.method == "POST", ip, ip.src ==, dns, and others based on our needs.
   - **HTTP Filter:** ![View Example](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/http_filter.png)
- In this screenshot, I have applied an HTTP filter in Wireshark to capture and analyze HTTP requests and responses.

  ### First Steps
  - I checked my IP address using the ifconfig command.
  - I verified the target website’s reachability using the ping command.
    
  #### Key Observations from captured packets
     1. GET Request (Packet 12)
        - The source IP (192.168.1.10) sends a GET /login.php request to destination IP (44.228.249.3).
        - The Host is testphp.vulnweb.com, a vulnerable testing website.
        - The User-Agent reveals that the request was made using Mozilla Firefox on Linux.
        - The request contains an HTTP Cookie, which may indicate a logged-in session.

   2. POST Request (Packet 52 & 93)
      - The source IP (192.168.1.10) sends a POST /userinfo.php request to the same target.
      - The Content-Type is application/x-www-form-urlencoded, which means form data (possibly login credentials) is being sent.
      - The request body may contain usernames, passwords, or other sensitive information.


  ### Next Step
-  Right-click on a POST request and select Follow → HTTP Stream to view the full login details
- Or else, use  filter like : http.request.method == "POST"
    - [**Example**](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/req_method_post.png)

- From there, we can get the **username, password, headers, and all details,Sensitive Information**(If a site is vulnerable, data leaks might appear in responses) of the HTTP request and response.
   - [Example](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/http_stream.png)
 
#### key observation from HTTP stream
  1. Captured Login Credentials:
      - The POST request sent username (uname=test) and password (pass=test) in plaintext.
      - This means the website is not using HTTPS, making credentials vulnerable to interception.
   2. HTTP Headers:
      - Origin & Referer: Shows the request came from http://testphp.vulnweb.com/login.php.
      - Cookie: Captured session cookie (login=test%2Ftest), which can be used for session hijacking.
   3. Server Response:
      - The server responds with HTTP/1.1 200 OK, meaning the login was successful.
      - The response contains Set-Cookie, which is used to maintain the user session.

 * Sensitive information like usernames and passwords can be exposed if a website doesn’t use encryption (HTTPS).
 * Attackers can steal session cookies and gain unauthorized access to accounts.


 
      


       













  











