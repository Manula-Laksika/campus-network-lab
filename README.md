# Campus Network Lab (Cisco Packet Tracer)

A multi-site enterprise campus network built in Cisco Packet Tracer. I rebuilt a two-office CCNA reference lab from scratch, and I am extending it into a three-site campus with a branch office and a firewalled server room with a DMZ, without changing any of the original configuration.

## Attribution

The base lab (two offices with VLANs, VTP, EtherChannel, HSRP, OSPF, NAT, ACLs, wireless, port security, DHCP snooping and DAI) follows the Mega Lab task list from **Jeremy's IT Lab**. I rebuilt it from that task list. This repository does not redistribute his files.

**What is my own work:** the extension of Offices A and B, the Office C branch, the firewalled server room and DMZ, the test plan, and all documentation in this repository.

## Status

- [x] Base lab rebuilt and working
- [ ] Phase 1: Offices A and B extended (four new access switches)
- [ ] Phase 2: Office C branch (router-on-a-stick, local DHCP, guest ACL, OSPF)
- [ ] Phase 3: Firewall, server room and DMZ
- [ ] Phase 4: Full test run and failure drills
- [ ] Phase 5: Final documentation and write-ups

## What the base lab covers

- VLANs, VTP v2, Rapid PVST+, Layer 2 and Layer 3 EtherChannel
- HSRPv2 gateways, OSPF, floating static default routes, IPv6 basics
- DHCP with relay, DNS, NTP, SNMP, Syslog, FTP IOS upgrade, SSH with ACL access control
- Static NAT and pool-based PAT, extended ACLs
- Port security, DHCP snooping, Dynamic ARP Inspection, BPDU Guard, LLDP
- Wireless LAN controller with two lightweight access points

## Planned additions

- Four new access switches across Offices A and B
- Office C branch with a router-on-a-stick, local DHCP, dual-homed OSPF and a restricted guest VLAN
- ISA 3000 firewall with a server room and DMZ
- A 42-case test plan with five failure drills

## Repository layout

    docs/             addressing, VLANs, inventory, change log, test plan, design notes
    docs/incidents/   write-ups of problems found and fixed
    configs/original/ running configs of the base lab
    configs/extended/ running configs after the expansion
    packet-tracer/    versioned .pkt files

## How to open the lab

Open the `.pkt` files in `packet-tracer/` with Cisco Packet Tracer 8.2 or newer. Log in on any device with user `cisco` and password `ccna`, then use enable password `jeremysitlab`. These are the lab's training credentials, not real secrets.

## Known limits

- Packet Tracer wireless clients cannot lease addresses from the controller's Wi-Fi pool, and the client scan did not list the controller-based SSID, so laptops join by entering the SSID and WPA2-PSK key manually.
- Packet Tracer supports only a subset of real IOS and firewall commands.
