## Categorized CLI Command Tables for IP Configuration and Network Management

---

### 🔧 **Windows Host Configuration Commands**

|**Command**|**Description**|
|---|---|
|`ipconfig`|Shows basic IP config info|
|`ipconfig /all`|Shows detailed IP and MAC info|
|`ipconfig /release`|Releases current IP address|
|`ipconfig /renew`|Renews IP address from DHCP|
|`ipconfig /displaydns`|Displays DNS resolver cache|
|`arp -a`|Shows ARP table (IP-to-MAC mappings)|
|`netsh interface ip delete arpcache`|Clears the ARP cache|


---

### 🌐 **Common Cisco IOS Show Commands**

|**Command**|**Description**|
|---|---|
|`show running-config`|Shows current config in RAM|
|`show interfaces`|Displays detailed interface status|
|`show ip interface`|IP config and interface status|
|`show arp`|ARP cache entries|
|`show ip route`|Routing table|
|`show protocols`|Protocol status on interfaces|
|`show version`|IOS version and device info|
|`show cdp neighbors`|Lists directly connected Cisco devices|
|`show cdp neighbors detail`|IP + platform details of neighbors|
|`show ip interface brief`|Summary of IP and interface status|

---

### 🚀 **Privileged EXEC Mode Commands**

| **Command**                         | **Description**                       |
| ----------------------------------- | ------------------------------------- |
| `enable`                            | Enters privileged EXEC mode           |
| `ping -l <size> <address>`          | Pings with custom packet size         |
| `show vlan brief`                   | VLAN configuration summary            |
| `show interfaces status`            | Interface status and port mode        |
| `show interfaces trunk`             | Displays trunk links                  |
| `show vtp status`                   | VTP version and mode                  |
| `show spanning-tree`                | Global STP info                       |
| `show spanning-tree vlan 1`         | STP info for VLAN 1                   |
| `spanning-tree vlan 1 root primary` | Set device as primary root for VLAN 1 |
| `show interfaces include Ethernet`  |                                       |
| `show etherchannel summary`         | Displays EtherChannel status          |
| `shutdown` / `no shutdown`          | Disables / enables an interface       |
| `show interfaces port-channel 1`    | EtherChannel port details             |
| `show ip protocols`                 | Shows routing protocols in use        |
| `show ip ospf interface g0/1`       | OSPF interface details                |
| `show ip ospf interface brief`      | Summary of OSPF interfaces            |
| `show controllers`                  | View DCE/DTE sides                    |
| `show ipv6 neighbor`                | Shows IPv6 MAC mappings               |
| `ipconfig /all`                     | (Windows) MAC and IP details          |
| `show hosts`                        | Displays DNS host entries             |
| `show ip dhcp binding`              | DHCP address bindings                 |

---

### ⚙️ **Global Configuration Mode Commands**

|**Command**|**Description**|
|---|---|
|`configure terminal`|Enters global config mode|
|`hostname <name>`|Sets device name|
|`enable secret <password>`|Sets encrypted password for enable mode|
|`service password-encryption`|Encrypts passwords in config|
|`banner motd #<msg>#`|Message of the Day banner|
|`ip route <dest> <mask> <next-hop>`|Static routing|
|`ip routing`|Enables L3 routing on switch|
|`vtp domain cisco`|Sets VTP domain|
|`vtp mode client` / `transparent`|Sets VTP mode|
|`vtp version 2`|Sets VTP version|
|`ip ospf cost 1000`|Sets OSPF cost metric|
|`bandwidth 10000`|Sets interface bandwidth|
|`ipv6 address <addr>/<prefix>`|Assigns IPv6 address|
|`ipv6 unicast-routing`|Enables IPv6 routing|
|`ipv6 enable`|Enables link-local addressing|
|`ipv6 address autoconfig`|Enables SLAAC (stateless autoconfig)|

---

### 🧾 **Line Configuration Mode Commands**

| **Command**                  | **Description**                                  |
| ---------------------------- | ------------------------------------------------ |
| `line console 0`             | Enters console line config mode                  |
| `password <pwd>; login`      | Sets password and enables login for console line |
| `line vty 0 4` / `0 15`      | VTY line config (Telnet/SSH access)              |
| `transport input ssh telnet` |                                                  |

---

### 🛠️ **Basic Router Initial Setup

```bash
Router(config)# hostname RouterName
Router(config)# enable secret <password>
Router(config)# line console 0
Router(config-line)# password <password>
Router(config-line)# login
Router(config)# line vty 0 4
Router(config-line)# password <password>
Router(config-line)# login
Router(config-line)# transport input ssh
Router(config-line)# exit
Router(config)# service password-encryption
Router(config)# banner motd #Welcome to the Router#
Router(config)# end
Router# copy running-config startup-config
```

Let me know if you'd like this exported as PDF, Markdown, or something more interactive!

## VLAN commands:
|**Command**|**Purpose**|**Mode**|
|---|---|---|
|`vlan <vlan-id>`|Creates a VLAN with the specified ID|Global Configuration|
|`vlan 100,102,105-107`|Creates multiple VLANs at once|Global Configuration|
|`name <vlan-name>`|Names the VLAN (e.g., `name student`)|VLAN Configuration|
|`interface <interface-id>`|Enters interface configuration for the given port|Global Configuration|
|`interface range <range>`|Configures a range of interfaces|Global Configuration|
|`switchport mode access`|Sets the port to access mode (non-trunk)|Interface Configuration|
|`switchport access vlan <vlan-id>`|Assigns the port to a specific VLAN|Interface Configuration|
|`no switchport access vlan`|Resets the port to default VLAN 1|Interface Configuration|
|`switchport voice vlan <vlan-id>`|Assigns a voice VLAN to the interface|Interface Configuration|
|`mls qos trust cos`|Enables QoS and trusts CoS value for voice|Interface Configuration|
|`show vlan`|Displays all VLANs configured|Privileged EXEC|
|`show vlan brief`|Summarized list of VLANs and assigned ports|Privileged EXEC|
|`show vlan id <vlan-id>`|Displays details about a specific VLAN|Privileged EXEC|
|`show vlan name <vlan-name>`|Displays VLAN details by name|Privileged EXEC|
|`show vlan summary`|Displays VLAN count summary|Privileged EXEC|
|`show interfaces <interface-id> switchport`|Displays VLAN and mode info of the interface|Privileged EXEC|
|`show interfaces vlan <vlan-id>`|Displays interface info for SVI VLAN (if configured)|Privileged EXEC|
|`no vlan <vlan-id>`|Deletes a specific VLAN|Global Configuration|
|`delete flash:vlan.dat` or `delete vlan.dat`|Deletes all VLANs (vlan.dat file)|Privileged EXEC|
|`erase startup-config`|Deletes startup configuration|Privileged EXEC|
|`reload`|Reloads the switch after deletion|Privileged EXEC|

