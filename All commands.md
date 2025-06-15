## Privileged Access Mode:

#### `enable` -> enter into priv access mode

- `show running-config` 
- `copy running-config startup-config` -> save data in *NVRAM*
- `show ip route`
- `show vlan brief` -> displays vlans info
- `show interfaces status`
- `show interfaces trunk`
- `show vtp status`
- `show spanning-tree`
- `show spanning-tree vlan 1`
- `spanning tree vlan 1 root primary`
- `show interfaces | include Ethernet`
- `show etherchannel summary`
- `shutdown` // `no shutdown`
- `show interfaces port-channel 1`
 
---

## Global Config Mode:

**To run user priv commands from global config append `do` before all commands.**
#### `configure terminal `-> enter into global config mode

- `hostname <name>` -> changes name of device 
- `enable secret <password>` -> sets password, secret password holds higher priority than "enable password"
- `service password-encryption` -> encrypts all current passwords in running config
- `banner motd #<banner message>#` -> gives a welcome message shown on terminal, the hash before and after message isnt necessarily a hash, it can be any delimiter that is not part of the message.
- `ip route [destination network] [subnet mask] [next hop IP address or exit interface]` -> static route config
- `ip routing` -> enables L3 routing on multiswitch
- `vtp domain cisco`
- `vtp mode client / transparent`
- `vtp version 2`

#### Line Config Mode:

- `line console 0password <password>; login` -> can password protect console 0 or 1 or 2 on switch from this command
- `line vty <0> <n>` -> n can be 4 or 15 (n=4 -> makes 5 users, similarly n=15 -> 16 users), enters line config mode to set virtual terminal access to switch users and passwords
