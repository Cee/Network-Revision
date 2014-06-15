#LAN Switching and VLAN

###Switch

+ Main Task

	- Building and maintaining switching tables
	
	- Switching frames out the interface to the destination
	
+ Switching

	- Symmetric: Provide switched connections between ports with the same bandwidth
	
	- Asymmetric: Require memory buffering
	
		+ Port-based memory buffering
		
		+ Shared memory buffering
		
+ Switching Methods

	- Store-and-Forward: receives the entire frame, calculating the CRC at the end, before sending it to the destination
	
	- Cut-through
		
		+ Fast forward switching: only checks the destination MAC  before immediately forwarding the frame
		
		+ Fragment Free: reads the first 64 bytes to reduce errors before forwarding the frame
		
+ Layer Switching

	- Layer 2: Data-Link
	
		+ Low cost
		
		+ Low latency
		
		+ High-speed
		
		+ Hardware-based bridging
		
		+ MAC address
		
	- Layer 3: Network
		
		+ Qos
		
		+ Security
		
		+ Flow accounting
		
		+ Low latency
		
		+ Low per-port cost
		
		+ High-speed scalability
		
		+ Hardware-based packet forwarding
		
	- Layer 4: Transport
	
		+ Based on Layer 3
		
		+ TCP/UDP Fields
		
		+ Qos
		
		+ Traffic control
		
	- Multilayer
	
		+ Low latency
		
		+ High-speed scalability
	
###The Spanning-Tree Protocol

+ Loops

	- Layer 2
	
		+ No TTL field
		
		+ Filp flop the bridging table entry
		
+ Overview of STP

	- Main function: allow redundant paths
	
	- Prevent loops: calculate a stable spanning-tree network
	
	- Spanning-tree frames(BPDU, Bridge Protocol Data Unit)
	
+ Decision Sequence

	- Lowest root BID(Bridge Identification)
	
		+ BID: 8bytes
		
			- Bridge priority(2 bytes): 0-65535 possible values
			
			- MAC address assigned to the switch(6 bytes)
				
	- Lowest path cost to root bridge
	
	- Lowest sender BID
	
	- Lowest port ID

+ STP cost values: lower costs are better
		
	- Bridges use the concept of cost to evaluate how close they are to other bridges
		
+ Electing the Root Switch
		
	- The switches elect a single root switch by looking for the switch with the lowest BID
			
	- If all the switches are using the default bridge priority of 32,768, the lowest MAC address serves as the tie-breaker
			
+ Five STP States
		
	- Blocking: frames forwarded, BPDUs heard
			
	- Listening: no frames forwarded, listening for data frames

	- Learning: no frames forwarded, learning addresses

	- Forwarding: frames forwarded, learning addresses

	- Disabled: no frames forwarded, no BPDUs heard

*continue on pp25.*	
	
	