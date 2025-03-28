# INTRODUCTION

## What is Wireshark
 -  Wireshark is a network packet analyzer. A network packet analyzer presents captured packet data in as much detail as possible.
 -  Wireshark is available for free, is open source, and is one of the best packet analyzers available today
 -  Available for  Windows , Linux and UNIX
 -  Capture live network packets , can  open and analyze packet capture files from Wireshark, tcpdump, etc.
 -  It can display detailed protocol information for each packet.
 -  We can Save and export packet data in different formats.
 -  Apply filters to analyze specific packets efficiently

 -  can get detalied information from it's official site **"https://www.wireshark.org/"**

## Downloading and using Wireshark

 - In most Kali Linux installations, Wireshark comes pre-installed
 - if not you can install using  **sudo apt update && sudo apt install wireshark -y**  and run with **sudo wireshark** command
 - In linux we can run wireshark with **"wireshark filename"**
 - Example : **wireshark capture.pcapng** , if we capture the network traffic and save as capture.pcapng ,Wireshark supports both *.pcap and *.pcapng files

 - For windows wireshark can be downloaded from it's offcial site : https://www.wireshark.org/download.html

   **Here , i'm using kali linux for wireshark , not windows**

## About .pcapng  and .pcap files

- *.pcap (Packet Capture) → Older format, stores captured network packets.
- *.pcapng (Packet Capture Next Generation) → Newer format, supports multiple interfaces, metadata, and better compression.

# Filters in wireshark 
  - **Wireshark has two types of filters:**
   1. Capture Filters → Applied before capturing packets.
      -  Example:tcp port 80  --> (Captures only TCP traffic on port 80.)
      
  [example](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/wireshar_capture_filter.png)

   2. Display Filters → Applied after capturing packets to analyze specific data.
      - Example:http ---> (Shows only HTTP packets.)

 [Some basic filters in Wireshark](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/wireshark%20filters.jpg)


# How to open a pcapng file through wireshrak in linux 

 ## **Method 1: Using GUI**  
1. Open Wireshark:  command used "**wireshark &**
2. Click **"File" → "Open"**.  
3. Navigate to your ".pcapng" file and select it.  
4. Click **"Open"** to start analyzing the packet data.  

## **Method 2: Using Terminal**  
- If you already know the file location, open it directly from the terminal:  **wireshark /path/to/file.pcapng**
- [Example](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/wireshark_open_through_terminal.png)
  
## **Method 3: Using TShark (CLI Alternative to Wireshark)**  
- If you prefer the **command line**, use **TShark**:  tshark -r /path/to/file.pcapng
- This prints the packet details in the terminal  
[Example](https://github.com/deepthiii33/futureintern_projects/blob/main/task3/Images/tshark.png)
- Can get more usage of tshark through the command **tshark --help**









   

  






