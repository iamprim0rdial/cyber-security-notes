# 🕸️

**Place Your Security Devices Correctly**

- You should place a firewall at every junction of a network zone. Each segment of your network should be protected by a firewall.
- Another device that obviously belongs on the perimeter is an anti-DDoS device so you can stop DDoS attacks before they affect the entire network.
- Behind the main firewall that faces public network, you should have a web filter proxy.
- consider load balancers. If we have a cluster of web servers in a DMZ, then the load balancer needs to be in the DMZ as well.
- If we have a cluster of database servers in a private network segment, then the load balancer must be placed with that cluster.
- Network aggregation.
- Port mirroring.
- an IDS or IPS

**Use Centralized Logging and Immediate Log Analysis**

Record suspicious logins and other computer events and look for anomalies. This best practice will help you reconstruct what happened during an attack so you can take steps to improve your threat detection process and quickly block attacks in the future. remember that attackers are clever and will try to avoid detection and logging. They will attack a sacrificial computer, perform different actions and monitor what happens in order to learn how your systems work and what thresholds they need to stay below to avoid triggering alerts.

**Use Honeypots and Honeynets**

A honeypot is a separate system that appears to be an attractive target but is in reality a trap for attackers (internal or external). For example, you might set up a server that appears to be a financial database but actually has only fake records. Using a honeypot accomplishes two important goals. First, attackers who believe they have found what they are looking for will leave your other systems alone, at least for a while. Second, since honeypots are not real systems, no legitimate users ever access it and therefore you can turn on extremely detailed monitoring and logging there. When an attacker does access it, you’ll be gathering an impressive amount of evidence to aid in your investigation. A honeynet is the next logical extension of a honeypot — it is a fake network segment that appears to be a very enticing target. Some organizations set up fake wireless access points for just this purpose.

**Protect Your Network From Insider Threats**

To deal with insider threats, you need both prevention and detection strategies. The most important preventive measure is to establish and enforce the least-privilege principle for access management and access control. Giving users the least amount of access they need to do their jobs enhances data security, because it limits what they can accidentally or deliberately access and ensures that is their password is compromised, the hacker doesn’t have all keys to the kingdom. Other

**preventative measures include**

- system hardening
- anti-sniffing networks
- strong authentication

**Detection strategies include**

- monitoring users and networks
- Using both network- and host-based intrusion detection systems which are typically based on signatures, anomalies, behaviour or heuristics.

End users also need to be trained in how to deal with the security threats they face, such as phishing emails and attachments. The best security in the world can be undermined by end users who fail to follow security policies. However, they cannot really be expected to follow those policies without adequate training.

**Use VPNs**

A virtual private network (VPN) is a secure private network connection across a public network. For example, VPNs can be used to connect LANs together across the internet.

**Use Multiple Vendors**

In addition to diversity of controls, you should strive for diversity of vendors. For example, to defend against malware, you should have antimalware software on each of your computers, as well as on the network and at the firewall — and use software from different vendors for each of these places. Because each vendor uses the same malware detection algorithms in all its products, if your workstation, network and firewall antimalware solutions all come from vendor A, then anything missed by one product will be missed by all three. The best approach is to use vendor A for the firewall antimalware, vendor B for the network solution, and vendor C to protect individual computers. The probability of all three products, created by different vendors and using different detection algorithms, missing a specific piece of malware is far lower than any one of them alone missing it.

**Know Network Defences**

