#Routing and Routers

###Router Basics

+ Internal Components

	- RAM
		
		+ Stores Routing tables, ARP cache, Fast switching cache, Packet buffering and Packet hold queues
	
	- NVRAM(Non-volatile RAM)
	
		+ Stores backup/startup configuration files
	
	- Flash
	
		+ Stores Cisco IOS
	
	- ROM
	
		+ Contains POST(Power On Self Test)
		
		+ Loads Cisco IOS
		
		+ Operates system software
	
	- Console
	
	- Auxiliary
	
	- Interfaces
	
		+ Network connections through which packets enter and exit the router
		
		+ Attached to the motherboard or as separate modules

###Router Startup procedure

+ POST

+ Verify the basic operation of CPU, memory and network interface ports

+ Software init

	- Bootstrap Loader in ROM
	
	- Find OS and boot
	
	- Load OS
	
	- Load conf. saved in NVRAM
	
	- If no vaild conf., executes a question-driven init. conf.
	
###Routing

+ Switching function

	- Allows a router to accept a packet on one interface and forward it through a second interface
	
+ Path determination

	- Enables the router to select the most appropriate interface for forwarding a packet
	
+ Static & Dynamic

	- Static: Hide, one-to-one
	
			ip route network [mask] {address | interface} [distance]
			
		+ Administrative Distance: a rating of the trustworthiness from 0 to 255(the higher the number, the lower the trustworthiness rating)
		
	- Dynamic: Share knowledge
	
		+ Maintenance of a routing table
		
		+ Distribution of knowledge to other routers
		
		+ Classification
			
			- Distance Vector(Bellman-Ford)
			
				+ Problem: Routing Loops, Counting to Inf.
				
				+ Solution
				
					- Defining a Maximum
					
					- Route Poisoning
					
					- Split Horizon
					
					- Hold-Down Timers
					
				+ Prevent
				
						Router(config-router)#Passive-interface f0/0
			
			- Link State
			
				+ Known as SPF(shortest path first) algorithms
				
				+ Concern: Processing & Memory, Bandwidth
				
				+ Problem: Link-state Updates
				
			- Hybrid Routing(IS-IS, EIGRP)
			
				+ Share attibutes of both Distance Vector & Link State
				
				> Notes:
				
				> RIP - a distance-vector routing protocol
				
				> IGRP - Cisco’s distance-vector routing protocol
				
				> OSPF - a link-state routing protocol
				
				> EIGRP - a balanced hybrid routing protocol
				
###Router configuration

+ Primary Goals

	- Optimal Route
	
	- Efficiency
	
	- Rapid Convergence
	
	- Flexibility

+ Configure

		Router(config)# router protocol [keyword]
		// Defines an IP routing protocol
		// protocol: either RIP, IGRP, OSPF, or EIGRP
		// options: such as autonomous system, which is used with protocols that require it, such as IGRP
		Router(config-router)# network network-number
		// Specifies a directly-connected network
		
+ Define Default Route

	- Using dynamic route
	
			Router(config)# ip default-network [network-number]
			//network-number: IP network number or subnet number defined as the default
			
	- Using static route
	
			Router(config)# ip route 0.0.0.0 0.0.0.0 [next-hop-ip-address| exit-interface]
			// use show ip route