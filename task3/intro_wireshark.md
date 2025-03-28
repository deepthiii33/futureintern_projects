# INTRODUCTION

## What is Wireshark
 -  Wireshark is a network packet analyzer. A network packet analyzer presents captured packet data in as much detail as possible.
 -  Wireshark is available for free, is open source, and is one of the best packet analyzers available today
 -  Available for  Windows , Linux and UNIX
 -  Capture live network packets , can  open and analyze packet capture files from Wireshark, tcpdump, etc.
 -  It can display detailed protocol information for each packet.
 -  We can Save and export packet data in different formats.
 -  Apply filters to analyze specific packets efficiently

 -  can get detalied information from it's official site https://www.wireshark.org/

## Downloading and using Wireshark

 - In most Kali Linux installations, Wireshark comes pre-installed
 - if not you can install using  **sudo apt update && sudo apt install wireshark -y**  and run with **sudo wireshark** command
 - In linux we can run wireshark with **"wireshark filename"**
 - Example : **wireshark capture.pcapng** , if we capture the network traffic and save as capture.pcapng ,Wireshark supports both *.pcap and *.pcapng files

 - For windows wireshark can be downloaded from it's offcial site : https://www.wireshark.org/download.html

## About .pcapng  and .pcap files

- *.pcap (Packet Capture) → Older format, stores captured network packets.
- *.pcapng (Packet Capture Next Generation) → Newer format, supports multiple interfaces, metadata, and better compression.

# Filters in wireshark 
  - **Wireshark has two types of filters:**
   1. Capture Filters → Applied before capturing packets.
      -  Example:tcp port 80  --> (Captures only TCP traffic on port 80.)
      [example]()

   2. Display Filters → Applied after capturing packets to analyze specific data.
      - Example:http ---> (Shows only HTTP packets.)

[Some basic filters in Wireshark]







   

  






