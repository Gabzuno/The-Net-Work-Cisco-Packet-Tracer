<div align="center">
  <h1>The-Network-Cisco-Packet-Tracer</h1>
</div>
<div align="center">
  <p>This repository contains my personal exercise in a journey to learn Networking using Cisco Packet Tracers, computer networking simulation software for teaching and learning networking, IoT, and cybersecurity skills in a virtual lab.</p>
</div>

</br>

## 01. Installing Cisco Packet Tracer

### Visit their official website by clicking 👾<a href="https://www.netacad.com/cisco-packet-tracer">here</a>👾.<br>

<p style="text-align:justify;">Create your own Cisco account by registering through any email accounts or via google account. Then, click their module for <b>Getting Started with Cisco Packet Tracer</b> which will give you the installation link of the software witihn its modular. Once installed, login the account you created and you can now start learning.</p>

## 02. Connecting 2 PCs with a Cross FastEthernet Cable

<p align="center">
  <img src="assets/img/Connecting%202Pcs.png" alt="Output">
</p>

## GLOSSARY

<ol>
  <li>
    <b>EIGRP (Enhanced Interior Gateway Routing Protocol)</b> - is a Cisco proprietary protocol. Considered to be easier to configure and manage than OSPF. It uses a <b style="color:MediumSeaGreen;">hybrid routing protocol</b> that combines features of both <b style="color:MediumSeaGreen;">distance vector</b> and <b style="color:MediumSeaGreen;">link-state</b> routing protocols. To calculate the best path to a destination, it uses a composite metric that takes into account factors such as bandwidth, delay, reliability, and load. Supports different  network topologies, including hub-and-spoke, point-to-point, and mesh.
    </li>
  <li>
    <b>OSPF (Open Shortest Path First)</b> - is an open standard protocol. Suited for larger networks with complex topologies. It uses <b style="color:MediumSeaGreen;">pure link-state</b> protocol. To calculate the best path to a destination, OSPF uses a cost-based metric that is calculated based on the bandwith of the links.
  </li>
  <li>
    <b>FLSM (Fixed Length Subnet Masks)</b> - is an IP subnetting method where all created subnets are the same size, using the same subnet mask, which simplifies configuration but can waste IP addresses if network segments have different host needs, unlike its counterpart VLSM (Variable Length Subnet Mask).
  </li>
  <li>
    <b>VLSM (Variable Length Subnet Masks)</b> - the ability to use different subnet masks for different subnets within the same network. It optimizes within an organization by creating subnets of different sizes, matching actual host needs (e.g., 10 hosts vs. 50 hosts) with different subnet masks (like /27, /26) to reduce waste.
  </li>
  <li>
    <b>CIDR (Classless Inter-Domain Routing)</b> - a method for ISPs and routers to manage large blocks of IP addresses and reduce the size of global routing tables. It optimizes between organizations, allowing ISPs to allocate large address blocks and aggregate them into single routes (supernetting), simplifying internet routing tables. 
  </li>
  <li>
    <b>ARPANET (Advanced Research Projects Agency Network)</b> - is a computer network considered the foundation of the internet. The basis of Internet technologies are the technologies used in ARPANET. In 1969, ARPANET was connected to three university networks in the USA, creating a computer network. Later, this structure expanded and grew even more.
  </li>
  <li>
    <b>IANA (Internet Assigned Numbers Authority)</b> - a crucial global body that coordinates unique identifiers for the internet, managing IP addresses, DNS root zone, and protocol parameters to keep the digital world organized, working under ICANN (Internet Corporation for Assigned Names and Numbers) and providing vital functions like the Time Zone Database. 
  </li>
  <li>
    <b>ICANN (Internet Corporation for Assgined Names and Numbers)</b> - is a global, non-profit organization that coordinates the unique identifiers for the internet, like domain names (e.g., .com, .org) and IP addresses, ensuring the internet's stable, secure, and unified operation by managing the Domain Name System (DNS) and related technical parameters. Essentially, it acts as the internet's phonebook administrator, preventing conflicts and allowing smooth navigation for users worldwide. 
  </li>
  <li>
    <b>Network Topology</b> - is a visual map to understand the physical or logical structure of a computer network. The locations of the devices and cables in the network are among the factors that determine the network topology.
  </li>
</ol>
