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

## Configuration Steps

1. Console into the switch

Connect PC0x4 to Switch0 using a console cable,open the Terminal application on PC0x4 with default settings, and press Enter to reach User EXEC mode (Switch>)

2. Explore the current configuration
   1. enable
   2. show run
   3. show ip interface brief

<img width="601" height="634" alt="image" src="https://github.com/user-attachments/assets/3256919c-8dad-4c4e-8116-052e10f3811f" />

3. Enter global configuration mode
   1. configure terminal
   2. hostname NjabuloSwitch
   3. enable secret cisco123

<img width="450" height="144" alt="image" src="https://github.com/user-attachments/assets/7a34b70f-cbf2-440c-ab5a-ea235c53015f" />

4. Secure the console line
   1. line console 0
   2. password cisco
   3. login
   4. exit

6. Secure the VTY (remote access) lines
   1. line vty 0 4
   2. password cisco
   3. login
   4. exit
   5. line vty 5 15
   6. login
   7. exit

<img width="441" height="296" alt="image" src="https://github.com/user-attachments/assets/471ff691-bba3-4603-bd7a-c6855e6d25bf" />

6. Set a Message of the Day
banner motd #
< Hello Everyone welcome to Njabulo's World of Networking >
#
<img width="353" height="153" alt="image" src="https://github.com/user-attachments/assets/6b959c30-cf74-4a90-8374-1facd353d5c2" />

7. Configure the VLAN 1 management interface and save the configuration
   1. interface VLAN1
   2. ip address 192.168.4.3 255.255.255.0
   3. no shutdown
   4. end
   5. copy run start

   <img width="526" height="338" alt="image" src="https://github.com/user-attachments/assets/f4b8eacc-1e6a-4c21-aed6-4afec1254f39" />

8. Verify remote access
   1. Assign PC3 an IP address/subnet mask on the same 192.168.4.1/28 network.
   2. From PC3's command prompt, run:
   telnet 10.1.17.146
   3. Confirm the MOTD banner and password prompt appear.
   4. Log in, then run enable and authenticate to reach Privileged EXEC mode (NjabuloSwitch#).

   
<img width="372" height="242" alt="image" src="https://github.com/user-attachments/assets/ea815f58-8a22-40e7-a9c4-70af8d152b68" />




