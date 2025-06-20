## Networking:

 **ISP**  Internet service provider → which give us internet. example : airtel, jio, BSNL.
```
    Internet theoritically diagram:
    
    
    🗄️ Servers are directly connected to the internet
    |
--------------------------INTERNET----------------------------------------         <-- Internet is like backbone wire.
                              | 
                              |
     🖥️------------------- [ ISP ]
 But User/client is not directly connected to internet, instead it is connected through ISP 

```
**Wimax :**

( Worldwide  interoperability microwave access )  **a telecommunications technology aimed at providing wireless data over long distances in a variety of ways, from point-to-point links to full mobile cellular type access**

---

**Gateway help us to connect between different network. Its an application or software or firmware. it is not a deivce, in built in routers, same as router also called protocol converter**

---
1. LAN [ local area network ] → Small Network Connect Host      Faster | cheaper

        → Same room                 Common standard use: Ethernet

        → Same Building

        → Same Campus  

1. WAN [ wide area network] → Host maybe widely dispersed     Slower | Expensive
    
    → Across Campus
    
    → Across Cities / Countries / Continent 
    

CSU / DSU → Channel service Unit/ Data service unit 

      |———>———LAN————[. CSU/DSU  ]———→——-WAN————-|

convert Data from LAN                to a WAN

---
## **Network Device**

**Hub:**

Connect computer devices together in star topology network. transfer data in every device connected to hubs [no intelligence] 

**Switch:** 

Intelligent version of Hub, contain memory element to store mac-address of every device. Good in security, Layer 2 device of OSI model.

You can tell, switch whom to send data by telling IP address & port no. 

The Spanning tree protocol:

- Allow for fault tolerance and prevent unnecessary traffic loops.
- Allow the switch to talk to each other to find if loop are happening in network.

Multi layer switch: Operate at layer 2 and 3 of OSI Model

Content switch: Can operate ay layer 4 through 7 of OSI model

**Bridge:**

Intelligent repeater contain memory device, store MAC address in RAM,  store incoming and outgoing data information

**Routers:**

Layer 3 device, Connect different network.

**NICs:**

Network Interface Card. work to convert incoming serial data into parallel data. Layer 1 and 2 device. every NICs comes with there MAC address [Hardware address]

**Repeater:**

Use wireless or wired connection. regenerate the wifi signals

**Modem:** 

Modulator and demodulator, 

Work: To convert analogy signals into binary and vice versa. we can establish internet with the help of modem

```
                                        |||         |||         |||
                         Phone         |   |       |   |       |   |
01100111100100101010010[. Modem ] ----|-----|-----|-----|-----|-----|--
                                             |   |       |   |
                                              |||         |||

actually device know                we communicate into analog pulse (Up and down)
always binary language  

Draw back: old device, low bandwidth (3000Hz) less speed,

```
Modify version of modem:

**DSL:** digital subscriber line → most used in now, best bandwidth goes upto several millions of hertz, best speed

- ADSL: Asynchronous digital subscriber line. 9Mbps( Download speed) 640 Kbps (upload speed). use telephone line to connect to internet. Most use in now days.
- SDSL: synchronous digital subscriber line

DRAWBACK: Your home should be front of ISP.

       **Increase in cable length ∝ Internet speed [ more cable length slower speed ]**

---


## TOPOLOGY
**Defination:** Topology is the physical or logical layout that tell how computers and devices connect and communicate with each other in a network.

## Types: 
1. **Star Topology**: A network where all devices are connected to a central hub or switch. An example of media type used  in star topo, is 10baseT Ethernet .
2. **Bus Topology**: A network where all devices are connected to a single central cable (bus). Media type such as 10Base5 or 10Base2 Ethernet . vampire tap
3. **Ring Topology**: A network where each device is connected to two other devices, forming a circular path. Every nodes is connected to its next node . Dual ring topology is used when you need redundancy . for ex if one of the component is fail than ring wrap itself to provide single ring functional . FDDI ( fiber distributed data transfer )  is an example of dual ring topo.
4. **Mesh Topology**: A network where every device is connected to every other device, providing multiple paths.
5. **Point-to-Point Topology**: A direct connection between two devices, forming a simple link.
6. **Client-Server Topology**: A network where clients request services from a central server.
7. **Peer-to-Peer Topology**: A network where all devices act as both clients and servers, sharing resources with each other.
8. **Hybrid Topology**: A combination of two or more different topologies in a single network.

### Common Hybrid Topologies

