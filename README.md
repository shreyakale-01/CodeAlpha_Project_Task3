# CodeAlpha_Project_Task3
## Network-Based Intrusion Detection System (NIDS)

This project demonstrates the setup of a network-based intrusion detection system using Snort. It includes installation instructions, configuration steps, and how to create and enable custom rules.

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

Step 1: Start Your Kali Linux

Step 2: Start your Metasploitable

Step 3: Go to Kali linux root terminal and install the dependencies mentioned below
   
    sudo apt-get install -y build-essential autotools-dev libdumbnet-dev libluajit-5.1-dev libpcap-dev zlib1g-dev pkg-config libhwloc-dev cmake liblzma-dev openssl libssl-dev cpputest libsqlite3-dev libtool uuid-dev git autoconf bison flex libcmocka-dev libnetfilter-queue-dev libunwind-dev libmnl-dev ethtool libjemalloc-dev

![Screenshot 2024-08-11 113940](https://github.com/user-attachments/assets/992d1c87-a485-4833-9a26-044118004aa1)

  Explanation of Dependencies: 
  
    build-essential: Essential development tools including the GCC compiler and make.
    autotools-dev: Tools for generating configuration scripts for software.
    libdumbnet-dev: Provides low-level networking routines.
    libluajit-5.1-dev: LuaJIT for Lua scripting.
    libpcap-dev: Network packet capture library.
    zlib1g-dev: Compression library.
    pkg-config: Helper tool for compiling applications and libraries.
    libhwloc-dev: Abstraction library for hierarchical architectures.
    cmake: Cross-platform build automation tool.
    liblzma-dev: XZ and LZMA compression library.
    openssl, libssl-dev: Secure communication libraries.
    cpputest: C/C++ test framework.
    libsqlite3-dev: SQLite 3 library for database management.
    libtool: Generic library support script.
    uuid-dev: Library for generating unique identifiers.
    git: Version control system.
    autoconf: Tool for generating configuration scripts.
    bison, flex: Tools for generating parsers and lexical analyzers.
    libcmocka-dev: Unit testing library. 
    libnetfilter-queue-dev: Handling packets queued by the kernel packet filter.
    libunwind-dev: Library for determining the call-chain of a program.
    libmnl-dev: Minimalistic user-space library oriented to Netlink developers.
    ethtool: Utility for examining and tuning network interface settings.
    libjemalloc-dev: Efficient memory allocator library.

Step 4: Run the following commands
  apt-get update 
  apt-get install snort

![Screenshot 2024-08-11 114104](https://github.com/user-attachments/assets/0785c861-0d21-4d62-8841-92802d603eaf)


