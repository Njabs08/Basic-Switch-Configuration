# Basic-Switch-Configuration
Cisco Packet Tracer  lab: baasic switch configuration, hostnames, secure password, VTY/console lines, MOTD. VLAN1 management IP

---

## Project Overview
This project configures Switch0 in the Njabulo's Office with:

A console connection for initial CLI access
Hostname and secure enable password
Console and VTY (remote) line authentication
A custom Message of the Day (MOTD) banner
An IP address on the VLAN 1 management interface for remote (Telnet) access
A saved (persistent) configuration

## Network Details
Item	Value
Assigned subnbet 192.168.4./24
Subnet mask	255.255.255.0
Router gateway (reserved)	192.168.4.1
Switch VLAN 1 address	192.168.4.3
Device password	"cisco123" (lab convenience only not best practice)

## Topology
<img width="441" height="231" alt="image" src="https://github.com/user-attachments/assets/a04986ea-8790-4bc4-9c7f-18711e45ce76" />

PC2 — connected via copper straight through and a console cable (RS232 → switch console port) for initial CLI configuration

PC3 — connected via copper strraight through cable used later to test remote Telnet access

Switch0 — the device being configured (renamed NjabuloSwitch)

Router — connected Via copper straight through to the switch (not used)

Printer — connected via cooper straight through to the switch (not used)

## 
