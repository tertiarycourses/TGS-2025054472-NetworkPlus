# TGS-2025054472 — CompTIA Network+ N10-009 Hands-On Labs

> **Course:** WSQ — CompTIA Certified Network+ Training
> **Course Code:** TGS-2025054472
> **Register here:** https://www.tertiarycourses.com.sg/wsq-comptia-certified-network-training.html

These are the official hands-on lab exercises for the WSQ CompTIA Certified Network+ Training course delivered by **Tertiary Infotech Academy Pte Ltd**.

A complete set of **36 step-by-step labs** aligned to the CompTIA Network+ N10-009 exam objectives. Every lab runs on the free **Killercoda Ubuntu Playground** (https://killercoda.com/playgrounds/scenario/ubuntu) — no local install required.

---

## How to use

1. Open the Killercoda playground in your browser: https://killercoda.com/playgrounds/scenario/ubuntu
2. Pick a lab from the list below and follow the steps in order.
3. Reset the playground between labs that change firewall or routing rules.
4. See [labs/tools.md](labs/tools.md) for every free tool used (with install commands and download links).

---

## Lab catalogue

### Domain 1 — Networking Concepts
- [Lab 1 — OSI Model Packet Inspection](labs/lab-01-osi-packet-inspection.md)
- [Lab 2 — IPv4 Subnetting and CIDR](labs/lab-02-ipv4-subnetting.md)
- [Lab 3 — IPv6 Addressing and Link-Local](labs/lab-03-ipv6-slaac.md)
- [Lab 4 — Common Ports and Protocols](labs/lab-04-common-ports.md)
- [Lab 5 — DNS Record Types](labs/lab-05-dns-records.md)
- [Lab 6 — DHCP Lease Capture (DORA)](labs/lab-06-dhcp-capture.md)
- [Lab 7 — Cloud VPC with Network Namespaces](labs/lab-07-cloud-vpc-namespaces.md)

### Domain 2 — Network Implementation
- [Lab 8 — Static Routing Between Subnets](labs/lab-08-static-routing.md)
- [Lab 9 — 802.1Q VLAN Tagging](labs/lab-09-vlan-tagging.md)
- [Lab 10 — Link Aggregation (LACP Bond)](labs/lab-10-link-aggregation.md)
- [Lab 11 — Wireless Concepts and Survey](labs/lab-11-wireless-concepts.md)
- [Lab 12 — NAT and PAT with iptables](labs/lab-12-nat-pat.md)
- [Lab 13 — DHCP Server (isc-dhcp-server)](labs/lab-13-dhcp-server.md)
- [Lab 14 — Authoritative DNS with BIND9](labs/lab-14-bind9-dns.md)

### Domain 3 — Network Operations
- [Lab 15 — SNMP Monitoring](labs/lab-15-snmp-monitoring.md)
- [Lab 16 — NetFlow Analysis with nfdump](labs/lab-16-netflow.md)
- [Lab 17 — Centralised Logging (rsyslog)](labs/lab-17-syslog.md)
- [Lab 18 — Time Sync with Chrony](labs/lab-18-ntp.md)
- [Lab 19 — Configuration Backup with Git](labs/lab-19-config-backup.md)
- [Lab 20 — Performance Baseline with iperf3](labs/lab-20-iperf3.md)

### Domain 4 — Network Security
- [Lab 21 — Host Firewall with UFW](labs/lab-21-host-firewall.md)
- [Lab 22 — TLS Certificate with OpenSSL + Nginx](labs/lab-22-tls-certificate.md)
- [Lab 23 — SSH Hardening with Key Auth](labs/lab-23-ssh-hardening.md)
- [Lab 24 — Site-to-Site VPN with WireGuard](labs/lab-24-wireguard-vpn.md)
- [Lab 25 — Port Scanning and Hardening](labs/lab-25-port-scanning.md)
- [Lab 26 — Suricata IDS](labs/lab-26-suricata-ids.md)
- [Lab 27 — ACL with iptables](labs/lab-27-iptables-acl.md)

### Domain 5 — Network Troubleshooting
- [Lab 28 — Layer 1/2 Diagnostics](labs/lab-28-layer1-2-diagnostics.md)
- [Lab 29 — ping, traceroute, mtr](labs/lab-29-ping-traceroute-mtr.md)
- [Lab 30 — DNS Troubleshooting](labs/lab-30-dns-troubleshooting.md)
- [Lab 31 — ARP and Neighbour Table](labs/lab-31-arp-neighbor.md)
- [Lab 32 — Packet Capture (tcpdump/tshark)](labs/lab-32-packet-capture.md)
- [Lab 33 — MTU and Path-MTU Discovery](labs/lab-33-mtu-pmtud.md)
- [Lab 34 — Routing Issues](labs/lab-34-routing-issues.md)
- [Lab 35 — Network Emulation with tc](labs/lab-35-tc-network-emulation.md)
- [Lab 36 — Service Reachability Triage](labs/lab-36-service-triage.md)

---

## Reference

- [labs/README.md](labs/README.md) — Lab index grouped by domain with software requirements
- [labs/tools.md](labs/tools.md) — Complete list of free tools (Killercoda + external)
- `comptia-network-n10-009-exam-objectives-(4-0).pdf` — Official exam blueprint

---

## Free tools used

All tooling is **100% free**. The bulk runs inside the disposable Killercoda VM via `apt`. Two labs use software on your own machine:

- **Lab 11 (Wireless)** — needs a real radio. Use WiFi Analyzer / Acrylic Wi-Fi (Win), wavemon+iw (Linux), or built-in Wireless Diagnostics (macOS).
- **Lab 32 (Packet Capture)** — optional GUI analysis with **Wireshark** (https://www.wireshark.org).

Full tool list: [labs/tools.md](labs/tools.md).
