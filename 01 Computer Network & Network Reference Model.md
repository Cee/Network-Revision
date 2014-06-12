#Computer Network & Network Reference Model

###Overview of Computer Network

+ Network:
A network is an intricately connected system of objects, devices, or people.

+ LAN:
Local Area Networks

+ WAN:
Wide Area Networks

+ Internet: 
A network whose nodes are networks

+ ISP:
Internet Service Providers

+ LAN Devices: Hub Bridge Switch Router

+ WAN Devices: Router Modem ISDN DSL

+ Units, using OSI model, can be called **packets**, or **frames** or **segments**

+ Why data packets? 

	- Computers can take turns sending packets.
	
	- If packet is lost, only small amount of data must be retransmitted. 
	
	- Data can take different paths.

+ Source and Destination

+ Bandwidth: the measure of how much information can flow from one place to another in a given amount of time. 

	- Measured in bits/second (bps)
	
	- Throughput(吞吐量) ≤ Bandwidth
	
###OSI Reference Model

+ OSI Model: Open System Interconnection Model
 
	- Proposed by International Organization for Standardization (ISO) 
	
	- A layered communication process:
		
		+ Reduce Complexity
		
		+ Standardizes interfaces
		
		+ Facilitates modular engineering
		
		+ Ensures interoperable tech
		
		+ Accelerates evolution
		
		+ Simplifies teaching & learning

	- 7 Layers: Dataflow(1-4) & Application(5-7) layers 
		
		+ Physical: Binary transmission
		
			Keywords: Signal and Media
		
		+ Data Link: Access to media
		
			Keywords: Frame, Media access control
		
		+ Network: Addresses and best path
		
			Keywords: Path selection, Routing, Addressing
			
		+ Transport: End-to-end connections
		
			Keywords: Reliability, Flow control, Error correction
		
		+ Session: Inter-host connection
		
			Keywords: Dialog and Conversations
		
		+ Presentation: Data presentation and encryption
		
			Keywords: Common Format
		
		+ Application: User Interface
		
			Keyword: Browser

![Protocols on ISO layers]()

+ Protocols on ISO layers

###TCP/IP Model

+ Four layers: Application, Transport, Internet, Network Access

	- Application: Handles high-level protocols, issues of representation, encoding, and session control
	
	- Transport: Reliability, flow control and error correction
	
		+ TCP(Transmission Control Protocol) 
		
		+ UDP(User Datagram Protocol)
		
		+ Package infomation into segments
		
	- Internet: Source & Destination, best path determination and packet switching occur at this layer
	
		+ IP(Internet Protocol)
		
	- Network Access: LAN & WAN tech details

![Common TCP/IP Protocols]()
	
+ Common TCP/IP Protocols

	- FTP(File Transfer Protocol)

	- HTTP(Hypertext Transfer Protocol)
	
	- SMTP(Simple Mail Transfer Protocol) 

	- DNS(Domain Name System)
	
	- TFTP(Trivial File Transfer Protocol)
	
###Network Topology

![Network Topologies]()

+ Topology: Defines the structure of the network

	- Physical: bus, star, ring, hierarchical, mesh, tree, cellular
	
	- Logical: token passing
	
	- Pros & Cons?

###Network Devices

+ NICs

+ Switches

+ Bridges

+ Routers

+ Gateways (protocol transformation)

+ PCs(all devices that operate at all levels of the OSI model)
