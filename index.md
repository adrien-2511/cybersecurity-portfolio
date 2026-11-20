---
layout: default
title: Home
---

# Adrien Turck - Cybersecurity Portfolio

[About me](#about-me) · [Technical skills](#technical-skills) · [Certifications and training](#certifications-and-training) · [Projects](#projects) · [Learning journey](#learning-journey) · [Career objective](#career-objective) · [Contact](#contact)

## About me

I am a French student in cyber security. In France I study in a work-study program, so I spend part of the year in a company and part at school. My degree ends in 2027. This semester I am on an Erasmus exchange at Universiti Malaya in Kuala Lumpur, in the Faculty of Computer Science and Information Technology.

My background is more on the infrastructure side : networks, Linux and Windows servers, virtualization. I came to security because when you build a network, you quickly see how many ways there are to break it. I prefer to understand an attack in my own lab before I try to defend against it.

Outside the courses I run a small home lab with a hypervisor and a few virtual machines, where I test what I learn.

## Technical skills

| Skill | Level | Where I used it |
|---|---|---|
| TCP/IP, subnetting, IPv6 | Confident | [OSPF network](projects/ospf-dhcp-network/) |
| Cisco IOS : OSPF, DHCP, VLAN, SSH | Working knowledge | [OSPF network](projects/ospf-dhcp-network/) |
| Virtualization (UTM, Proxmox) | Confident | [Virtual lab](projects/virtual-lab-setup/) |
| Linux command line | Working knowledge | [Virtual lab](projects/virtual-lab-setup/) |
| Nmap (discovery, service scan, NSE) | Working knowledge | [Virtual lab](projects/virtual-lab-setup/) |
| Wireshark and tcpdump | Beginner | Course labs (WQE7001) |
| Packet Tracer and GNS3 | Working knowledge | [OSPF network](projects/ospf-dhcp-network/) |
| Git and GitHub | Beginner | This repository |
| Python and Bash scripting | Beginner | Not yet in a project |
| SIEM (Splunk, Wazuh) | Beginner, not practiced yet | Planned for 2027 |

## Certifications and training

I don't have a certification yet. Everything below is in progress, with a target date.

- Cisco Networking Academy, CyberOps Associate (course WQE7001) : in progress, target January 2027.
- Cisco Networking Academy, CCNA Introduction to Networks, Switching Routing and Wireless Essentials, Enterprise Networking Security and Automation (course WQE7007) : in progress, target January 2027.
- ISC2 Certified in Cybersecurity (CC) : planned, target February 2027.
- TryHackMe SOC Level 1 path : planned, December 2026 to February 2027.

When I get a badge I will add the Credly link here.

## Projects

1. [Isolated virtual lab and Nmap service scan](projects/virtual-lab-setup/) : an attacker VM and a vulnerable target in a host-only network. I tested the isolation, then scanned the target with Nmap and analysed the results.
2. [Multi-area OSPF network with DHCP and SSH](projects/ospf-dhcp-network/) : a four-router network with OSPFv2 and OSPFv3 in two areas, DHCPv4 and DHCPv6 servers on the routers and SSH-only remote access.

## Learning journey

When the semester started I was comfortable with networks but I had never used Kali or Nmap seriously. The first weeks of WQE7001 were about threat actors and the role of a SOC. It helped me to see where the technical work fits : an analyst runs tools, but the real job is to decide fast if an alert is real.

The first topic that changed my way of working was the virtual lab for the Pathway assignment. I built it on a MacBook with an Apple M5 chip. The Cisco VMs are made for x86 and VirtualBox, so I used UTM, which can emulate x86. I learned that a lab is only safe if you can prove it is isolated. Running a scan is easy, but showing that the target cannot reach the Internet takes more work.

The second topic was the routing exercise with my number XY = 25. I had to build four routers with OSPF in two areas, DHCP for IPv4 and IPv6, and SSH on the core router. I learned how OSPF areas reduce the work of each router, and that IPv6 needs extra steps compared to IPv4. For example, a router interface needs the managed flag so that the PCs ask the DHCPv6 server for an address.

Something went wrong in the lab. My Kali VM had two network cards : one in host-only mode for the lab and one in shared mode (NAT) for the updates. At first I only put the NAT card down inside Kali before the tests. When I checked again I saw the problem : one command in Kali is enough to put the card up again. Then the scans could leave the lab. To fix it, I removed the second card in the UTM settings, so Kali has only the host-only card. Then I tested the worst case. I forced a default route through the Mac on both VMs, and the pings to 8.8.8.8 and to my home router still failed. Now the isolation does not depend on a setting inside the VM.


The topic I still find hard is everything that needs x86 VMs on Apple Silicon. Security Onion and the CyberOps Workstation are slow in emulation, and GNS3 with real IOS images is not easy to install on a Mac. I am also still a beginner with SIEM tools, which are used in every SOC job posting I read.

My improvement goal : pass the nine CyberOps group exams on NetAcad before 4 January 2027, with at least 80 % in each one. I will measure it with the scores in the NetAcad gradebook. I will plan two exams per week during the mid-semester break, from 30 November to 6 December.

## Career objective

My target role for the start of my career is SOC analyst, level 1. I like this role because it mixes networks, systems and investigation, and many postings accept junior profiles. In the longer term I want to become a security architect for infrastructure, because I like to design networks that are secure from the start.

My next steps :

1. Finish the TryHackMe SOC Level 1 path and pass the ISC2 CC exam before the end of February 2027.
2. Install Wazuh in my own lab and write five detection rules, between March and May 2027. I will publish them in this portfolio.
3. Find a work-study position in a SOC in France from September 2027, then prepare CompTIA Security+ for January 2028.

This plan follows the learning plan I wrote for the Pathway assignment of this course.

## Contact

- GitHub : [adrien-2511](https://github.com/adrien-2511)
- LinkedIn : [linkedin.com/in/adrien-turck](https://www.linkedin.com/in/adrien-turck/)

I don't publish my phone number or my address. You can contact me with a message on LinkedIn.
