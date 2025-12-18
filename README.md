# DDoS SYN Flood Mitigation Project

**Course:** CSCI 401 Capstone  
**Environment:** Ubuntu 22.04, Kali Linux, VirtualBox  
**Focus:** Host level and kernel mitigations against TCP SYN flood attacks

## Overview
This project evaluates the effectiveness of system hardening techniques against
a TCP SYN flood denial-of-service attack by comparing a protected and an
unprotected Ubuntu server.

Two identical servers were subjected to a simulated SYN flood generated from
a Kali Linux attacker. Performance and availability were measured before and
during the attack.

## Lab Setup
- Attacker: Kali Linux
- Target 1: Ubuntu 22.04 (unprotected)
- Target 2: Ubuntu 22.04 (protected)
- Network: VirtualBox host only network

## Attack Simulation
- SYN flood generated using `hping3`
- Traffic captured and verified with `tcpdump`
- Service responsiveness measured with `curl` timing tests

## Defensive Controls Implemented
- TCP SYN cookies and backlog tuning
- Reverse path filtering (rp_filter)
- Netfilter connection tracking tuning
- UFW firewall restrictions
- Nginx request rate limiting
- Fail2Ban automated IP blocking

## Results
- Both servers performed similarly under normal conditions
- Under attack, the unprotected server experienced multi second timeouts
- The protected server maintained near baseline response times

## Files
- 'report/CSCI 401 Project Implementation.docx' - for the fuull project report
