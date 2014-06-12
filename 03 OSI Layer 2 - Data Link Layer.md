#OSI Layer 2: Data Link Layer

###Overview

+ Format of data and actions between two nodes

+ Main tasks:

	- Error notification

	- Network topology

	- Flow control
	
+ Media Access Control & Common LANs
	
	- Deterministic(Scheduled): Token Ring, FDDI
	
	- Non-deterministic(First come, first served): Ethernet/802.3
	
		+ This MAC protocol is called Carrier Sense Multiple Access with Collision Detection (CSMA/CD)
	
+ LAN Transmission Methods

	- Unicast
	
	- Multicast
	
	- Broadcast
	
###Ethernet and CSMA/CD

####LLC and MAC Sub-layers

+ Data Link Layer - two parts:
	
	- Media Access Control (MAC) (transitions down to media)
	
		+ 802.3 defines how to transmit frames, network topology, line discipline, and handles physical addressing.
		
	- Logical Link Control (LLC) (transitions up to the network layer) 
	
		+ Logically identifies different protocol types and encapsulates them.
		
+ Media Access Control Sublayer

	- Preamble(8 bytes): A coming frame
	
	- Dest. add.(6 bytes) & Source add.(6 bytes)
		
		+ Source: unicast add.
		
		+ Dest. add.: unicast, multicast or broadcast 
		
	- Length(2 bytes)
	
	- Data(Varable)
	
	- FCS(4 byts): CRC, cyclic redundancy check value.
	
+ Logical Link Control Sublayer
	
	- Defined in the IEEE 802.2 specification and supports
	
	- Encapsulation:
	
		+ Position: Physical Layer → MAC → LLC → Network Layer
		
		+ Encapsulation: MAC - LLC - Packet - MAC
		
####Media Access Control in MAC Sub-layer

+ MAC Address: 48 bits

	- Broadcast: FFFF.FFFF.FFFF
	
	- Use: Don't know IP Address
	
+ Ethernet Media Access Control - CSMA/CD

	- Ethernet / IEEE 802.3 MAC mechanism
	
	- CSMA(Carrier Sense Multiple Access)
	
		+ Listen to the channel first
		
		+ 1-persist, non-persist, p-persist
	
	- CSMA/CD
	
		+ Use CSMA mechanism to judge if the host should send the data
		
		+ In the transmitting process, listen to the channel at the same time
		
			- When a collision detected, broadcast the jam signal 

			- Back off algorithms determine when the colliding stations can retransmit. 
			
![Ethernet CSMA/CD]()

####Flow Control in LLC Sub-layer

![Sliding Window Protocol]()

+ Sliding Window Protocol(Slides: p39)
	
	- Send messages with an index(0 ~ 2^n - 1)
	
	- Pipelining
	
####Development of Ethernet 

> Ethernet is the most widely used LAN technology. 

+ 802 Standards

	- 802.3: CSMA/CD Access Method
	
	- 802.5: Token Ring Access Method
	
####Wireless LAN and CSMA/CA

- Wireless LAN Standard: 802.11b/a/g/n

	+ 802.11: Direct Sequence Spread Spectrum
	
	+ 802.11b: Wi-Fi, operate within 2.4 GHz, throughoutput of 54Mbps
	
	+ 802.11a: Using the 5 GHz
	
	+ 802.11g: Compatibility for 802.11b
	
	+ 802.11n: Next generation WLAN, double bandwidth
	
- Scanning: Active or Passive

- Frames

- CSMA/CA(Carrier Sense Multiple Access with Collision Avoidance)(Slides: p67)

###Layer2: Data Link Layer

- NICs, bridges, switches