#OSI Layer 3: Network Layer

###Overview of the Network Layer

+ Main Tasks:
	
	- Move data through networks

	- Use a hierarchical addressing scheme (opposed to MAC addressing, which is flat)

	- Segment network and control flow of traffic

	- Reduce congestion

	- Talk to other networks
	
+ Device: Router

###IP Addresses and Subnets

- Datagram: Head + Data (Slides: pp6-23)

	+ Include source and dest. address
	
- IP Addresses

	- Two parts: Network ID, Host ID
	
	- Classes 
		
		+ 0 – 127 Class A address

		+ 128 - 191 Class B address
		
		+ 192 – 223 Class C address
		
		+ The first address in each network is reserved for the network address
		
		+ The last address is reserved for the broadcast address
		
	- Private Address
	
		+ 10.0.0.0 - 10.255.255.255

		+ 172.16.0.0 - 172.31.255.255

		+ 192.168.0.0 - 192.168.255.255
	
	- Subnet
	
		+ The minimum number of bits you can borrow is two
		
		+ Mask
		
###Layer 3 Devices

+ Path determination: choose the next hop

+ Router function

	- Static addressing
	
	- Dynamic addressing: RARP, BOOTP, DHCP (Slides: pp66-68)
	
###ARP Protocol

+ ARP(Address Resolution Protocol) (Slides: pp71-79)

	- Need both the IP and MAC addresses of dest. devices

+ Communicate

	- Default gateway
	
	- Proxy ARP
	
+ **Network Layer Services**

	- Connection-oriented & Circuit switched

	- Connectionless network & Packet switched

###Routed and Routing Protocols
	
####Routing tables

+ Static and Dynamic

	- Static: manually
	
	- Dynamic: routing protocols like RIP, IGRP, EIGRP, OSPF
	
		+ Routing protocols

			- Determine the paths that routed protocols follow to their destinations
			
+ IGP and EGP

	- Interior Gateway Protocols (RIP, IGRP, EIGRP, OSPF)
	
		+ A network of routers under one administration
		
	- Exterior Gateway Protocols (EGP, BGP)
	
		+ Autonomous systems
		
+ DVP and LSP (Slides: p101)

	- Distance-Vector Protocols (RIP, IGRP)
	
	- Link State Protocols (OSPF)
	
###Protocols

+ RIP(Route Information Protocol)

	- Most popular

	- Interior Gateway Protocol

	- Distance Vector Protocol

	- Only metric is number of hops
	
	- Maximum number of hops is 15

	- Updates every 30 seconds

	- Doesn’t always select fastest path
	
	- Generates lots of network traffic
	
+ IGRP(Interior Gateway Route Protocol) & EIGRP(Enhanced IGRP) 
	
	- Cisco proprietary

	- Interior Gateway Protocol
	
	- Distance Vector Protocol
	
	- Metric is compose of bandwidth, load, delay and reliability

	- Maximum number of hops is 255
	
	- Updates every 90 seconds

+ OSPF(Open Shortest Path First)

	- Interior Gateway Protocol

	- Link State Protocol

	- Metric is compose of cost, speed, traffic, reliability, and security

	- Event-triggered updates

###VLSM(Variable-Length Subnet Masks)

> VLSM is simply a feature that allows a single autonomous system to have networks with different subnet masks. 

+ How to use(Slides: pp114-126)

+ Routing Aggregation(Slides: pp127-130)

###ICMP(Internet Control Message Protocol)

> In order to increase the chance of data delivery.

+ Data format(Slides: p134)

+ PING(Packet InterNet Groper)

###Mobile IP

+ Find, Reg, Tunnel


	