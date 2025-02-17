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

---

### CABLE STANDARD

**10BASE-T:** 10 REFER TO Max speed which is 10mbps , Base is Baseband Transmission and T is for twisted pair cable.  
**10BASE - 2 :**  IT IS ALSO REFER TO Thin Ethernet . uses coaxial cable it has maximum speed is 10Mbps and Maximum length of 200 meters.  
**100BASE - T : Maximum**  speed 100Mbps . Uses UTP cat. 5 or higher. maximum length of 100 meters . also known as fast ethernet. Uses copper cable .  
**100BASE - FX : Maximum**  speed 100Mbps .Uses **Fibre** cable. maximum length of 400 meters (half duplex) and 2 kilometres (full duplex)  

**Gigabits standards**  

**1000BASE - T : Maximum**  speed 100Mbps .  Uses UTP cat. 5 or higher. maximum length of 100 meters   
**1000BASE - TX : Similar to**  1000BASE T  . Supposed to be an easier setup because it only uses 2 unidirectional pairs of wires for communication. Never Caught on . Known as a failure in commercial implementation    
**10G BASE - T :**  Maximum speed of 10,000Mbps. Uses both STP and UTP cabling. maximum length of 100 metres if using category or cat 6a cables and Maximum length of 55 metres if using cat 6.  
**10G BASE - SR :**  SR stand for short range. commonly used standard multimode fibre specification. and have length of 300 metres .   
**10G BASE - ER :**  ER stand for extended range  and have length of 40 kilometres using single mode fibre  
**10G BASE - SW : Same specs as 10G BASE SR**  , But specifically used to operate over SONET (Synchronous optical network)  

---

## What Are Ports?

In computer networking, a **port** is a communication endpoint that allows data to flow between a device and the network. Ports are used by protocols like TCP/IP to differentiate between different services running on the same machine.

Each port is associated with a **port number**. These numbers range from 0 to 65535 and are divided into different categories:

1. **Well-Known Ports (0-1023)**: Reserved for widely-used services and protocols.
2. **Registered Ports (1024-49151)**: Used by user applications and services.
3. **Dynamic or Private Ports (49152-65535)**: Typically used for ephemeral (temporary) connections.

## Example of Common Ports and Their Services:

- **Port 80 (HTTP)[]**: Used for serving web pages using the HTTP protocol (unencrypted).
- **Port 443 (HTTPS)**: Used for serving secure web pages over HTTPS.
- **Port 21 (FTP)**: Used for file transfer via FTP.
- **Port 22 (SSH)**: Used for secure remote login via the SSH protocol.
- **Port 25 (SMTP)**: Used for sending email through the SMTP protocol.
- **Port 53 (DNS)**: Used for Domain Name System (DNS) resolution.
- **Port 3306 (MySQL)**: Default port used for MySQL database connections.

## Useful Ports for Bug Hunters

As a **bug hunter**, certain ports are particularly important for identifying and exploiting vulnerabilities in a system. Below is a list of commonly used ports that bug hunters should keep an eye on during penetration testing:

### Well-Known Ports (0-1023)
- **Port 22 (SSH)**: Common for secure remote shell access. Misconfigurations can allow unauthorized access or weak password attacks.
- **Port 23 (Telnet)**: An insecure remote login protocol. It's often vulnerable to eavesdropping and brute-force attacks.
- **Port 80 (HTTP)**: Commonly used for unencrypted web traffic. Look for vulnerabilities like XSS, CSRF, and SQL injection.
- **Port 443 (HTTPS)**: Secure web traffic. Look for vulnerabilities like SSL/TLS misconfigurations, weak ciphers, or missing certificates.
- **Port 21 (FTP)**: File Transfer Protocol. Vulnerabilities include weak or missing authentication and data interception.
- **Port 25 (SMTP)**: Simple Mail Transfer Protocol. Can be used for sending malicious emails or relay attacks.
- **Port 53 (DNS)**: Domain Name System. Look for DNS misconfigurations, DNS cache poisoning, or information leaks.
- **Port 110 (POP3)**: Used for receiving emails. Look for weak authentication and email interception vulnerabilities.

### Registered Ports (1024-49151)
- **Port 3306 (MySQL)**: Default MySQL database port. Vulnerabilities include weak authentication, SQL injection, and improper database configurations.
- **Port 5432 (PostgreSQL)**: Default PostgreSQL database port. Misconfigurations can lead to unauthorized access or privilege escalation.
- **Port 3389 (RDP)**: Remote Desktop Protocol. Known for vulnerabilities like weak passwords and exploits for remote code execution.
- **Port 8080 (HTTP Alternative)**: Often used for alternative HTTP services or web application testing.
- **Port 6379 (Redis)**: Default port for Redis. Unauthorized access can lead to arbitrary command execution and data compromise.
  
### Dynamic or Private Ports (49152-65535)
- **Ports for Ephemeral (Temporary) Connections**: These are typically assigned by the operating system for client connections. These are useful for testing how a server handles a large number of simultaneous connections.



### Notes:
- Always check for **open ports** on a target system, they can indicate potential attack surfaces.Use tools like **Nmap** to scan for open ports and identify services running on a target system. Be aware of **default ports** used by specific services, as they might be misconfigured or exposed to the internet.


---

### Network protocols
A network protocol is a set of rules for communication between devices on a network. rotocols define how data is transmitted, formatted, and processed. Each protocol serves a specific purpose and operates on a particular layer of the OSI model (Open Systems Interconnection). . It determines the format, timing, and flow of information exchanges between devices to ensure successful communication. Think of it as a common language for computers to communicate with each other over a network. **HTTP, SMTP, DHCP, FTP, Telnet, SNMP , TCP , IP , UDP , POP.**

## Common Networking Protocols

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


---

## OSI Model:

The OSI (Open Systems Interconnection) model is a framework/reference model that tell how the data is transmitted between computers over a network.
 - 7 different layers: Each of which is responsible for performing a specific task.
   - These layers are:

1. **Physical Layer:** This layer deals with the physical components of the network, such as cables, transmitters, and receivers.
2. **Data Link Layer:** This layer is responsible for the reliable delivery of data over the physical layer by adding error checking and flow control to the data.
3. **Network Layer:** This layer provides the routing and addressing of data, allowing it to travel from one network to another.
4. **Transport Layer:** This layer is responsible for ensuring that data is transmitted reliably and in the correct order, by using techniques like flow control and error correction.
5. **Session Layer:** This layer manages the communication sessions between applications and ensures that the data is transmitted in an orderly manner.
6. **Presentation Layer:** This layer deals with the format and compression of data, ensuring that it can be understood by the application.
7. **Application Layer:** This layer is the highest layer and deals with the user-end applications and services, such as email and web browsing.

Each layer of the OSI model communicates with the layer above and below it, allowing data to be transmitted from one computer to another in a standardized and organized way

### Advantage of OSI model

1. interoperability 
2. simplification
3. modular  design
4. training

---

## Protocols:
