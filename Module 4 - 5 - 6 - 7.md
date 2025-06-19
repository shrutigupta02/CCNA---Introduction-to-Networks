## Module 4:
### Physical Layer: Core Objective & Functions

- **Objective**: Carry raw data (voltage, light, electromagnetic waves) from source to destination.
- **Key Functions**:
    - **Multiplexing/Demultiplexing**: Combine/separate signals (TDM, WDM for wired; FDM for wireless).
    - **Modulation/Demodulation**: Attach weak signals to strong carrier signals for transmission.
    - **Encoding**: Convert data bits into recognizable codes (e.g., Manchester encoding: 0 → high-low, 1 → low-high voltage).
    - **Signalling**: Physical representation of bits (electrical, optical, radio waves).

---

### Physical Layer Standards & Components

- **Hardware Layer**: Deals with circuits, media, and connectors.
- **Standard Bodies**: ISO, IEEE, ANSI, ITU, TIA/EIA, FCC, ETSI, CSA, CENELEC, JIS. (IETF for TCP/IP upper layers).
- **Components**: NICs, connectors, cables, interfaces, hardware ports.

---

### Bandwidth Terminology

- **Bandwidth**: Data capacity of a medium (kbps, Mbps, Gbps). Not speed.
- **Latency**: Time for data to travel end-to-end. Combining all delays as well.
- **Throughput**: Actual/Successful bits transferred per second (often < bandwidth).
- **Goodput**: Usable data transferred (throughput - unusable data like header files).

---

### Wired Media

- **Types**: Twisted Pair, Fiber Optic, Coaxial.

#### Copper Cabling

- **Characteristics**: Cheap, easy to install, low resistance. Data as electrical pulses.
- **Limitations**:
    - **Attenuation**: Signal weakens over distance.
    - **EMI/RFI**: Electromagnetic/Radio Frequency Interference (external distortion).
    - **Crosstalk**: Interference from adjacent wires.
