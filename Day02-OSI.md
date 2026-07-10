# Day 2 – OSI Model

**OSI Model**


The OSI model, developed by the International Organization for Standardization (ISO) in 1984, is considered the architectural model for communication between computers. This model divides the data transmission and reception process into seven layers, defining the specific tasks of each layer and how they interact with each other. The purpose of the OSI model is to provide a framework for different systems and technologies to work together in a compatible manner.



**Upper Layers:** These layers are where users and programs communicate with each other. In other words, the upper layers represent the tasks carried out by the software. The Application, Presentation, and Session layers are considered upper layers.

**Lower Layers:** These layers are concerned with how data is transmitted. They handle the physical transmission of data from one computer to another. The Physical, Data Link, Network, and Transport layers are the lower layers.

**1) Physical Layer**

Covers the functions necessary to physically transfer data in the form of bits over a communication medium.
It is the lowest layer of the OSI model.
Cables, connector standards are part of this layer (UTP, RJ45, RS-232C, V.35, and other port standards).
Defines how two or more devices can physically connect.
Defines whether the transmission mode between two devices will be simplex, half-duplex, or full-duplex.
Hardware examples include network adapters, repeaters, network hubs, etc.

**2) Data Link Layer**

This layer ensures reliable data transfer between computers or network devices over the network. It is responsible for framing the data, addressing (using MAC addresses), ensuring it reaches the correct destination, and detecting transmission errors.
It receives the data from a device wanting to send data, then breaks it into frames. Information like the destination address (addressing) and error-checking data are added to each frame. Afterward, the frames are sent across the network to the receiving device. On the receiving device, the Data Link Layer checks the frames for errors and forwards the data to the next layer (Network Layer). If an error is detected, this layer handles the necessary correction.
Framing: It packages the transmitted data into frames, marking the beginning and end of the data to ensure the receiver can interpret it correctly.
Addressing: Every network device uses a unique physical address (MAC address) in this layer. The Data Link Layer uses these addresses to ensure the data reaches the correct device.
Error Checking: Errors can occur during data transmission. The Data Link Layer detects errors in the transmitted frames and may correct some of them.
Flow Control: It controls the flow of data to prevent overwhelming the receiver with too much data at once, maintaining a balance between transmission and reception.

**3) Network Layer**

Manages data transmission between different networks. It handles logical addressing (IP addresses), routing, and packet forwarding.
When a data packet is sent, the Network Layer determines the path it must follow to reach its destination. This path may pass through several gateways or routers. At each hop, the Network Layer decides the next destination for the packet. This process continues until the packet reaches its destination.
Protocols used for routing traffic in the network are called Network Layer protocols. Examples include IP and IPv6.
Routing: The Network Layer determines the best path for data packets from source to destination, using various routing algorithms to select the most optimal path based on network conditions.
Addressing: Each device has a unique address (such as an IP address). The Network Layer ensures the data packets are directed to the correct destination using these addresses.
Packetization: Data is broken into smaller units called packets at this layer. Each packet includes a header containing essential control information like the destination address.
Error Detection and Correction: This layer detects issues like packet loss or incorrect transmission and informs the higher layers.
Routers are Layer 3 devices, specified in this layer, and are used to provide inter-network routing services.

**4) Transport Layer**

The Transport Layer ensures reliable, accurate, and efficient end-to-end data transmission.
During this process, it handles flow control, error correction, and congestion management.
It receives data from the upper layer and divides it into smaller units called segments.
The Transport Layer takes data from the upper layer (Session Layer), segments it, and adds control information such as destination details and sequence numbers before sending it to the Network Layer.
It receives segments from the Network Layer, reassembles them, and forwards them to the upper layer (Session Layer).
Segmentation and Reassembly: When the Transport Layer receives a message from the upper layer, it divides it into multiple segments and assigns a unique sequence number to each segment. Upon arrival at the destination, the Transport Layer reassembles the message based on the sequence numbers.
Connection Control: The Transport Layer provides two types of services: connection-oriented and connectionless. A connectionless service treats each segment as an independent packet that may travel through different routes to the destination. A connection-oriented service establishes a connection with the transport layer on the target machine before delivering packets, with all packets following the same path.
Error Control: The Transport Layer is also responsible for error control. It performs end-to-end error correction, ensuring the message reaches the destination without errors.

