# CompTIA Network+ N10-009 — Lab Index

All labs run on the free Killercoda Ubuntu Playground:
**https://killercoda.com/playgrounds/scenario/ubuntu**

No installs required on your own machine for the Killercoda labs — every package is pulled with `apt` inside the throw-away VM. The few labs that need software on your **own** PC/laptop are flagged with **🖥 Local download** below.

---

## Domain 1 — Networking Concepts

| # | Lab | Free software needed |
|---|-----|----------------------|
| 1 | [OSI Model Packet Inspection](lab-01-osi-packet-inspection.md) | `tcpdump`, `curl` (apt) |
| 2 | [IPv4 Subnetting and CIDR](lab-02-ipv4-subnetting.md) | 🌐 **Web tool** — TIS IP Calculator: https://alfredang.github.io/ipcalculator/ |
| 3 | [IPv6 Addressing and Link-Local](lab-03-ipv6-slaac.md) | 🌐 **Web tool** — TIS IP Calculator: https://alfredang.github.io/ipcalculator/ |
| 4 | [Common Ports and Protocols](lab-04-common-ports.md) | `nmap`, `net-tools` (apt) |
| 5 | [DNS Record Types](lab-05-dns-records.md) | `dnsutils` (apt) |
| 6 | [DHCP Lease Capture (DORA)](lab-06-dhcp-capture.md) | `isc-dhcp-client`, `tcpdump` (apt) |
| 7 | [Cloud VPC with Network Namespaces](lab-07-cloud-vpc-namespaces.md) | none extra |

## Domain 2 — Network Implementation

| # | Lab | Free software needed |
|---|-----|----------------------|
| 8 | [Static Routing Between Subnets](lab-08-static-routing.md) | none extra |
| 9 | [802.1Q VLAN Tagging](lab-09-vlan-tagging.md) | `tcpdump` (apt) |
| 10 | [Link Aggregation (LACP Bond)](lab-10-link-aggregation.md) | `ifenslave` (apt) |
| 11 | [Wireless Concepts and Survey](lab-11-wireless-concepts.md) | 🖥 **Local download** — `iw`+`wavemon` (Linux), **WiFi Analyzer** / **Acrylic Wi-Fi Home** (Windows), built-in **Wireless Diagnostics** (macOS) |
| 12 | [NAT and PAT with iptables](lab-12-nat-pat.md) | `conntrack` (apt) |
| 13 | [DHCP Server (isc-dhcp-server)](lab-13-dhcp-server.md) | `isc-dhcp-server` (apt) |
| 14 | [Authoritative DNS with BIND9](lab-14-bind9-dns.md) | `bind9`, `dnsutils` (apt) |

## Domain 3 — Network Operations

| # | Lab | Free software needed |
|---|-----|----------------------|
| 15 | [SNMP Monitoring](lab-15-snmp-monitoring.md) | `snmpd`, `snmp`, `snmp-mibs-downloader` (apt) |
| 16 | [NetFlow Analysis with nfdump](lab-16-netflow.md) | `nfdump`, `fprobe` (apt) |
| 17 | [Centralised Logging (rsyslog)](lab-17-syslog.md) | none extra |
| 18 | [Time Sync with Chrony](lab-18-ntp.md) | `chrony` (apt) |
| 19 | [Configuration Backup with Git](lab-19-config-backup.md) | `git` (apt) |
| 20 | [Performance Baseline with iperf3](lab-20-iperf3.md) | `iperf3` (apt) |

## Domain 4 — Network Security

| # | Lab | Free software needed |
|---|-----|----------------------|
| 21 | [Host Firewall with UFW](lab-21-host-firewall.md) | `ufw` (apt) |
| 22 | [TLS Certificate with OpenSSL + Nginx](lab-22-tls-certificate.md) | `openssl`, `nginx`, `curl` (apt) |
| 23 | [SSH Hardening with Key Auth](lab-23-ssh-hardening.md) | none extra |
| 24 | [Site-to-Site VPN with WireGuard](lab-24-wireguard-vpn.md) | `wireguard`, `wireguard-tools` (apt) |
| 25 | [Port Scanning and Hardening](lab-25-port-scanning.md) | `nmap` (apt) |
| 26 | [Suricata IDS](lab-26-suricata-ids.md) | `suricata`, `jq` (apt) |
| 27 | [ACL with iptables](lab-27-iptables-acl.md) | `iptables-persistent` (apt) |

## Domain 5 — Network Troubleshooting

| # | Lab | Free software needed |
|---|-----|----------------------|
| 28 | [Layer 1/2 Diagnostics](lab-28-layer1-2-diagnostics.md) | `ethtool` (apt) |
| 29 | [ping, traceroute, mtr](lab-29-ping-traceroute-mtr.md) | `traceroute`, `mtr-tiny` (apt) |
| 30 | [DNS Troubleshooting](lab-30-dns-troubleshooting.md) | `dnsutils` (apt) |
| 31 | [ARP and Neighbour Table](lab-31-arp-neighbor.md) | `iputils-arping`, `ndisc6` (apt) |
| 32 | [Packet Capture (tcpdump/tshark)](lab-32-packet-capture.md) | `tcpdump`, `tshark` (apt). 🖥 **Optional local download:** **Wireshark** from https://www.wireshark.org for graphical analysis on your laptop. |
| 33 | [MTU and Path-MTU Discovery](lab-33-mtu-pmtud.md) | none extra |
| 34 | [Routing Issues](lab-34-routing-issues.md) | none extra |
| 35 | [Network Emulation with tc](lab-35-tc-network-emulation.md) | `iperf3` (apt) |
| 36 | [Service Reachability Triage](lab-36-service-triage.md) | `curl`, `netcat-openbsd`, `openssl` (apt) |

---

## Labs that require downloading free software onto your **own** machine

Every other lab installs everything inside the disposable Killercoda VM, so nothing touches your host. These two are the exceptions:

1. **Lab 11 — Wireless Concepts** (you need a real Wi-Fi radio, so you must run it on your own laptop)
   - Linux: `sudo apt install iw wavemon`
   - Windows: **WiFi Analyzer** (Microsoft Store) or **Acrylic Wi-Fi Home**
   - macOS: built-in **Wireless Diagnostics** (Option-click Wi-Fi icon)
2. **Lab 32 — Packet Capture** (optional graphical analysis)
   - **Wireshark** — https://www.wireshark.org (Windows / macOS / Linux)

---

## Suggested order

Work through Domain 1 → 2 → 3 → 4 → 5 in numeric order. Each lab is self-contained; reset the Killercoda playground between labs that change routing or firewall rules to avoid carry-over.
