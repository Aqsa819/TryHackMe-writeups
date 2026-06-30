
**Link:** https://tryhackme.com/room/nmap01
**Path:** Level 2 - Tooling
**Difficulty:** Easy
**Date:** 30 June 2026

## Concepts & Tools Covered
- Nmap
- ARP Scan (Layer 2 discovery on local network)
- ICMP Scan (ping sweep)
- TCP/UDP Ping Scan

## Approach

Learned how Nmap can discover which hosts are "alive" on a network before running deeper scans. Different discovery methods work depending on whether you're on the same local network (ARP) or scanning over a routed network (ICMP/TCP/UDP).

## Key Commands

```
# ARP scan (local network only)
nmap -sn -PR <target_range>

# ICMP echo scan
nmap -sn -PE <target_range>

# TCP SYN ping scan (specific port)
nmap -sn -PS<port> <target_range>

# UDP ping scan
nmap -sn -PU<port> <target_range>
```

## Findings / Screenshots

<img width="1372" height="821" alt="image" src="https://github.com/user-attachments/assets/c3025d2f-c74f-4578-ab1d-69f18ade9734" /># Nmap Live Host Discovery




## What I Learned

Different host discovery techniques are needed depending on network position — ARP is fastest and most reliable on local networks (Layer 2), while ICMP/TCP/UDP probes are necessary when scanning across routed networks where ARP doesn't work.