**Transport Layer Protocols: Two main protocols are used at the Transport Layer:**

**TCP**
Provides reliable communication, guaranteeing that data packets are received without loss.
It is the standard protocol for internet communication.
When data is transmitted via TCP, it is divided into smaller units called segments. Each segment travels over multiple paths across the internet and may arrive at the destination in a different order. TCP rearranges the packets at the receiving end to restore the correct sequence.
**UDP**
Provides fast but unreliable communication. It consumes fewer resources than TCP but does not guarantee that the data will reach its destination in the correct order or error-free.
As the receiver does not send any acknowledgment, and the sender does not expect any acknowledgment, it is considered an unreliable transmission protocol.
An example of UDP usage is video streaming.

**5) Session Layer**

The Session Layer is responsible for managing communication sessions between applications. This layer handles the initiation, management, and termination of sessions.

**6) Presentation Layer**

This layer is part of the operating system that transforms data into another format.
It performs tasks like data compression and decompression, encryption and decryption, and ASCII conversion.
Data Formatting and Conversion: The Presentation Layer transforms data so it is compatible between systems, such as converting data from one system's format to one that can be understood by another.
Data Compression: To speed up transmission over the network, the Presentation Layer compresses data, reducing network traffic and increasing transmission speed.
Data Encryption and Security: The Presentation Layer uses encryption and security protocols (like SSL) to ensure data is transmitted securely, which is particularly important for sensitive data.
Data Encoding and Decoding: This layer is responsible for encoding data into a format that can be understood and decoded correctly by the target system.

**7) Application Layer**

The Application Layer contains the protocols and interfaces necessary for users to interact with network applications. It directly serves applications such as email, file transfer, remote access, and web browsing.

The Application Layer acts as a window for users and applications to access network services.
It handles network-related tasks such as resource allocation.
It is not an application itself but performs the functions that allow applications to work.
It provides network services to end users.
Communication is performed using various protocols. Some of these protocols include:
HTTP (Hypertext Transfer Protocol): Used for transmitting and viewing web pages over the internet.
FTP (File Transfer Protocol): Used for transferring files.
SMTP (Simple Mail Transfer Protocol): Used for sending emails.
POP3 (Post Office Protocol version 3) and IMAP (Internet Message Access Protocol): Used for receiving emails.
When a user accesses a website through a web browser, the Application Layer processes the request using the HTTP protocol. An HTTP request is sent to the relevant web server, and the server prepares the requested web page to be delivered to the user via the HTTP protocol.

**Flow of a Data Packet from Source to Destination:**


Application Layer (Layer 7): The user requests a web page, typically via a web browser. The Application Layer receives the user's request and converts it into an appropriate format for the network. Protocols like HTTP and FTP operate at this layer.

Presentation Layer (Layer 6): This layer converts the data into an appropriate format for transmission over the network (e.g., encryption, compression).

Session Layer (Layer 5): Establishes, maintains, and terminates the communication session between the source and destination.

Transport Layer (Layer 4): The data is divided into segments. If using TCP, the Transport Layer ensures that each segment reaches its destination reliably and in order.

Network Layer (Layer 3): The segments are broken down into packets. This layer adds logical addressing information (e.g., IP address) to ensure the packets are delivered to the correct device across networks.

Data Link Layer (Layer 2): The packets are framed into data units (frames) and the MAC address is added for local network addressing.

Physical Layer (Layer 1): The data is converted into electrical, optical, or radio signals for transmission over the physical medium (cables, fiber optics, wireless channels).
