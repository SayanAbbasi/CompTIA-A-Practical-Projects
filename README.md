# CompTIA A+ & Network Administration Practical Portfolio

Welcome to my practical IT and networking documentation repository. This portfolio demonstrates hands-on lab projects, diagnostic procedures, and security setups completed during my Network Administrator program.

---

## Lab Project 1: Basic Network Diagnostics & Baseline Configuration

### Objective
To perform fundamental network diagnostic procedures, identify local IP settings, test connectivity paths, and document SOHO router security standards based on CompTIA A+ Core 1 & Core 2 specifications.

### Tools & Environment Used
- **OS:** Windows 10/11 Command Prompt (CMD)
- **Networking Commands:** `ipconfig`, `ping`, `tracert`, `nslookup`
- **Environment:** SOHO Router Interface

---

### Step-by-Step Execution & Documentation

#### Step 1: Local Network Configuration Discovery
Executing `ipconfig /all` to retrieve local IPv4 address, Subnet Mask, Default Gateway, and MAC address.

```cmd
ipconfig /all

Windows IP Configuration

   Host Name . . . . . . . . . . . . : Sayan
   Primary Dns Suffix  . . . . . . . :
   Node Type . . . . . . . . . . . . : Hybrid
   IP Routing Enabled. . . . . . . . : No
   WINS Proxy Enabled. . . . . . . . : No

Wireless LAN adapter Local Area Connection* 1:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :
   Description . . . . . . . . . . . : Microsoft Wi-Fi Direct Virtual Adapter
   Physical Address. . . . . . . . . : 16-5A-41-C3-F6-93
   DHCP Enabled. . . . . . . . . . . : Yes
   Autoconfiguration Enabled . . . . : Yes

Wireless LAN adapter Local Area Connection* 2:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :
   Description . . . . . . . . . . . : Microsoft Wi-Fi Direct Virtual Adapter #2
   Physical Address. . . . . . . . . : 1A-5A-41-C3-F6-93
   DHCP Enabled. . . . . . . . . . . : No
   Autoconfiguration Enabled . . . . : Yes

Wireless LAN adapter Wi-Fi:

   Connection-specific DNS Suffix  . :
   Description . . . . . . . . . . . : Realtek RTL8852BE WiFi 6 802.11ax PCIe Adapter
   Physical Address. . . . . . . . . : 14-5A-41-C3-F6-93
   DHCP Enabled. . . . . . . . . . . : Yes
   Autoconfiguration Enabled . . . . : Yes
   Link-local IPv6 Address . . . . . : fe80::16c0:775a:f498:5566%10(Preferred)
   IPv4 Address. . . . . . . . . . . : 192.168.68.54(Preferred)
   Subnet Mask . . . . . . . . . . . : 255.255.252.0
   Lease Obtained. . . . . . . . . . : November 12, 2026 9:19:45 AM
   Lease Expires . . . . . . . . . . : November 12, 2026 9:56:50 PM
   Default Gateway . . . . . . . . . : fe80::7ef1:7eff:fea6:d581%10
                                       192.168.68.1
   DHCP Server . . . . . . . . . . . : 192.168.68.1
   DHCPv6 IAID . . . . . . . . . . . : 118774337
   DHCPv6 Client DUID. . . . . . . . : 00-01-01-00-31-A5-98-D3-00-E0-4C-68-0C-22
   DNS Servers . . . . . . . . . . . : 8.8.8.8
                                       8.8.4.4
   NetBIOS over Tcpip. . . . . . . . : Enabled

Ethernet adapter Bluetooth Network Connection:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :
   Description . . . . . . . . . . . : Bluetooth Device (Personal Area Network)
   Physical Address. . . . . . . . . : 14-5A-41-C3-F6-94
   DHCP Enabled. . . . . . . . . . . : Yes
   Autoconfiguration Enabled . . . . : Yes
```

#### Step 2: Connectivity Testing & Latency Verification

Verifying external network reachability and packet stability by pinging Google Public DNS (`8.8.8.8`).

```cmd
ping
    C:\Users\abbas>ping 8.8.8.8

    Pinging 8.8.8.8 with 32 bytes of data:
    Reply from 8.8.8.8: bytes=32 time=16ms TTL=119
    Reply from 8.8.8.8: bytes=32 time=13ms TTL=119
    Reply from 8.8.8.8: bytes=32 time=20ms TTL=119
    Reply from 8.8.8.8: bytes=32 time=13ms TTL=119

    Ping statistics for 8.8.8.8:
        Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
    Approximate round trip times in milli-seconds:
        Minimum = 13ms, Maximum = 20ms, Average = 15ms
```
#### Step 3: Route Tracing & Path Analysis
Tracing the network path and hops from my local system to Google Public DNS (8.8.8.8) to analyze routing efficiency.

```cmd
tracert 8.8.8.8
   C:\Users\abbas>tracert 8.8.8.8
   
   Tracing route to dns.google [8.8.8.8]
   over a maximum of 30 hops:
   
     1    12 ms    17 ms     6 ms  192.168.68.1
     2     *        *        *     Request timed out.
     3    27 ms    14 ms    14 ms  ae21-20.tor-cor-bdr04.distributel.net [206.80.255.14]
     4    16 ms    12 ms    11 ms  74.125.32.42
     5    13 ms    11 ms    12 ms  192.178.99.39
     6    18 ms    12 ms    10 ms  216.239.50.119
     7    15 ms    16 ms    12 ms  dns.google [8.8.8.8]

      Trace complete.
```
#### Step 4: DNS Resolution & Lookup Verification
Querying Domain Name System (DNS) records to verify name resolution functionality.

```cmd
nslookup google.com
C:\Users\abbas>nslookup google.com
Server:  dns.google
Address:  8.8.8.8

Non-authoritative answer:
Name:    google.com
Addresses:  2607:f8b0:4023:1804::8a
          2607:f8b0:4023:1804::64
          2607:f8b0:4023:1804::71
          2607:f8b0:4023:1804::65
          142.250.137.102
          142.250.137.138
          142.250.137.100
          142.250.137.101
          142.250.137.139
          142.250.137.113
```
