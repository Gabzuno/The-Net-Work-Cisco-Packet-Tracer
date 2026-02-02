// Assigning IP Helper-Address //

\# Router

en => conf t => int <port> ex.go0/0

ip helper-address <DHCP Server IP>



\# delete helper

no ip helper-address <IP>



\# Showing helper

en => show run | include ip helper-address




// Creating ACL (Access Control List) Router //



en => conf t => ip access-list extended <NAME>

permit ip host <host ip> host <target ip>



\# denying anymore access

deny ip <host network ip> <host subnet> <target network ip> <target host subnet>



ex. deny ip 192.168.1.0 0.0.0.255 192.168.2.0 0.0.0.255



permit ip any any



int vlan <num> => ip access-group <ACL NAME> in(inbound)



\# View



en => show running-config/run or show access-lists

