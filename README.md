# CodeAlpha_Project_Task3
## Network-Based Intrusion Detection System (NIDS)
  **Network Intrusion Detection System (NIDS)** is a security solution designed to monitor and analyze network traffic for signs of malicious activities or policy violations. It continuously monitors network traffic for suspicious or abnormal behavior. It can analyze data packets transmitted over the network to detect patterns indicative of potential security threats. It uses predefined rules or behavioral analysis to identify known attack patterns and anomalies. It can detect various types of threats, including unauthorized access, denial-of-service attacks, and malicious payloads. When NIDS identifies suspicious activity, it generates alerts to notify administrators of potential threats. This helps in responding quickly to security incidents and mitigating potential damage.

This project demonstrates the setup of a network-based intrusion detection system using Snort to monitor and analyze network traffic for signs of suspicious activity. It includes installation instructions, configuration steps, and how to create and enable custom rules.

- **Tool Used:** Snort
- **Features:** 
  - Real-time network traffic analysis
  - Customizable rules for detecting suspicious activities
  - Logging and alerting mechanisms
 
    
### Prerequisites

- A Linux-based operating system (e.g., Kali)
- Administrative access (sudo privileges)
- Basic knowledge of network security concepts
- Metasploitable

### Installation

**Step 1**: Start Your Kali Linux

**Step 2**: Start your Metasploitable

**Step 3**: Go to Kali linux root terminal and install the dependencies mentioned below
   
    sudo apt-get install -y build-essential autotools-dev libdumbnet-dev libluajit-5.1-dev libpcap-dev zlib1g-dev pkg-config libhwloc-dev cmake liblzma-dev openssl libssl-dev cpputest libsqlite3-dev libtool uuid-dev git autoconf bison flex libcmocka-dev libnetfilter-queue-dev libunwind-dev libmnl-dev ethtool libjemalloc-dev

![Screenshot 2024-08-11 113940](https://github.com/user-attachments/assets/992d1c87-a485-4833-9a26-044118004aa1)

### Explanation of Dependencies: 
  
   - **build-essential**: Essential development tools including the GCC compiler and make.
  
   - **autotools-dev**: Tools for generating configuration scripts for software.
   
   - **libdumbnet-dev**: Provides low-level networking routines.
   
   - **libluajit-5.1-dev**: LuaJIT for Lua scripting.
   
   - **libpcap-dev**: Network packet capture library.
   
   - **zlib1g-dev**: Compression library.
   
   - **pkg-config**: Helper tool for compiling applications and libraries.
   
   - **libhwloc-dev**: Abstraction library for hierarchical architectures.
   
   - **cmake**: Cross-platform build automation tool.
   
   - **liblzma-dev**: XZ and LZMA compression library.
   
   - **openssl, libssl-dev**: Secure communication libraries.
   
   - **cpputest**: C/C++ test framework.
   
   - **libsqlite3-dev**: SQLite 3 library for database management.
   
   - **libtool**: Generic library support script.
   
   - **uuid-dev**: Library for generating unique identifiers.
   
   - **git**: Version control system.
   
   - **autoconf**: Tool for generating configuration scripts.
   
   - **bison, flex**: Tools for generating parsers and lexical analyzers.
   
   - **libcmocka-dev**: Unit testing library. 
   
   - **libnetfilter-queue-dev**: Handling packets queued by the kernel packet filter.
   
   - **libunwind-dev**: Library for determining the call-chain of a program.
   
   - **libmnl-dev**: Minimalistic user-space library oriented to Netlink developers.
   
   - **ethtool**: Utility for examining and tuning network interface settings.
   
   - **libjemalloc-dev**: Efficient memory allocator library.



**Step 4**: Run the following commands
  apt-get update 
  apt-get install snort

![Screenshot 2024-08-11 114104](https://github.com/user-attachments/assets/0785c861-0d21-4d62-8841-92802d603eaf)


### Snort Configuration

**Step 1**: Find the location of configuration file.
 You will find configuration file at below locations (You have to find the location of configuration file.)
     
      **/etc/snort/snort.lua** 
  or   
     
     **/etc/snort/lua/snort.lua**
  or   
    
    **/etc/snort/snort/lua/snort.lua**

![Screenshot 2024-08-11 114336](https://github.com/user-attachments/assets/8e943674-8d15-4495-8641-84f85a72ea3c)
![Screenshot 2024-08-11 114413](https://github.com/user-attachments/assets/778c3b8a-9d84-4bc1-b8c5-01cfa8c69535)

**Step 2**: Open the file by using following command:
    
    mousepad snort.lua
**Step 3**: Make changes as mentioned in below screenshort:

 Here you have to add range of IP address in HOME_NET along with the CIDR notation
![Screenshot 2024-08-11 114508](https://github.com/user-attachments/assets/e3d2a8c4-a671-4fbb-b21a-f40a4a1258c8)

 Add the path of local.rules file as mentioned below.
 
![Screenshot 2024-08-11 114538](https://github.com/user-attachments/assets/b75602f3-6aa0-4e64-ad29-ddf732484502)

**Step 4**: Go to rules directory by using following commands and create a local.rules in the rules directory.
    
![Screenshot 2024-08-11 114826](https://github.com/user-attachments/assets/ed44d7e5-ff8d-4a45-8c31-c962a2510f0d)

**Step 5**: Open the file and add the following rule in it.

    alert icmp any any -> [ip address of host machine] any (msg:"DANGER ICMP has detected on host machine"; sid:1000003; )
    
![Screenshot 2024-08-11 114938](https://github.com/user-attachments/assets/db1eb7e7-8897-4ba8-a725-9a4e0f6f1c5a)

### Running Snort
**Step 1**: Check your network interface by using below command:
      
      ifconfig
  (In my case its eth0 that's why I will use eth0 in the below command)
**Step 2**: Run snort by using following command in the root terminal
     
     snort -A alert_fast -c /etc/snort/snort3/lua/snort.lua -i eth0
  ![Screenshot 2024-08-11 115440](https://github.com/user-attachments/assets/1552b1e4-596b-477f-a195-147755a989b3)
  ![Screenshot 2024-08-11 115504](https://github.com/user-attachments/assets/aeaf30ef-e96e-4f30-8733-faea03fd3d7a)

**Step 3**: Go to metasploitable and ping your host machine 
 ![Screenshot 2024-08-11 120251](https://github.com/user-attachments/assets/5bef55ca-2be2-4d47-a57c-afd013b954fa)

**Step 4**: Go to the kali terminal and observe the alert generated in the snort console.
![Screenshot 2024-08-11 120329](https://github.com/user-attachments/assets/782d5101-f587-468b-aa15-ae40f2d5381c)

### Conclusion 
This **Network Intrusion Detection System (NIDS)** project demonstrates the implementation and configuration of Snort to effectively monitor and analyze network traffic for potential security threats. By setting up custom detection rules and utilizing real-time alerting mechanisms, the system effectively identifies and mitigates potential threats. This project demonstrates the importance of robust network monitoring solutions and offers a solid foundation for further exploration and improvement in the field of cybersecurity.


 
 