- **Firewall** — One of the first lines of defence in a network, a firewall isolates one network from another. A firewall can be either software or hardware. It is designed to prevent unauthorized access to network resources by filtering network data packets according to an Access Control List (ACL). It blocks unwanted traffic and permits desired traffic. Firewalls either can be standalone systems or included in other devices, such as routers or servers.
- **ACL (Access Control List) -** An ACL is a list of rules that determines what can access the network. It either allows or denies permission.
- **Implicit Deny** - ****This refers to the default rule set that comes with a firewall, where traffic that is not explicitly allowed is denied by default.
- **Intrusion detection system (IDS)** — An IDS enhances cybersecurity by spotting a hacker or malicious software on a network so you can remove it promptly to prevent a breach or other problems, and use the data logged about the event to better defend against similar intrusion incidents in the future.
- **Intrusion prevention system (IPS**) — An IPS is a network security solution that can not only detect intruders, but also prevent them from successfully launching any known attack. Intrusion prevention systems combine the abilities of firewalls and intrusion detection systems. However, implementing an IPS on an effective scale can be costly, so businesses should carefully assess their IT risks before making the investment. Moreover, some intrusion prevention systems are not as fast and robust as some firewalls and intrusion detection systems, so it might not be an appropriate solution when speed is an absolute requirement.
- **EDR (Endpoint Detection and Response)** - ****EDR solutions provide continuous monitoring and response to potential threats on endpoints such as computers and mobile devices.
- **Network access control (NAC)** — involves restricting the availability of network resources to endpoint devices that comply with your security policy. Some NAC solutions can automatically fix non-compliant nodes to ensure it is secure before access is allowed.
- **Web filters** — are solutions that by preventing users’ browsers from loading certain pages from particular websites. There are different web filters designed for individual, family, institutional and enterprise use. Proxy servers act as negotiators for requests from client software seeking resources from other servers.
- **Anti-DDoS** — devices detect distributed denial of service (DDoS) attacks in their early stages, absorb the volume of traffic and identify the source of the attack.
- **Load balancers** — are physical units that direct computers to individual servers in a network based on factors such as server processor utilization, number of connections to a server or overall server performance.
- **Spam filters** — detect unwanted email and prevent it from getting to a user's mailbox. Spam filters judge emails based on policies or patterns designed by an organization or vendor.
- **CONTENT FILTERING** - Content filtering technology is commonly used in email systems. It filters data based on its content and is often used to filter out email spam. ****

**Segregate Your Network**

Network segmentation involves segregating the network into logical or functional units called **zones**. For example, you might have a zone for sales, a zone for technical support and another zone for research, each of which has different technical needs. You can separate them using routers or switches or using virtual local area networks (VLANs), which you create by configuring a set of ports on a switch to behave like a separate network. Segmentation limits the potential damage of a compromise to whatever is in that one zone. Essentially, it divides one target into many, leaving attackers with two choices: Treat each segment as a separate network, or compromise one and attempt to jump the divide. Neither choice is appealing. Treating each segment as a separate network creates a great deal of additional work, since the attacker must compromise each segment individually; this approach also dramatically increases the attacker’s exposure to being discovered.

```
 [ Network 1 ] …. [ Network 2 ] …. [ Network 3]
   Sales Zone  ….technical support …. Research.
							Network segmentation
```

**Types of Network Segments**

**Network segments can be classified into the following categories:**

- Public networks allow accessibility to everyone.
- Semi-private networks sit between public networks and private networks.
- Private networks are organizational networks that handle confidential and propriety data.
- Demilitarized zone (DMZ) is a noncritical yet secure region at the periphery of a private network, separated from the public network by a firewall; it might also be separated from the private network by a second firewall.
- Software-defined networking (SDN) is a relatively recent trend that can be useful both in placing security devices and in segmenting the network.

### TYPES OF FIREWALLS

**HOST-BASED FIREWALL:**

A software firewall that protects only a host and nothing else. It typically comes built-in with operating systems such as Windows.

**NETWORK-BASED FIREWALL:**

A combination of hardware and software that operates at the network layer. It protects the entire network, not just a single host like a host-based firewall. It applies rules to the entire network.

**Stateful vs Stateless FIREWALLS:**

Firewalls inspect traffic in different ways:

- **Stateful:**
    
    A stateful firewall monitors all connections and data streams passing through. It keeps a record of the state of active connections, offering dynamic protection to the network.
    
- **Stateless:**
    
    A stateless firewall does not monitor the state of connections. It uses an ACL to allow or deny traffic but does not keep a record of the traffic.
    

### 

**Splunk** - ****Splunk is a platform used for monitoring, searching, and analyzing machine-generated big data via a web-style interface.

### 

**Signature Identification:**

Another type of filter is called signature identification, which is used to detect viruses that exhibit well-known behavioral patterns. Firewalls using signature identification are programmed to recognize these patterns.