- **Countermeasures**: Shielding (for EMI/RFI), twisting pairs (for crosstalk).
- **Types**:
    - **UTP (Unshielded Twisted Pair)**: Most common in LANs. 4 twisted pairs in a plastic sheath. Uses RJ-45. Relies on cancellation and varying twist rates for noise reduction.
        - **Categories**:
            - Cat 5/5e: 100 Mbps / 1 Gbps
            - Cat 6/6a: up to 10 Gbps
            - Cat 7/8: up to 40 Gbps
            - twisted pair has 4 pairs: 
				- orange - orange white (1-2)
				- green - green white (3 - 6)
				- blue - blue white (4 - 5) 
				- used for poe -> power on ethernet, uses dc current ideally 40V
				- brown white - brown (7 - 8)
				- used for VoIP
				![How to Distinguish T568A and T568B of RJ45 Ethernet Cable Wiring?](https://media.licdn.com/dms/image/v2/C4E12AQG6kZ5vRJtRCA/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1520147644406?e=1753920000&v=beta&t=NXUFWTpFtS44wVVHu-762a5rJfPCaBNc2mG5MLB_tPI)
        - **Cable Types**:
            - **Straight-through**: Host ↔ Switch, Switch ↔ Router.
            - **Crossover**: Switch ↔ Switch, Host ↔ Host, Router ↔ Router (largely replaced by auto-MDIX).
            - **Rollover**: PC → Router/Switch console (Cisco proprietary).
    - **STP (Shielded Twisted Pair)**: Better noise protection than UTP (shielding + twisting). More expensive, harder to install, requires proper grounding.
    - **Coaxial Cable**: Two conductors sharing an axis (inner copper + insulation + metallic shield + jacket). Used in wireless antennas, cable internet. Connectors: BNC, N, F.

- ###### Data Terminal Equipment (DTE): 
- It includes any unit that functions either as a source of or as a destination for binary digital data.
- ex: PC, router, printer.
- ###### Data Communication Equipment (DCE):
- It is a device used as an interface between a DTE.
- ex: switch, modem.

#### Fiber-Optic Cabling

- **Characteristics**: Transmits light impulses over thin glass strands.
    - **Advantages**: Long distances, high bandwidth, low attenuation, immune to EMI/RFI.
    - **Disadvantages**: Expensive, harder to install.
- **Types**:
    - **Single-Mode Fiber (SMF)**: Single ray of light (laser-based). Hundreds of km. Low dispersion. Yellow jacket.
    - **Multimode Fiber (MMF)**: Multiple rays of light. Up to 500m. Higher dispersion. Orange/Aqua jacket.
- **Usage**: Enterprise backbone, FTTH, long-haul, submarine cables.
- **Connectors**: ST (bayonet), SC (snap-in), LC (small form), Duplex LC. SFP transceivers common.

---

### Wireless Media

- **Characteristics**: Uses radio/microwave frequencies.
    - **Advantage**: Mobility.
    - **Limitations**:
	    - **Half Duplex**
        - Limited coverage area (materials/terrain).
        - Interference (household devices).
        - Security risks (no physical medium).
        - Shared medium (one device transmits at a time).
- **Types**:
    - **Wi-Fi (802.11)**: WLAN, uses CSMA/CA.
    - **Bluetooth (802.15)**: WPAN, 1-100m range.
    - **WiMAX (802.16)**: Wireless broadband.
    - **Zigbee (802.15.4)**: Low-power IoT (sensors, lights).
- **WLAN Components**: Wireless Access Point (AP), Wireless NIC adapters.
- **Benefits**: Cost savings on cabling, mobility.
- **Security**: Critical due to ease of access.

---

## Module 6:
#### Data Link Layer:
- **Node to Node communication**: a node is a device that can receive, create, store, or forward data along a communications path. Eg: Laptop, PC, Switch.
  
- **Purpose:
	1.  **Frame delimiting**: Describe the start of frame and end of frame.
	2. **Error Detection**: Includes a trailer used to detect transmission errors. 32 bit CRC
	3. **Flow Control / Addressing**: Provides source and destination addressing for transporting the Layer 2 frame between devices on the same shared medium.
	  
- **Divided into two sublayers:
	1. **LLC** -> Logical Link Control: IEEE 802.2 
		- communicates between the networking software at the upper layers and the device hardware at the lower layers.
		-  It **places information in the frame that identifies which network layer protocol is being used for the frame**. This information allows multiple Layer 3 protocols, such as IPv4 and IPv6, to use the same network interface and media.
	2. **MAC Sublayer**: IEEE 802.3(Ethernet), 802.11(WLAN), or 802.15(WPAN)
		- responsible for data **encapsulation and media access control.**


###### At each hop along the path, a router performs the following Layer 2 functions:

1. Accepts a frame from a medium
2. De-encapsulates the frame
3. Re-encapsulates the packet into a new frame
4. Forwards the new frame appropriate to the medium of that segment of the physical network

### Topologies:

The topology of a network is the arrangement, or the relationship.

**Physical topology** - Identifies the physical connections and how end devices and intermediary devices (i.e, routers, switches, and wireless access points) are interconnected.

**Logical topology** - Refers to the way a network transfers frames from one node to the next. This topology identifies virtual connections using device interfaces and Layer 3 IP addressing schemes.

### WAN Topologies:
1. **Point to point**: This is the simplest and most common WAN topology. It consists of a permanent link between two endpoints.
2. **Hub and Spoke**: This is a **WAN version of the star topology** in which a central site interconnects branch sites through the use of point-to-point links
3. **Mesh**: every end system is interconnected to every other system.

### LAN Topologies:
**in LANs, end devices (i.e., nodes) are interconnected using star or extended star topologies. The star and extended topologies are easy to install, very scalable (easy to add and remove end devices), and easy to troubleshoot**

**Bus** - All end systems are chained to each other and terminated in some form on each end.
**Ring** - End systems are connected to their respective neighbor forming a ring.


---

## Module 7:

