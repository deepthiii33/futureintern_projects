## John the Ripper – Cracking Password Hashes

- John the Ripper is a powerful tool used for cracking password hashes. It helps in testing password security by attempting to recover the original password from a hash using brute force and wordlist attacks.
- It  is designed to crack hashed passwords, not plaintext passwords.If a password is already in plaintext (like capturing credentials with Burp Suite), John is not needed. You already have the password!
  However, if you have a hashed password, John can help crack it by trying different passwords from a wordlist
- So, John the Ripper works only when passwords are stored in hashed form and needs to be cracked

   ## Steps to Use John the Ripper:
  
   # 1.  Create a Hash (Example: MD5)
     
      echo -n "password123" | openssl dgst -md5 | awk '{print $2}' > password123_hash.txt

  -  echo -n "password123" --->  Prints "password123" without adding a newline (-n prevents a new line).This is the password we want to hash.
  -  | openssl dgst -md5   --->  Pipes (|) the password into openssl. dgst -md5 tells OpenSSL to create an MD5 hash of the password.
  -  | awk '{print $2}'    --->  Extracts only the hash value from OpenSSL’s output.
  -  password123_hash.txt  --->  Saves the extracted hash into a file called password123_hash.txt

  -  The output may be like this , when we use cat command , cat <filename>
  -  cat password123_hash.txt   : 482c811da5d5b4bc6d497ffa98491e38


   #  2. Run John the Ripper on the Hash

       john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt password123_hash.txt

  - john ---> Runs John the Ripper, the password-cracking tool
  - --format=raw-md5 ---> Specifies that we are cracking an MD5 hash (since passwords can be hashed in different formats).
  - --wordlist=/usr/share/wordlists/rockyou.txt ---> Uses the RockYou wordlist, a common list of passwords, to try and crack the hash.You can replace it with your own wordlist if needed
  - password123_hash.txt ---> The file containing the hashed password that we want to crack.

[example of using john the ripper md5 hashed password](https://github.com/deepthiii33/futureintern_projects/blob/main/task4/john_ripper_md5.png)


If we have a hashed passowrd with us we can do the  "run john the ripper on the hash" command and get the password of the hash value. Suppose we don't know type of hash value(md5 , sha1 , sha256,...) , we can use online hash indentifiers or 
hashid and hash idenifier command in kali 
- To use ;  hashid <hashvalue> --->  will get the hash type
- we must know the hash type to find the hash value password
- This is a basic example of md5 , like this we can do for sha1 or any type of hash

   # Below is an example for sha1 hash type

      [sha1 hash type pass cracking using john the ripper](https://github.com/deepthiii33/futureintern_projects/blob/main/task4/john_sha1.png)

  - like this we can hashcat tool for same process

## hashcat - cracking password hashes

- Hashcat is a powerful password-cracking tool used to recover passwords from hashed values.
- It supports various hashing algorithms like MD5, SHA-1, SHA-256, etc

   ## steps to use hashcat:
  
     # 1. Create a Hash value same as we do in john the ripper (here i use sha1 algorithm )
         echo -n "passwords123" | openssl dgst -sha1 | awk '{print $2}' > hashvalue.txt

     # 2. Run John the Ripper command
           hashcat -m 0 -a 0 hashvalue.txt /usr/share/wordlists/rockyou.txt

    - hashcat ---> Runs Hashcat, a powerful password-cracking tool.
    - -m 0 ---> Specifies the hash type .  0 = MD5 (Other hash types have different numbers, e.g., SHA-1 is 100, SHA-256 is 1400)
    - -a  ---> Specifies the attack mode. 0 = Dictionary attack (tries passwords from a list).
    - hashvalue.txt ---> The file that contains the hashed password we want to crack.
    - /usr/share/wordlists/rockyou.txt ---> The wordlist Hashcat will use to try and crack the hash.
 
  [example for hashcat](https://github.com/deepthiii33/futureintern_projects/blob/main/task4/hashcat.png)

  * Hashcat takes the hash from hash.txt.
  * It compares it with hashes of passwords from rockyou.txt.
  * If a match is found, it displays the cracked password.

 ---------   

 * like this , if we obtain a **hashed password**, we can crack it using **Hashcat** or **John the Ripper**. However, if the password is transmitted in **plain text**, we can capture and exploit it using **Burp Suite** or **Hydra**.
 * 

  






  
  

    
      
   

  