- **Star-Ring Network**: A combination of star and ring topologies, where devices in a star setup form a ring.
- **Star-Bus Network**: A combination of star and bus topologies, where devices connect to a central hub like in a star, but the central hub connects to a bus cable.

### Apart from this there are 2 type of topology 

1. **Physical Topology :**  Tell us how components are physically connected to each other . 10BaseT and FDDI is example of physical topology
2. **Logical Topology :**  Tell us how communication is done through network device logically .

- **Note:** You might be using 10BaseTwith physical star topology to connect component together however these component communicate using logical bus topology. Token ring is good example of communication protocol that has different physical topology from its logical one 
**10BASE-T:** 10 REFER TO Max speed which is 10mbps , Base is Baseband Transmission and T is for twisted pair cable.  

---

## What Are Ports?

In computer networking, a **port** is a communication endpoint that allows data to flow between a device and the network. Ports are used by protocols like TCP/IP to differentiate between different services running on the same machine.  
**for example**   
Imagine you live in a building with many apartments. The building is like a computer, and each apartment represents a different service or program running on that computer. The door of the apartment is like a port on the computer. Now, if you want to send a parcel (data) to a specific service (like a website or email program) inside the building, you need to know the correct apartment number (the port number). When you send the parcel to the building's main entrance (the computer's IP address), the receptionist (TCP/IP protocol) will direct the parcel to the right apartment based on the apartment number (port number).

Each port is associated with a **port number**. These numbers range from 0 to 65535 and are divided into different categories:

1. **Well-Known Ports (0-1023)**: Reserved for widely-used services and protocols.
2. **Registered Ports (1024-49151)**: Used by user applications and services.
3. **Dynamic or Private Ports (49152-65535)**: Typically used for ephemeral (temporary) connections.

## Example of Common Ports and Their Services:

