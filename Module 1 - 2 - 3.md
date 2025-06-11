## Module 1:
### Network Device Roles

- **Hosts**: Devices directly involved in network communication, assigned an **IP address**.
    - **Servers**: Provide services (email, web); require specific server software.
    - **Clients**: Request and display info (e.g., via web browsers); can run multiple client software types.
- **Peer-to-Peer**: Computers act as both clients and servers.
    - **Pros**: Easy setup, low cost, simple sharing.
    - **Cons**: No central admin, less secure, poor scalability, performance degradation.
- **End Devices**: Source or destination of messages. Each has a unique address.
- **Intermediary Devices**: Connect end devices, manage data flow, and link networks.
    - **Functions**: Regenerate signals, maintain pathways, handle errors, direct data, prioritize traffic, implement security.
    - **Examples**: Wireless router, LAN switch, router, multilayer switch, firewall.
- **Network Media**: Channel for data transmission.
    - **Types**: Metal wires (electrical signals), Fiber optic cables (light pulses), Wireless (electromagnetic waves).

---

### Network Representations & Topologies

- **Network Representations**: Show component connections, locations, and interactions.
    - **Diagram Symbols**:
        - **End Devices**: Desktop, laptop, printer, IP phone, tablet, TelePresence endpoint.
        - **Intermediary Devices**: Wireless router, LAN switch, router, multilayer switch, firewall.
        - **Network Media**: Wireless, LAN, WAN cloud.
    - **Terms**:
        - **NIC (Network Interface Card)**: Connects end device to network.
        - **Physical Port**: Connector for media on a device.
        - **Interface**: Router ports connecting to networks (interchangeable with 'port').
- **Topology Diagrams**: Visual maps of a network.
    - **Physical Topology**: Shows **physical location** of devices and **cabling**.
    - **Logical Topology**: Shows **devices, ports, and IP addressing schemes**.

---

### Network Sizes & Types

- **LAN (Local Area Network)**:
    - **Scope**: Small geographical area (home, office, campus).
    - **Admin**: Single control.
    - **Speed**: High-speed bandwidth.
    - **Example**: Network within a building.
- **WAN (Wide Area Network)**:
    - **Scope**: Wide geographical areas (cities, countries).
    - **Connects**: Multiple LANs.
    - **Admin**: Managed by multiple service providers (SPs/ISPs).
    - **Speed**: Slower links than LANs.
- **The Internet**: Global network of interconnected LANs & WANs.
    - No single ownership; governed by **common standards and cooperation**.
    - **Organizations**: IETF, ICANN, IAB.
- **Intranet**: Private network (LANs/WANs) **within an organization**, accessible only to authorized members.
- **Extranet**: Provides **secure access to external users** (e.g., suppliers, partners) to an organization's internal systems.

---

### Internet Connection Types

- **Home & Small Office**:
    - **Cable**: High bandwidth, always-on (uses TV line).
    - **DSL (ADSL)**: High bandwidth, always-on (uses phone line; download > upload).
    - **Cellular**: Via mobile network (depends on signal strength).
    - **Satellite**: For remote areas (requires clear line of sight).
    - **Dial-Up**: Very low bandwidth, outdated (still useful for some mobile/remote needs).
- **Business**: Require high bandwidth, dedicated & managed services.
    - **Dedicated Leased Line**: Private circuit between sites (expensive, fixed cost).
    - **Metro Ethernet**: Extends LAN into WAN (high performance).
    - **Business DSL (SDSL)**: Equal upload & download speeds (better than home DSL).
    - **Satellite**: For backup or remote areas.

---

### Converging Networks

- **Traditional Networks**: Separate infrastructure for data, voice, and video.
- **Converged Networks**: Single network carries **data, voice, and video** over the same infrastructure, using unified rules. More efficient and cost-effective.

---

### Network Architecture Characteristics

- **Fault Tolerance**: Ability to operate despite component failures.
- **Scalability**: Ability to expand easily to support more users/services.
- **Quality of Service (QoS)**: Prioritizes different types of network traffic (e.g., voice over email).
- **Security**:
    - **Confidentiality**: Data accessible only to authorized users.
    - **Integrity**: Data remains unaltered during transit.
    - **Availability**: Data and services are reliably accessible when needed.

## Module 2:

**Why do we not use hubs?**

-> because hub is a layer 1 device and all collision avoidance protocols are for L2 devices so hub is prone to collisions.
-> because of this the devices connected to hub must be half duplex only.

---
### Memory:
#### 3 types only: 
1. Flash Memo - used to store OS and VLAN only.
2. NVRAM - non volatile random access memory.
	- DHCP info, Hostname, Passwords etc.
3. RAM - 

### Hub connectivity:
- Hubs do not have their own MAC addresses because they are L1 devices.
- In Cisco Packet Tracer, we use hubs as switches
- Hubs (and switches) maintain a CAM (Content Address Memory) table that has two attributes: port number of the hub, and the MAC address of the device connected to that particular port.
- Hub sends a HELLO packet every 4 seconds to the connected device and if no response is received for 3 consecutive packets then it removes the entry from its CAM table
- Hub broadcasts received packets to all connected devices and all devices except for the destination device drop the packet.

##### APIPA:
**Automatic Private IP Addressing**
- Gives temporary IP address that cannot facilitate communication.









---

## Module 3:
### Communication Fundamentals & Protocols

#### 3.1.2 Communication Fundamentals

- **Core Idea**: For communication to occur, devices need physical connection + "how" to communicate (rules).
- **3 Common Elements of Communication**:
    1. **Message Source (Sender)**: Initiates the message.
    2. **Message Destination (Receiver)**: Interprets the message.
    3. **Channel**: Medium/pathway for the message.

#### 3.1.3 Communication Protocols

- **Protocols**: Rules governing communication, specific to the medium.
- **Analogy (Human Communication)**: Agreement on language, message format (grammar, sentence structure).
- **Network Communication**: Devices must agree on "how" to communicate and format messages for understanding.

#### 3.1.4 Rule Establishment

- **Importance**: Without established rules/protocols, messages are difficult to understand.
- **Protocols Account for**:
    - Identified sender and receiver.
    - Common language and grammar.
    - Speed and timing of delivery.
    - Acknowledgment requirements.

#### 3.1.5 Network Protocol Requirements

- Network protocols build on fundamental communication rules.
- **Define Details of Transmission**: How messages are sent across a network.
- **Common Requirements**: encoding, formatting, encapsulation, size, timing, delivery options
#### 3.1.6 Message Encoding

- ***Encoding: Process of converting info into an acceptable form for transmission.***
- **Decoding**: Reverses the encoding to interpret info.
#### 3.1.7 Message Formatting and Encapsulation

- Messages need specific format/structure (depends on type & channel).
- Network Example: IP (Internet Protocol) acts like an envelope, identifying source/destination (e.g., IPv6 fields) to send messages across networks.
#### 3.1.8 Message Size

- Long messages are broken into **smaller pieces (frames)** for network transmission.
- **Rules**: Strict minimum/maximum size requirements for frames; different per channel.
- **Process**: Source breaks message, each frame gets addressing info, receiver reconstructs.
#### 3.1.9 Message Timing

- **Flow Control**: Manages data transmission rate (how much/how fast). 
	- Prevents overwhelming receiver.
- **Response Timeout**: Specifies wait time for responses; action if no response.
- **Access Method**: Determines when a device can send a message (e.g., WLAN NIC checks if medium is available to avoid collisions).

#### 3.1.10 Message Delivery Options

- **Unicast**: Information to a **single** end device.
- **Multicast**: Information to **one or more** (a group of) end devices.
- **Broadcast**: Information to **all** end devices on the network.

---
### Protocols

| Protocol Type           | Description                                                                         |
| ----------------------- | ----------------------------------------------------------------------------------- |
| Communication protocols | Enable devices to communicate over a network, ex: http, tcp                         |
| Security                | Secure data to provide auth, encryption, integrity. ex: SSH, SSL                    |
| Routing                 | Allow routers to exchange and compare path info and find best routes. ex: OSPF, BGP |
| Service discovery       | Automatic detection of devices or services near you. ex: DHCP                       |

#### Protocol Functions:
1. **Addressing**: identifies sender and receiver. ex: IP
2. **Reliability:** guaranteed delivery. managed by TCP
3. **Flow Control:** speed and amount of data communicated. managed by TCP
4. **Sequencing:** uniquely labels each segment of data. managed by TCP
5. **Error Detection:** detects data corruption occurred during transmission.
6. **App interface:** info for process-to-process communication, ex: http, https

- **Hypertext Transfer Protocol (HTTP)** - This protocol governs the way a web server and a web client interact. HTTP defines the content and formatting of the requests and responses that are exchanged between the client and server. Both the client and the web server software implement HTTP as part of the application. HTTP relies on other protocols to govern how the messages are transported between the client and server.
- **Transmission Control Protocol (TCP)** - This protocol manages the individual conversations. TCP is responsible for **guaranteeing the reliable delivery** of the information and managing flow control between the end devices.
- **Internet Protocol (IP)** - This protocol is responsible for delivering messages from the sender to the receiver. IP is used by routers to forward the messages across multiple networks.
- **Ethernet**- This protocol is responsible for the delivery of messages from one NIC to another NIC on the same Ethernet local area network (LAN).

### Network Protocol Suites

#### 3.3.1 Network Protocol Suites Fundamentals

- **Protocol Suite**: A group of inter-related protocols that work together for network communication.
- **Protocol Stack**: Visualizes how protocols in a suite are implemented in layers.
    - Lower layers: Moving data over network.
    - Upper layers: Focus on message content.

#### 3.3.4 TCP/IP Protocol Suite Details

- **Open Standard**: Freely available, usable by any vendor.
- **Standards-Based**: Endorsed by industry/organisations, ensuring interoperability.
- **Key Protocols by Layer**:
    - **Application Layer**:
        - **Name System**: DNS (Domain Name System - domain names to IP addresses).
        - **Host Config**: DHCPv4/v6 (Dynamic Host Configuration Protocol - assigns IP addresses), SLAAC (Stateless Address Autoconfiguration - IPv6 without DHCPv6).
        - **Email**: SMTP (sending), POP3 (retrieving, downloading), IMAP (accessing/maintaining on server).
        - **File Transfer**: FTP (reliable file transfer), SFTP (secure FTP via SSH), TFTP (simple, unacknowledged file transfer).
        - **Web/Web Service**: HTTP (web exchange), HTTPS (secure HTTP), REST (web service APIs).
    - **Transport Layer**:        
        - **Connection-Oriented**: TCP (Transmission Control Protocol - reliable, acknowledged, confirmed delivery).
        - **Connectionless**: UDP (User Datagram Protocol - unconfirmed, best-effort delivery).
    - **Internet Layer**:
        - **Internet Protocol**: IPv4 (32-bit addressing, packages messages into packets), IPv6 (128-bit addressing).
        - **NAT**: Network Address Translation (translates private IPv4 to public IPv4).
        - **Messaging**: ICMPv4/v6 (Internet Control Message Protocol - error feedback), ICMPv6 ND (Neighbor Discovery - address resolution, duplicate detection).
        - **Routing Protocols**: OSPF (Open Shortest Path First - link-state, open standard), EIGRP (Enhanced Interior Gateway Routing Protocol - Cisco, composite metric), BGP (Border Gateway Protocol - exterior, between ISPs).
    - **Network Access Layer**:
        - **Address Resolution**: ARP (Address Resolution Protocol - IPv4 to hardware/MAC address mapping). _Note: In this context, it's considered Layer 2._
        - **Data Link Protocols**: Ethernet (wired LAN rules), WLAN (wireless LAN rules - 2.4/5 GHz).
---
### Network Standards

#### 3.4.1 Open Standards:

- **Purpose**: Ensure **interoperability** among different network components from various manufacturers, just like car parts.
- **Benefits**: Encourages **interoperability, competition, and innovation**. Prevents monopolies.

Organisations:
- **Internet Society (ISOC)**: Promotes global internet development and use.
- **Internet Architecture Board (IAB)**: Manages and develops overall internet standards.
- **Internet Engineering Task Force (IETF)**: Develops, updates, and maintains internet/TCP/IP technologies, including **Request for Comments (RFC)** documents for new/updated protocols.
- **Internet Research Task Force (IRTF)**: Focuses on long-term internet research (e.g., anti-spam, crypto, P2P).
- **Internet Corporation for Assigned Names and Numbers (ICANN)**: Coordinates IP address allocation, domain name management, and protocol assignments.
- **Internet Assigned Numbers Authority (IANA)**: Oversees and manages IP address allocation, domain names, and protocol identifiers for ICANN.
- **Institute of Electrical and Electronics Engineers (IEEE)**: Advances technological innovation and creates standards in various industries, including networking. Key standards include **802.3 Ethernet** and **802.11 WLAN**.
- **Electronic Industries Alliance (EIA)**: Known for standards related to electrical wiring, connectors, and 19-inch racks for networking equipment.
- **Telecommunications Industry Association (TIA)**: Develops communication standards for radio equipment, cellular towers, VoIP, satellite communications, etc.
- **International Telecommunications Union-Telecommunication Standardisation Sector (ITU-T)**: One of the largest and oldest communication standards organisations; defines standards for video compression, IPTV, and broadband communications (e.g., DSL).

---
#### 3.6.1 Segmenting Messages

- **Problem**: Sending large, uninterrupted data streams (e.g., video, large email) across a network causes delays for others and total retransmission if a link fails.
- **Solution**: **Segmentation** – dividing data into smaller, manageable units (IP packets) for transmission.
- **Benefits of Segmentation**: speed and efficiency.
#### 3.6.2 Sequencing

- **Challenge of Segmentation**: Segments might arrive out-of-order.
- **Solution**: **Sequencing** – attaching a sequence number to each segment.
- **Responsibility**: **TCP** is responsible for sequencing segments to allow the receiver to reassemble the original message correctly.
---
#### **Address Purposes**:

- **Network Layer Addresses (IP)**: Deliver the IP packet from the **original source** to the **final destination** (can be on same or remote network).
- **Data Link Layer Addresses (MAC)**: Deliver the data link frame from one **NIC** to another **NIC on the same network**.
##### Data Link Addresses 

- **Purpose**: To deliver the data link frame from **NIC-to-NIC** on the **same network**.
- **Encapsulation**: Before IP packets are sent over a medium, they are encapsulated in a data link frame.
- **Hop-by-Hop**: As an IP packet travels through the network (host-to-router, router-to-router, router-to-host), it's repeatedly encapsulated in _new_ data link frames at each hop.
- **Frame Contents**:
    - **Source data link address**: Physical address of the sending NIC for _that specific hop_.
    - **Destination data link address**: Physical address of the receiving NIC for _that specific hop_ (either the next router or the final destination device).

#### Role of Data Link Layer Addresses - Same IP Network

- When sender and receiver are on the **same network**, the data link frame is sent **directly** to the receiving device.
- **Ethernet MAC Addresses**: Data link addresses for Ethernet networks, physically embedded on NICs.
- **Frame Contains**:
    - **Source MAC address**: MAC of the sending NIC.
    - **Destination MAC address**: MAC of the receiving NIC (of the final destination device).
    
#### 3.7.7 Role of the Data Link Layer Addresses - Different IP Networks

- When the destination is on a **different network**, the Ethernet frame **cannot be sent directly** to the final destination.
- The frame is sent to the **default gateway (router)** on the sender's local network.
- **Frame Contains**:
    - **Source MAC address**: MAC of the sending device's NIC (e.g., PC1's MAC).
    - **Destination MAC address**: MAC of the **default gateway's** interface on the sender's local network.
-  **Router Action**: The router removes the old Layer 2 info, processes the IP packet, and adds _new_ Layer 2 info for the next hop (another router or the final destination) before forwarding.
- **Default Gateway Importance**: Every host must be configured with its default gateway's IP address to send packets to remote networks.