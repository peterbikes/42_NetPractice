# NetPractice

_NetPractice is a general practical exercise to let you discover networking._

The following is just a collection of notes I took while studying for this project.
No actual files had to be turned for evaluation other than the `.json` files also present in this repository.

### IP

An IP, or Internet Protocol, is a set of rules governing data format for internet and local network communication. IP addresses, unique numerical labels, identify devices on computer networks using this protocol. They serve two main purposes:

IP addresses serve two main purposes in computer networking:
 
**Host Identification:** IP addresses are used to identify and locate devices on a network. Just as your home address helps mail carriers find your house, an IP address helps routers and other network devices route data packets to the correct destination. It uniquely identifies a device on a particular network.

**Routing:** IP addresses are essential for routing data packets across networks. When you send data over the internet or any network, it gets broken down into small packets. Each packet contains the source and destination IP addresses. Routers use these addresses to determine where to send the packets next, ensuring they reach their intended destination.


### TCP - Transmission Control Protocol

TCP is a transport layer protocol in the TCP/IP suite. It ensures reliable, connection-oriented data transmission with features like reliability, ordered delivery, a connection setup process, and flow control.

TCP and IP are closely related protocols fundamental to data transmission on the internet and networks. They work together for reliable data communication:

**Difference between TCP and IP:**
TCP focuses on reliable data transfer and connection setup, while IP handles routing and addressing. TCP guarantees data integrity and order, whereas IP provides best-effort delivery. TCP establishes connections; IP routes packets based on destinations.

In summary, TCP and IP collaborate in the TCP/IP suite, with TCP ensuring data reliability and IP handling packet addressing and routing. Together, they underpin modern internet communication.

<details>
<summary> <b> Click me for the long version </b> </summary> 

The TCP/IP model, also known as the Internet protocol suite, is a conceptual framework that defines the functions and relationships of networking protocols used to enable communication over the Internet and other interconnected networks. It consists of four distinct layers, each responsible for specific aspects of network communication. These layers are often compared to the OSI (Open Systems Interconnection) model, but the TCP/IP model is more commonly used in practical networking contexts.

The TCP/IP model has four layers, while the OSI model has seven layers, and they serve as conceptual frameworks for understanding how network protocols and communication work.

Here's a breakdown of the four layers in the TCP/IP model:

Application Layer: This layer is responsible for end-user applications and services. It includes protocols and functions that directly interact with applications and provide various network services, such as email (SMTP), web browsing (HTTP), file transfer (FTP), and remote access (SSH). The application layer enables communication between software applications running on different devices.

Transport Layer: The transport layer, as discussed earlier, is where protocols like TCP and UDP operate. It provides end-to-end communication services for data exchange between devices. TCP ensures reliable and ordered data transmission, while UDP offers a connectionless and simpler approach suitable for applications where speed is more critical than reliability.

Internet Layer: This layer is where the Internet Protocol (IP) operates. Its primary function is to facilitate the routing of packets across networks. It deals with addressing and packet forwarding, allowing data to traverse various interconnected networks to reach its destination. IP (both IPv4 and IPv6) is a fundamental part of this layer.

Network Interface (Link) Layer: Also known as the Network Layer in some contexts, this layer is responsible for the physical transmission of data packets over a specific network medium, such as Ethernet, Wi-Fi, or other technologies. It deals with hardware addressing (MAC addresses), frame formatting, and the actual transmission of data bits.

In summary, the four layers in the TCP/IP model represent different stages and functions of network communication, starting from applications and user interactions down to the physical transmission of data over the network medium. These layers help organize the various protocols and technologies involved in networking, making it easier to understand and troubleshoot network communication processes.


<b> How TCP/IP work's, broken down into steps: </b>

1. **Data Segmentation (Transport Layer - TCP):** When data is sent from one computer (or device) to another, it is first broken down into smaller units called "segments." The Transport Layer, specifically the TCP protocol, handles this segmentation. TCP ensures that data is divided into manageable segments, each with a sequence number for tracking and reassembly.

2. **Addressing and Routing (Internet Layer - IP):** Once the data is segmented, the Internet Layer (IP) comes into play. IP adds addressing information to each segment, including the source and destination IP addresses. The source and destination IP addresses are crucial for routing the data across the network. Routers and other network devices use this addressing information to determine where to forward the data.

3. **Packet Routing:** The data, now divided into IP packets, is sent into the network. Routers, which are network devices that connect different segments of a network or the internet, examine the destination IP address on each packet and make decisions about how to route the packets toward their final destination. This process continues until the packets reach their intended destination.

4. **Packet Delivery to the Host (Link Layer - Network Interface):** At the physical layer of the network, such as Ethernet or Wi-Fi, the packets are transmitted over the physical medium using hardware addressing (MAC addresses). Network Interface Cards (NICs) in devices use MAC addresses to ensure that the packets are delivered to the correct device within the local network.

5. **Data Reassembly (Transport Layer - TCP):** Once the packets arrive at the destination device, they are received by the Transport Layer, which may be using TCP as the transport protocol. TCP checks the sequence numbers on the incoming packets to ensure they are in the correct order and have arrived without errors. If any packets are missing or corrupted, TCP requests their retransmission.

6. **Delivery to the Application (Application Layer):** After successful reassembly of the data, the application or process at the destination (e.g., a web browser or email client) receives the complete and error-checked data. The data is then presented to the user or application for processing or display.

7. **Acknowledgments:** Throughout this process, TCP/IP includes mechanisms for acknowledgments (ACKs). When a packet is received successfully, the receiving end sends an acknowledgment back to the sender. If the sender does not receive an acknowledgment within a certain time, it assumes there was an issue and may retransmit the data.

8. **Connection Termination (Transport Layer - TCP):** When the communication is complete, TCP handles the termination of the connection. This involves a handshake to ensure both sides agree to end the connection gracefully.

</details>

### What is a switch?

A switch is a vital networking device at the data link layer (Layer 2) used in local area networks (LANs) to connect various devices like computers, printers, and servers. Unlike older hubs, switches use MAC addresses to intelligently direct data packets, enhancing network performance and security. They learn and associate MAC addresses with connected ports, making precise forwarding decisions to send data only to the appropriate destination. Switches also create separate collision domains, reducing congestion, and support Virtual LANs (VLANs) for improved network management and security, making them fundamental for efficient and reliable LAN communication.

<details>

<summary> <b> Click me for more information on switches </b> </summary>

1. **MAC Address Learning:** When devices connect to a switch, it learns their MAC addresses by examining incoming data frames' source MAC addresses, creating a MAC address table.

2. **Data Forwarding:** When a device wants to communicate with another, it sends a data frame with the destination MAC address. The switch uses its MAC address table to determine the correct port for the destination device.

3. **Forwarding Decision:** The switch forwards the data frame only to the port where the destination device is connected, reducing unnecessary traffic and congestion.

4. **Collision Domains:** Switches create separate collision domains for each port, allowing devices on different ports to transmit simultaneously without collisions, unlike network hubs.

5. **Broadcast Traffic:** While switches reduce broadcast traffic, they forward broadcast and multicast traffic as needed for services like ARP.

6. **VLAN Support:** Many modern switches support Virtual LANs (VLANs) to segment a LAN into logical networks, enhancing network management, security, and isolation.

</details>

### What is a Router?

A router is a hardware device that acts as a central hub for connecting multiple networks together. It is responsible for determining the best path for data packets to travel between different networks and forwarding them accordingly. Routers use network layer information, such as IP (Internet Protocol) addresses, to make routing decisions.


### What is a Modem?

A modem, short for "modulator-demodulator," is a hardware device that plays a critical role in connecting your computer or local network to the internet or other wide-area networks. Modems are essential for transmitting digital data over analog communication channels, such as telephone lines, cable systems, or fiber optics. They essentially bridge the gap between digital devices (like computers) and the analog communication infrastructure used by many ISPs (Internet Service Providers).


###  Router vs Modem

A modem is primarily responsible for connecting your local network to your ISP's network by converting digital data into analog signals for transmission, while a router is responsible for directing data traffic within your local network and managing connections to external networks, such as the internet. Both devices play critical roles in enabling internet connectivity for your devices.

Modem-router combo devices are common in households because they offer convenience, simplicity, and cost savings. They provide an all-in-one solution for connecting to the internet and creating a local network. However, users with more advanced networking requirements may opt for separate modem and router devices to gain greater control and customization options for their home network.

### Default Gateway

A default gateway is a network device, typically a router, that serves as the exit point for traffic from a local network to reach destinations outside the network, such as other networks or the internet. It acts as a central point for forwarding data packets to their intended destinations, allowing devices within the local network to communicate with devices on other networks. The default gateway is specified in network settings to direct outbound traffic that doesn't match a specific route to the appropriate external network.

### Loopback Address

A loopback address, often referred to as 127.0.0.1 in IPv4 or ::1 in IPv6, is a special network address used to establish network connections with the device itself. It's commonly used for testing and troubleshooting network-related software or services on a local machine without involving external networks. Data sent to the loopback address never leaves the device, ensuring a closed loop for self-testing purposes. It's a fundamental tool for diagnosing network issues and verifying network services on a computer.

### What is a Subnet?

A subnet, short for "subnetwork," is a logical subdivision of an IP network into smaller, manageable segments. Subnetting is a fundamental concept in IP addressing and network design, serving several purposes:

1. **Address Space Management:** Subnetting allows organizations to efficiently allocate and manage IP address resources. Instead of assigning a single IP address per device, subnets enable the allocation of smaller address blocks to specific network segments or departments.

2. **Network Segmentation:** Subnetting divides a larger network into smaller, isolated segments or subnetworks. This isolation enhances network security, reduces broadcast traffic, and improves overall network performance.

3. **Routing Efficiency:** Routers use subnet information to make routing decisions. By breaking down a large network into subnets, routers can make more granular and efficient routing choices, directing traffic only where it's needed.

4. **Broadcast Domain Control:** Each subnet forms a separate broadcast domain. This means broadcast traffic, such as ARP requests and DHCP broadcasts, is limited to the devices within the same subnet, reducing unnecessary network congestion.

5. **Security and Access Control:** Subnets can be used to enforce network security policies and access controls. Devices within the same subnet may have more relaxed access rules, while traffic between subnets can be subject to stricter controls.

6. **Network Efficiency:** Subnetting can optimize network design by grouping devices with similar functions or requirements together. For example, servers and workstations might be placed in different subnets based on their roles.

Subnets are defined by subnet masks, which determine the range of IP addresses within a subnet. For example, a subnet mask of 255.255.255.0 (in IPv4) signifies a subnet with 256 possible addresses (from 192.168.1.0 to 192.168.1.255), while more extensive subnets may have masks like 255.255.0.0 (allowing 65,536 addresses).

In summary, subnets are a critical networking concept that enables efficient IP address management, network segmentation, routing optimization, and improved network performance and security. They are fundamental in designing and maintaining complex IP networks.

--------
LinkedIn: https://www.linkedin.com/in/pedrosmpm
