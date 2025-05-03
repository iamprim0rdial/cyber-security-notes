**IP:**

- IP [Internet Protocol] → Route the packets, IP is connectionless protocol provide unreliable delivery system for packet.
- Data transferred in packets via logical network paths in ordered format controlled by network layer. IP is method or protocol by which data is sent from one to another on internet.
- Each computer on internet has at least one IP address that is uniquely identify it from all other computer on the internet.
- Each packet is independent of one another.
- Header of minimum 20 byte address.

```
                             FORMAT OF IP DATAGRAM

0                   4                  8                    15 16                     31         
+-------------------+------------------+----------------------+------------------------+
| Version (4 bits)  | HLen (4 bits)    | Service Type(8 bits) | Total Length(16 bits)  |
+-------------------+------------------+------------------+----------------------------+
| Identification (16 bits) | Flags (3 bits) | Fragment Offset (13 bits)                |    
+--------------------------+----------------+------------------------------------------+
| TTL (8 bits)      |  Protocol (8 bits)    | Header Checksum (16 bits)                |
+-------------------+-----------------------+------------------+-----------------------+
|                            Source IP Address (32 bits)                               | 
+-------------------+------------------+------------------+----------------------------+
|                            Destination IP Address (32 bits)                          |
+-------------------+------------------+------------------+----------------------------+
|                             Options (variable length)                                |
+--------------------------------------------------------------------------------------+
|                                      Data                                            |
+--------------------------------------------------------------------------------------+

```
IP Header fields:

- Version: version of ip
- Hlen: Header length → 32 bit ( 0 - 31 ).
- Total Length: Size of datagram include header, max datagram size → 2^16 = 65536 byte
- Service type: 8 Bit field, assigned a priority. router can use this field to route packet.
- Time to live → ( 8 Bit ) → 255 value
- Protocol → Identify the higher level protocol is being used
- Source IP
- Destination IP
- Identification, Flag, Fragment offset.
    - Used handling fragmentation.
    - Reassemble.
- Option ( variable width )
    - Can be given provide router support.
    - Source routing for example.
- Header checksum → for field error checking
    - covered only ip header
    - how computed
    

Viewing IP packet:

- we can use packet sniffer to view ip packets
- Some popular tool like wireshark, TCPdump, Windump, Tshark, Solarwind and many more

---

IP addressing & Routing.

- IP packet fragmentation
- Transparent/ non-transparent fragmentation.

Fragmentation: we need to break the packets, then ip layer inject a packet into data link layer

- limitation of packet size is called max transfer unit (MTU) - vary from network to network
- default size of MTU 1500 byte - 12000 bits

IP protocol use non-transparent fragmentation.

Packet is also called datagram


```
          Fixed Size                  Independent Size
+-----------------------------------------------------------------+ 
|                             |                                   |
|        DATAGRAM HEADER      |        DATAGRAM DATA AREA         |        = Packets
|_________________________________________________________________|  
Contain                IP helps  to attached 
Source IP          Both parts DG Headers + DG Data
Destination IP
ETC
```

Two version:

- IPV4
- IPV6

IP Datagram:

A packet should be 

- Network independent
- Travelled from any path but data is not change or temper
- Router should know what is meaning of header’s

The IP protocol makes all best effort is to deliver the packets. It does not handle 

- Datagram duplication.
- Delay or out-of-bound delivery.
- Corruption of data.
- Datagram loss

---

Address distribution:

A → 2 Billion

B → 1 Billion

C → 500 Million

Special purpose IP

Private use

- 10.X.X.X                 CLASS A
- 172.16.X.X - 172.31.X.X  CLASS B
- 192.168.X.X              CLASS C

Loop Back / Local address: 127.0.0.0 - 127.255.255.255

Default network - 0.0.0.0

Limited broadcast - 255.255.255.255

Port Number - 16 bit integer 2 ^16 = 65536

---

TCP Segment ( 20 - 60 byte of header )
```

0                    15   16                         31
+-----------------------+--------------------------------------------+ 
| Source Port (16 bits) | Destination Port (16 bits)                 | 
+-------------------+------------------+-----------------------------+ 
|          Sequence Number (32 bits)                                 | 
+--------------------------------------------------------------------+ 
|       Acknowledgment Number (32 bits)                              | 
+------------------------------------------------------------------------------------+ 
| Data Offset (4 bits) | Reserved (3 bits) | Flags (9 bits) |  Window Size (16 bits) |
+--------------------------+----------------+----------------------------------------+ 
|         Checksum (16 bits)             |  Urgent Pointer (16 bits) |
+--------------------------------------------------------------------+ 
|                       Options (variable length)                    | 
+--------------------------------------------------------------------+ 
|                         Data (variable length)                     |
+--------------------------------------------------------------------+ 

```

**Description of Each Field**

- **Source Port (16 bits):** The port number of the sender.
- **Destination Port (16 bits):** The port number of the receiver.
- **Sequence Number (32 bits):** The sequence number of the first byte in this segment (used for data reordering and flow control).
- **Acknowledgment Number (32 bits):** If the ACK flag is set, this field contains the next sequence number the sender of the segment expects to receive.
- **Data Offset (4 bits):** The size of the TCP header, expressed in 32-bit words. It tells where the data begins.
- **Reserved (3 bits):** Reserved for future use, should be set to zero.
- **Control Flags (9 bits):** A set of 9 flags that control the state of the connection, including:
    - **URG (1 bit):** Urgent pointer field is significant.
    - **ACK (1 bit):** Acknowledgment field is valid.
    - **PSH (1 bit):** Push function.
    - **RST (1 bit):** Reset the connection.
    - **SYN (1 bit):** Synchronize sequence numbers.
    - **FIN (1 bit):** No more data from the sender.
- **Window Size (16 bits):** The size of the sender's receive window (flow control).
- **Checksum (16 bits):** Error-checking the header and data. If the checksum is invalid, the segment is discarded.
- **Urgent Pointer (16 bits):** If the URG flag is set, this field points to the last urgent data byte in the segment.
- **Options (variable length):** Optional fields for various control purposes, such as maximum segment size (MSS), window scale factor, and timestamps.
- **Data (variable length):** The actual data or payload being transmitted in the TCP segment.

This format follows the standard TCP header structure and includes all the necessary fields that make up a TCP segment.

---

**Internet routing protocols:** 

Connection type: 

- Connection oriented [TCP uses Connection oriented approach ]
- Connection less [Ip protocol use connection-less approach ]

**Routing table:**

- Static: Enter manually, insert information. Does not need change with time
- Dynamic: Update periodically depend on net condition. use protocol like RIP, OSPF, BGP etc

Typically field in routing table

- Subnet
- Destination Ip address
- Next Hop address
- Flag
    - U → routers are up and running
    - G → Destination is in another network
    - H → Host- specific address.
    - D → Address by redirection
    - M → Modified by redirection
    
    **Interior protocol** → routing information protocol (RIP), Open shortest path first (OSPF).
    
    **Exterior** **protocol** → Border gateway protocol (BGP)

```
 
                           
+------------------------+                          +-------------+    
|         [A]            |  <-- Interior            |     [M]     | 
|        /   \           |      protocol            |      |      |
|       /     \          |                          |      |      |
|     [B]-----[C] -----------------exterior---------------[N]     |    
|     |                  |         protocol         +-------------+
+-----|------------------+
      | 
 An autonomous system, controlled
 and managed by single organisation
 
 Every autonomous system (AS) is assigned unique AS number.
 AS (autonomous system ): A collection of IP networks and routers under the control of a single organization that presents a common routing policy to the internet.
 Two BGP router exchanging information connection are called peer.
```

Key Differences between Interior and Exterior Protocols

- **Interior Protocols (IGP):**
    - Used within a single autonomous system (AS).
    - **Protocol Type:** The protocol used for routing inside the AS, such as:
        - **RIP (Routing Information Protocol):** A distance-vector protocol that uses hop count as a routing metric.
        - **OSPF (Open Shortest Path First):** A link-state protocol that uses cost as a metric, allowing for faster convergence and better scalability.
        - **EIGRP (Enhanced Interior Gateway Routing Protocol):** A hybrid protocol combining features of both distance-vector and link-state protocols.
    - Focused on efficient and fast routing inside the network.
    - Examples: RIP, OSPF, EIGRP.
- **Exterior Protocols (EGP):**
    - Used to exchange routing information between different autonomous systems.
    - Responsible for routing between different networks or organizations.
    - Example: BGP (Border Gateway Protocol).
    
- **BGP (Border Gateway Protocol):** The primary protocol used to exchange routing information between different autonomous systems on the internet.
- **Functional procedure in BGP**
    - Neighbour acquisition → Two router agree to be neighbour by exchanging message
    - Neighbour reachability → Check if neighbour is still alive & is maintaining the relationship.
    - Network reachability → Each route maintain a list of network that it can reach and the prefer route.
    - 

**Description of Fields**

- **Destination Network:** The destination network or IP range for the route.
- **Subnet Mask:** The subnet mask that defines the size of the destination network.
- **Next Hop:** The IP address of the next router or gateway that is responsible for forwarding packets toward the destination.
- **Metric:** The cost or "distance" associated with the route (e.g., hop count, bandwidth).
  
