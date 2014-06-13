#OSI Layer 5-7: Application Layers

###The Session Layer

+ Synchronized

	- Checkpoint

+ Dialogue separation

###The Presentation Layer

+ Main Task

	- Present data in a form that the receiving device can understand
	
	- Three main functions
	
		+ Data formatting
	
			- Codes
			
				+ EBCDIC(Extended Binary Coded Decimal Interchange Code)
				+ ASCII(American Standard Code for Information Interchange)
				
			- Graphics
			
				+ GIF(Graphic Interchange Format)
				
				+ JPEG(Joint Photographic Experts Group)
				
			- Multimedia
		
		+ Data compression

		+ Data encryption 


###The Application Layer

![OSI Model]()

+ Main Tasks

	- Identifies and establishes the availability of intended communication partners

	- Synchronizes cooperating applications

	- Establishes agreement on procedures for error recovery

	- Control of data integrity
	
+ HTTP

+ FTP

	- FTP first establishes a control connection between the client and the server(port 21)

	- Then a second connection is established, which is a link between the computers through which the data is transferred(port 20)
	
+ TFTP

	- TFTP is a connectionless service that uses UDP

+ Telnet

	- To log into a remote server
	
+ SMTP(Simple Mail Transfer Protocol)

+ POP3(Post Office Protocol version 3)

+ SNMP

	- Facilitates the exchange of management information between network devices

+ DNS(Domain Name System)

	- Manages domain names and responds to requests from clients to translate a domain name into the associated IP address
	
+ Application Layer: Communication Ways(Slides: p30)
	