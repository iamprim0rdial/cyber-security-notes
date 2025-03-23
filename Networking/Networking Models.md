**Layer Network architecture:**

OSI → Open system interconnection model → Seven layers → Set of Layer ( Hierarchical ).

Objective → Systematic approach design 

1. Application

6. Presentation

1. Session

4. Transport

1. Network

2. Data-Link

1. Physical

[ 4 - 7 ] Layers deal with → Host - to - Host

[ 1 - 3 ] Layers deal with → Point - to - Point

```
Node <-     [ A ] 
           /  |  \ --> Active in point to point connections            
            [ .. ]  
           /  |  \
            [ .. ] -> Intermediate Node [ devices, or computer ]   
           /  |  \            
            [ .. ]  
           /  |  \       
            [ Z ]

From [ A ] to [ Z ] is host to host connect not exist in intermediate.
```

    Route packet through **point to point** like where to send packet next through routing tables
1. **Physical** → Transmit raw bit stream over channel (electrical signals). This layer define network topology(Star, Mesh, Bus). Bits synchronization /asynchronization works on physical object.
2. **Data-Link** →  Work on **Intra-networking**(Host to Host), Ensure that the connection is reliable, ( Detect Error, retransmit data, flow control, error control, Framing of data ) `[packets are further divide into Frame]` 
3. **Network** → Work on **Inter-Networking** Divide data into fixed no of packets(Contain proper address/ logical address [ IP ADDRESS ].)`[ Logical addressing, Routing Path decide, Network conjection, Packet switching ]`
---
   **Host to Host**
   
5. **Transport** → Divide data in fixed size called segments( smaller pieces), `Process of dividing data into fix size so it can send easily over network is called segmentation` [ End to end reliable data transfer, error recovery, flow control, error control, port addressing ] [ TCP and UDP ]  
6. **Session** → Manage sessions ( Establishment, maintaining and terminating connection. )
7. **Presentation** → Raw data encoding-decoding, encryption-decryption, extensions, Formatting, provide data independency. 
8. **Application** → Use and produce raw data, Interface point for user application.[HTTP, FTP, DNS, TELNET, EMAIL]


```
Main difference between packet and frame [FRAME] contain more proper header files than packets. Frame contain Mac-address of receiving end.
```

```
All information of packet like [ Arrangement no, Segmentation size, Sender IP, Reciever IP, Segmentation No, Packet Size ] are store in header of packets
```

TCP/IP Model → Transmission control protocol, Main used in current internet, evolved from OSI Model. It is collection of different protocol or family of protocol.

```
  [ OSI MODEL ]              [ TCP/IP Model ]           [ TCP/IP Protocol Suite ]
  
7. Application        ]
6. Presentation       |---->  Application layer           Telnet, FTP, SMTP, DNS, SNMP, HTTP, HTTPS        Run top 3 layer
5. Session            ]
4. Transport         ------>  Transport  layer            TCP, UDP                                         End to end data transfer
3. Network           ------>  Network layer               ARP, IP, IGMP, ICMP, RARP                        Packet delivery 
2. Data-Link         ------>  Data Link layer          |  Ethernet Token  Frame  ATM           
1. Physical          ------>  Physical layer           |           Ring   Relay                            Frame transmission   

```

Most fundamental network protocol. 

- allow computer to communicate or shared resource.
- Used standard
- Bridge between non compatible platform.
- Developed by ARPA ( advanced research project agency )
- Mainly consist of 4 layer










