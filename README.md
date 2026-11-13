# CompTIA A+ & Network Administration Practical Portfolio

Welcome to my practical IT and networking documentation repository. This portfolio demonstrates hands-on lab projects, diagnostic procedures, and security setups completed during my Network Administrator program.

---

## Lab Project 1: Basic Network Diagnostics & Baseline Configuration

### 🎯 Objective
To perform fundamental network diagnostic procedures, identify local IP settings, test connectivity paths, and document SOHO router security standards based on CompTIA A+ Core 1 & Core 2 specifications.

### 🛠️ Tools & Environment Used
- **OS:** Windows 10/11 Command Prompt (CMD)
- **Networking Commands:** `ipconfig`, `ping`, `tracert`, `nslookup`
- **Environment:** SOHO Router Interface

---

### 📝 Step-by-Step Execution & Documentation

#### Step 1: Local Network Configuration Discovery
Executing `ipconfig /all` to retrieve local IPv4 address, Subnet Mask, Default Gateway, and MAC address.

```cmd
ipconfig /all
Windows IP Configuration


Wireless LAN adapter Local Area Connection* 1:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Local Area Connection* 2:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Wi-Fi:

   Connection-specific DNS Suffix  . :
   Link-local IPv6 Address . . . . . : fe80::16c0:775a:f498:5566%10
   IPv4 Address. . . . . . . . . . . : 192.168.68.54
   Subnet Mask . . . . . . . . . . . : 255.255.252.0
   Default Gateway . . . . . . . . . : fe80::7ef1:7eff:fea6:d581%10
                                       192.168.68.1

Ethernet adapter Bluetooth Network Connection:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :
