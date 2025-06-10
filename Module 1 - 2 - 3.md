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