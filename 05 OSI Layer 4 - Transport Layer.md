#OSI Layer 4: Transport Layer

###Overview

+ Main Task

	- Segment application data
	
	- Establish end-to-end operations
	
	- Send segments
	
	- **Flow control and reliaability**
	
+ Protocols: Divide messages and reassemble them

	- TCP(Transmission Control Protocol)
	
		+ Reliable
		
		+ Software checking
		
		+ Re-send anything lost or error
		
		+ Acknowledgments
		
		+ Flow control
	
	- UDP(User Datagram Protocol)

		+ Unreliable
		
		+ No software checking
		
		+ No acknowledgments
		
		+ No flow control

	- Port numbers below 255 are reserved for TCP and UDP public applications
	
###TCP

+ Problems

	- Reliable transfer
	
	- Flow control
	
	- Connection
	
+ Datagram(Slides: pp10-25)

	- Header(20 bytes)
	
	- Data(Varable)
	
	- Tail(Container)
	
+ Reliable Connection

	- Establish(3 Handshakes, Slides: pp28-32)
	
		+ First Handshake(`seq = x`)
		
			- Server: Monitor passively
			
			- Client: Send a TCP segment with `SYN = 1` and `ACK = 0`
			
		+ Second Handshake(`seq = y` and `ack = x + 1`)
		
			- Server: Check if exists service process monitoring the port
				+ If none, answer a TCP segment with `RST = 1`
				
				+ If exist, decide to reject or accept
				
				+ If accept, send a TCP segment with `SYN = 1` and `ACK = 1`
				
		+ Third Handshake(`seq = x + 1` and `ack = y + 1`)
		
			- Client: Send a TCP segment with `SYN = 0` and `ACK = 1` to acknowledge the connection
			
	![TCP Connection - Establish]()	
	
	- Transfer
	
		+ Stop and wait: poor efficiency
		
		+ Lost ACK and Late ACK
		
		+ ARQ(Automatic Repeat reQuest)
		
			- Slider window
			
	- Release(4 Handshakes, Slides: pp39-43)

		+ First Handshake(`seq = u`)
					
			- Server: Monitor passively
		
			- Client: Send a TCP segment with `FIN = 1`
			
		+ Second Handshake(`seq = v` and `ack = u + 1`)
		
			- Server: Send a TCP segment with `ACK = 1`
			
		+ Third Handshake(`seq = w` and `ack = u + 1`)
		
			- Server: Close passively, and send a TCP segment with `FIN = 1` and `ACK = 1` (tell the client to close the connection)
			
		+ Fourth Handshake(`seq = u` and `ack = w + 1`)
		
			- Client: Send a TCP segment with `ACK = 1`			
			- Before releasing connection, the client must wait for 2MSL(end connection)
			
				+ To ensure the last ACK sent by A can reach B

				+ To prevent any invalid connection request segment from emerging
			
		![TCP Connection - Release]()	
		
![TCP Connection - Status]()

###UDP

+ Why

	- Simple
	
	- No connection establishment
	
	- Small segment header
	
+ Datagram(Slides: pp49-50)

###An application: NAT and PAT

+ NAT

	- The process of swapping one address for another in the IP packet header

	- Types
	
		+ Static
		
		+ Dynamic
		
		+ PAT(Port Address Translation, overload)
		
			- Used to allow many internal users to share a single inside global address
			
	- NAT Address Types(Slides: pp55-61)
		
		+ Inside Local address
		
		+ Inside Global address
		
		+ Outside Global address
		