- **Port 80 [HTTP](https://github.com/iamprim0rdial/cyber-security-notes/blob/main/http.md)**: Used for serving web pages using the HTTP protocol (unencrypted).
- **Port 443 [HTTPS](https://github.com/iamprim0rdial/cyber-security-notes/blob/main/http.md)**: Used for serving secure web pages over HTTPS.
- **Port 21 (FTP)**: Used for file transfer via FTP.
- **Port 22 (SSH)**: Used for secure remote login via the SSH protocol.
- **Port 25 (SMTP)**: Used for sending email through the SMTP protocol.
- **Port 53 (DNS)**: Used for Domain Name System (DNS) resolution.
- **Port 3306 (MySQL)**: Default port used for MySQL database connections.

### Notes:
- Always check for **open ports** on a target system, they can indicate potential attack surfaces.Use tools like **Nmap** to scan for open ports and identify services running on a target system. Be aware of **default ports** used by specific services, as they might be misconfigured or exposed to the internet.

---

## Network protocols
A network protocol is a set of rules for communication between devices on a network. rotocols define how data is transmitted, formatted, and processed. Each protocol serves a specific purpose and operates on a particular layer of the OSI model (Open Systems Interconnection). . It determines the format, timing, and flow of information exchanges between devices to ensure successful communication. Think of it as a common language for computers to communicate with each other over a network. **HTTP, SMTP, DHCP, FTP, Telnet, SNMP , TCP , IP , UDP , POP.**

### Common Networking Protocols

Below is an explanation of some of the most commonly used networking protocols:

### 1. **HTTP (HyperText Transfer Protocol)**
   - **Port**: 80
   - **Purpose**: Used for transferring web pages on the internet.
   - **Vulnerabilities**: Look for common web application vulnerabilities such as **SQL Injection**, **Cross-Site Scripting (XSS)**, and **Cross-Site Request Forgery (CSRF)**.

### 2. **HTTPS (HyperText Transfer Protocol Secure)**
   - **Port**: 443
   - **Purpose**: Secure version of HTTP that uses SSL/TLS encryption to protect the data being transferred.
   - **Vulnerabilities**: Look for **SSL/TLS misconfigurations**, weak **cipher suites**, and **SSL/TLS version vulnerabilities**.

### 3. **FTP (File Transfer Protocol)**
   - **Port**: 21
   - **Purpose**: Used for transferring files between systems.
   - **Vulnerabilities**: **Cleartext credentials**, **brute force attacks**, and **anonymous access** are common risks.

### 4. **SSH (Secure Shell)**
   - **Port**: 22
   - **Purpose**: Secure remote login and command execution.
   - **Vulnerabilities**: **Weak passwords**, **SSH key misconfigurations**, and **brute force attacks** are common security issues.

### 5. **SMTP (Simple Mail Transfer Protocol)**
   - **Port**: 25
   - **Purpose**: Used for sending emails.
   - **Vulnerabilities**: **Email spoofing**, **relaying**, and **open mail servers** can be exploited by attackers.

### 6. **DNS (Domain Name System)**
   - **Port**: 53
   - **Purpose**: Resolves domain names to IP addresses.
   - **Vulnerabilities**: Look for **DNS cache poisoning**, **DNS amplification attacks**, and **information leakage**.

### 7. **Telnet**
   - **Port**: 23
   - **Purpose**: Used for remote command-line access (insecure, not encrypted).
   - **Vulnerabilities**: **Cleartext communication** and **brute force attacks** can be exploited easily.

### 8. **RDP (Remote Desktop Protocol)**
   - **Port**: 3389
   - **Purpose**: Provides remote access to Windows-based machines.
   - **Vulnerabilities**: Known for **weak passwords**, **remote code execution vulnerabilities**, and **Denial of Service (DoS)** attacks.

### 9. **SNMP (Simple Network Management Protocol)**
   - **Port**: 161 (for requests), 162 (for traps)
   - **Purpose**: Used for network management and monitoring devices.
   - **Vulnerabilities**: Misconfigurations or weak **community strings** can expose sensitive information about the network.

### 10. **ICMP (Internet Control Message Protocol)**
   - **Port**: N/A (works at the IP layer)
   - **Purpose**: Used for network diagnostics (e.g., **ping** command).
   - **Vulnerabilities**: **ICMP-based attacks** like **ping flood** and **ICMP tunneling** can be exploited.

## Useful Protocols in security prespective:

As a **security researcher**, understanding and identifying the protocols in use on a target system is essential for discovering potential attack vectors. Below is a list of protocols to focus on, along with common vulnerabilities associated with them.

### **1. HTTP/HTTPS (Web Traffic)**
   - **Common Ports**: 80 (HTTP), 443 (HTTPS)
   - **Focus Areas**: Look for **web application vulnerabilities** such as:
     - **SQL Injection** (SQLi)
     - **Cross-Site Scripting** (XSS)
     - **Cross-Site Request Forgery** (CSRF)
     - **Insecure Cookies** and **Weak Session Management**
     - **Directory Traversal** and **File Upload Vulnerabilities**

### **2. SSH (Secure Shell)**
   - **Common Port**: 22
   - **Focus Areas**:
     - **Weak Passwords**: Try brute force or dictionary attacks.
     - **Unprotected SSH Keys**: Expose or misuse unprotected SSH keys.
     - **Privilege Escalation**: Misconfigured sudoers files or improper user permissions.

### **3. FTP (File Transfer Protocol)**
   - **Common Port**: 21
   - **Focus Areas**:
     - **Anonymous Access**: Look for servers with public access.
     - **Cleartext Credentials**: Ensure credentials are not being transmitted in plain text.
     - **Directory Listings**: Look for exposed files that shouldn’t be accessible.

### **4. SMTP (Email)**
   - **Common Port**: 25
   - **Focus Areas**:
     - **Open Relays**: Misconfigured SMTP servers that allow unauthorized email sending.
     - **Mail Spoofing**: Craft emails that appear to come from trusted sources.
     - **Phishing and Spam**: Exploit weak email security for phishing campaigns.

### **5. RDP (Remote Desktop Protocol)**
   - **Common Port**: 3389
   - **Focus Areas**:
     - **Weak Passwords**: Brute force RDP login.
     - **RDP Vulnerabilities**: Look for unpatched **RDP vulnerabilities** that can lead to remote code execution.

### **6. DNS (Domain Name System)**
   - **Common Port**: 53
   - **Focus Areas**:
     - **DNS Cache Poisoning**: Exploit the DNS cache for redirecting traffic to malicious sites.
     - **DNS Tunneling**: Exfiltrate data or establish covert channels using DNS.

### **7. SNMP (Network Management)**
   - **Common Port**: 161
   - **Focus Areas**:
     - **Default Community Strings**: If default strings (e.g., "public", "private") are used, they could give attackers access to sensitive device information.
     - **Misconfigurations**: Exposing SNMP to the internet can leak device configuration details.

### **8. ICMP (Ping and Diagnostics)**
   - **Focus Areas**:
     - **Ping Flood Attacks**: Overload the target system with ICMP requests.
     - **ICMP Tunneling**: Use ICMP packets for unauthorized data transmission.


