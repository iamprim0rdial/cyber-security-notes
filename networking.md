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

## Data Communication: 
Data communication means two exchange the data between two or more nodes or devices. the effectiveness of data comm. is depend upon 4 characteristic .

### Delivery :
data must deliver to correct destination .

### Accuracy :
The system must deliver data accurately 

### Timeliness :
The system must deliver the data in timely manner. data deliver late means useless, ex— Video and audio timely deliver means data that are producing in the same order they are produce and without significant delay. This kind of delivery is called real-time transmission. 

### Jitter :
jitter refers to variation in packet arrival time

---

### Network protocols
A network protocol is a set of rules for communication between devices on a network. It determines the format, timing, and flow of information exchanges between devices to ensure successful communication. Think of it as a common language for computers to communicate with each other over a network. **HTTP, SMTP, DHCP, FTP, Telnet, SNMP , TCP , IP , UDP , POP.**

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
