## **ROUTER CONFIGURATION**

### 

### **EXEC/PRIVILEGED MODE**

* Router> en = enter privileged mode
* Router# sh run = show running-config
* Router# sh ip ro = show routing table
* Router# sh ip int br = interface status
* Router# sh ver = IOS \& Hardware info
* Router# wr = save config



### **GLOBAL CONFIG MODE**

* Router# conf t = enter global mode
* Router(config)# host R1 = set hostname
* R1(config)# ip ro <network> <subnetmask> <gateway> = static routing
* R1(config)# ip route = enable IP routing



### **INTERFACE CONFIG**

* R1(config)# int \[port] - selecting port interface
* R1(config-if)# ip add <IP> <Subnet mask> = assigning IP to physical int
* R1(config-if)# no ip address = remove IP from physical int
* R1(config-if)# no shut = enable interface



### **ROUTING PROTOCOLS**

* router rip = enables routing information protocol (rip)

	R1(config)# router rip

&nbsp;	R1(config-router)# version 1/2

&nbsp;	R1(config-router)# network/net <network address>

&nbsp;	

* router ospf \[process-id] = enables routers to dynamically learn network routes using a link-state protocol.

&nbsp;	R1(config-router)# router-id \[id]

&nbsp;	R1(config-router)# net \[network-address] \[wildcard-mask] area \[area-id]

&nbsp;		**Note**: The **wildcard mask** is the inverse of the subnet mask (e.g., /24 is 0.0.0.255).

&nbsp;	R1(config-router)# passive-interface \[interface-id]

&nbsp;		**Note:** Prevents neighbor adjacencies on networks with no routers.

&nbsp;	R1(config)# router ospf 1

&nbsp;	R1(config-router)# net 192.168.1.0 0.0.0.255 area 0

&nbsp;	R1(config-router)# passive-interface g0/0

##### **SUBINTERFACE CONFIG (VLAN)**

* Router(config)# int \[port].\[vlan id] ex. int f0/0.1
* Router(config-subif)# encapsulation dot1q \[vlan id] ex. encapsulation dot1q 1
* Router(config-subif)# ip address \[IP] \[Subnet Mask]
* Router(config-subif)# exit

## 

## **SWITCH CONFIGURATION**



### **EXEC/PRIVILEGED**

* Switch> en = enable privileged mode
* Switch# sh vlan br = VLAN Summary
* Switch# sh mac add = show MAC table
* Switch# sh int status = port status
* Switch# wr = save config



### **GLOBAL CONFIG MODE**

* Switch# conf t = enter global mode
* Switch(config)# host SW1 = set hostname
* Switch(config)# vlan \[1 - 1005] = Create VLAN
* Switch(config-vlan)# name \[name] = Name VLAN



### **INTERFACE CONFIG**

* Switch(config)# int \[port] = selecting interface/port
* Switch(config)# int range/r \[port range ex.f0/0-24] = select range of port
* Switch(config-if)# sw mo acc / switchport mode access = handle traffic for a single VLAN, sending untagged frames directly to end-user devices. 

&nbsp;	Switch(config-if or config-if-range)# sw acc vlan \[vlanID]

&nbsp;	Switch(config-if)# no shut = enable port interface

* Switch(config-if)# sw mo trunk / switchport mode trunk - carry traffic for multiple VLANs using 802.1Q tagging for inter-switch communication. Uplinks between switches, connections to routers.

&nbsp;	Switch(config-if or config-if-range)# sw trunk allowed vlan \[ID]

&nbsp;	Switch(config-if or config-if-range)# sw trunk allowed vlan 10,20,30,etc.

&nbsp;	# If using Layer 3 Switch, capable of routing:

&nbsp;	Switch(config-if or config-if-range)# sw trunk encapsulation \[dot1q (802.1Q), ISL, negotiate]

&nbsp;		**Note:** Layer 2 switch automatically assigned their encapsulation into dot1q (recommended).



### **LINE CONFIG (Router \& Switch)**

##### **# CONSOLE**

* Router(config)# line con 0 = configure an access line

&nbsp;	# SET LOCAL ACCOUNT

&nbsp;	Router(config)# username \[name] secret \[password] = This set a login auth when accessing both router or switch.

&nbsp;	# SET PASSWORD

&nbsp;	Router(config-line)# password \[pass]

&nbsp;	Router(config-line)# login = forces password check

&nbsp;		**Note:** Assigning Local username is recommended

&nbsp;	# SET LOCAL TO LINE

 	Router(config-line)# login local



&nbsp;	Router(config-line)# exec-timeout \[min] \[sec] = Logs out idle console sessions after set period of time.

&nbsp;	Router(config-line)# logging synchronous = controls how logs displayed. Display system messages after user done typing.

##### **# VTY (Virtual Teletype) / Remote**

* Router(config)# line vty 0 4

&nbsp;	# vty = remote access either ssh or telnet

&nbsp;	# 0 4 = 5 simultaneous sessions, session number start at 0. 0 15 = 16 users

* Router(config-line)# transport input \[protocol] = controls which protocols are allowed.

&nbsp;	# PROTOCOLS: ssh, telnet, all, none

##### **SETUP SSH**

* Router(config)# username \[name] secret \[pass]

&nbsp;	Router(config)# enable secret \[pass] // setting password before entering privileged mode

&nbsp;	Router(config)# ip domain-name \[domain ex. lab.local] (necessary)

&nbsp;	Router(config)# crypto key generate rsa

&nbsp;	Router(config)# ip ssh version 2

&nbsp;	Router(config)# line vty 0 4

&nbsp;	Router(config-line)# transport input ssh

&nbsp;	Router(config-line)# login local

&nbsp;	Router(config-line)# exec-timeout 10 0

&nbsp;	Router(config-line)# end

&nbsp;	Router# wr

##### **WAYS TO BACKUP CONFIG**

* Router# copy run start / copy running-config startup-config - saves run (RAM) to start (VRAM)
* 
**###### TFTP SERVER**

* Turned on the TFTP and assigned an IP same as router's network
* Router# copy run tftp // Backup
* Address or name of remote host \[]? \[ServerIP]
* Destination filename \[router-confg]? \[filename].cfg

&nbsp;	**Tips:** Name files with device + date. ex. R1\_2026-2-1.cfg

* Router# copy tftp run // Restore
* Address or name of remote host \[]? \[ServerIP]
* Source filename \[]? \[filename].cfg





