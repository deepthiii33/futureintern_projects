# INTRODUCTION

## What is Wireshark
Wireshark is a free and open-source network packet analyzer that allows users to capture and view data traveling through a network in real time. It is available for Windows, Linux, and UNIX. Wireshark can capture live network traffic, open and analyze packet capture files from tools like tcpdump, and display detailed protocol information for each packet. It also supports saving and exporting packet data in various formats. Users can apply filters to focus on specific packets, making network analysis more efficient and effective.

> Can get detalied information from it's official site **"https://www.wireshark.org/"**

----------

## Wireshark Setup & Usage

 - In most Kali Linux installations, Wireshark comes pre-installed
 - if not you can install using  **sudo apt update && sudo apt install wireshark -y**  and run with **sudo wireshark** command
 - In linux we can run wireshark with **"wireshark filename"**
 - Example : **wireshark capture.pcapng** , if we capture the network traffic and save as capture.pcapng ,Wireshark supports both *.pcap and *.pcapng files

> For windows wireshark can be downloaded from it's offcial site : **https://www.wireshark.org/download.html**

   **Here , i'm using kali linux for wireshark , not windows**

--------------

## About .pcapng  and .pcap files

- *.pcap (Packet Capture) → Older format, stores captured network packets.
- *.pcapng (Packet Capture Next Generation) → Newer format, supports multiple interfaces, metadata, and better compression.

## How to open a pcapng file through wireshrak in linux 

 ### **Method 1: Using GUI**  
1. Open Wireshark:  command used "**wireshark &**
2. Click **"File" → "Open"**.  
3. Navigate to your ".pcapng" file and select it.  
4. Click **"Open"** to start analyzing the packet data.  

 ### **Method 2: Using Terminal**  
- If you already know the file location, open it directly from the terminal:  **wireshark /path/to/file.pcapng**

![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots/wireshark_through_terminal.png)
  
 ### **Method 3: Using TShark (CLI Alternative to Wireshark)**  
- If you prefer the **command line**, use **TShark**:  tshark -r /path/to/file.pcapng
- This prints the packet details in the terminal  

![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots//tshark.png)

Can get more usage of tshark through the command **tshark --help**

-------------

## Filters in wireshark 
  - **Wireshark has two types of filters:**
   1. Capture Filters → Applied before capturing packets.
      -  Example:tcp port 80  --> (Captures only TCP traffic on port 80.)
        [example](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots//wireshar_capture_filter.png)

   2. Display Filters → Applied after capturing packets to analyze specific data.
      - Example:http ---> (Shows only HTTP packets.)

 ![](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots//wireshark%20filters.jpg)

-----------

## Wireshark Features (Packet Capture Details)

When capturing packets in Wireshark, , the interface provides multiple columns displaying useful information about each packet:

### Main Wireshark Columns

- No.	---> Packet number in the capture session.
- Time ---> 	Timestamp when the packet was captured.
- Source (Src) --->	The sender's IP or MAC address.
- Destination (Dst)	---> The receiver's IP or MAC address.
- Protocol ---> 	The protocol used (TCP, UDP, HTTP, DNS, etc.).
- Length --->	The size of the packet in bytes.
- Info	---> A summary of the packet details (e.g., HTTP request type, DNS query, etc.).

### Other Features in Wireshark

- Packet Details Pane --->  Shows deep protocol-level breakdown of a selected packet.
- Packet List Pane ---> Displays all captured packets with details.
- Packet Bytes Pane ---> Displays raw data in hexadecimal and ASCII format.
- Color Coding ---> Highlights packets based on protocol for easy identification.
- Filters ---> Allows searching for specific packets (e.g., http, ip.addr == 192.168.1.1).
- Follow Stream ---> Helps analyze a full conversation (e.g., TCP, HTTP request-response).
- Export Data ---> Save captured packets in various formats (.pcap, .txt, etc.).

  [example](https://github.com/deepthiii33/futureintern_projects/blob/main/task2/screenshots//captured_traffic.png)

  ------




  







   

  






