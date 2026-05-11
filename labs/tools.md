# Free Tools Reference — CompTIA Network+ N10-009 Labs

Every tool listed here is **100% free** (open-source, freeware, or free tier with no time limit).

Two categories:

1. **Inside Killercoda** — installed in the disposable Ubuntu VM via `apt`. Nothing touches your own machine.
2. **External / Standalone** — downloaded onto your own PC/laptop, or used in a browser. Useful when you're offline, on a school PC, or want a GUI.

Killercoda playground (free, no signup): https://killercoda.com/playgrounds/scenario/ubuntu

---

## Section A — Tools installed inside the Killercoda Ubuntu VM (via `apt`)

### A1. Networking core (pre-installed in Ubuntu)
| Tool | Purpose | Used in Lab |
|------|---------|-------------|
| `iproute2` (`ip`, `ss`) | Interfaces, routes, sockets, namespaces | 1, 2, 3, 7, 8, 9, 12, 28, 31, 34 |
| `iptables` | Stateful firewall / NAT | 12, 21, 27 |
| `sysctl` | Kernel tunables (e.g. `ip_forward`) | 8, 12 |
| `systemd-resolved` (`resolvectl`) | Local stub resolver | 30 |

### A2. Capture & analysis
| Tool | Install | Purpose | Lab |
|------|---------|---------|-----|
| `tcpdump` | `apt install tcpdump` | CLI packet capture | 1, 6, 9, 32 |
| `tshark` | `apt install tshark` | CLI Wireshark | 32 |
| `nfdump` | `apt install nfdump` | NetFlow collector / analyser | 16 |
| `fprobe` | `apt install fprobe` | NetFlow exporter | 16 |

### A3. Diagnostics
| Tool | Install | Purpose | Lab |
|------|---------|---------|-----|
| `iputils-ping` | pre-installed | ping | 3, 7, 8, 12, 29, 33, 35 |
| `traceroute` | `apt install traceroute` | Hop-by-hop path | 29 |
| `mtr-tiny` | `apt install mtr-tiny` | Live path + loss | 29 |
| `iputils-arping` | `apt install iputils-arping` | ARP probe | 31 |
| `ndisc6` | `apt install ndisc6` | IPv6 NDP probe | 31 |
| `ethtool` | `apt install ethtool` | NIC link/duplex/counters | 28 |
| TIS IP Calculator (web) | https://alfredang.github.io/ipcalculator/ | IPv4 + IPv6 subnet calculator (used in labs) | 2, 3 |
| `nmap` | `apt install nmap` | Port scanner | 4, 25 |
| `iperf3` | `apt install iperf3` | Throughput / jitter | 20, 35 |
| `tc` + `sch_netem` | in `iproute2` | Latency / loss / bandwidth emulation | 35 |
| `conntrack` | `apt install conntrack` | View NAT translation table | 12 |
| `net-tools` | `apt install net-tools` | Legacy `netstat`, `ifconfig` | 4 |

### A4. DNS / DHCP / Time / Logging
| Tool | Install | Purpose | Lab |
|------|---------|---------|-----|
| `dnsutils` (`dig`, `nslookup`, `host`) | `apt install dnsutils` | DNS query | 5, 14, 30 |
| `bind9` | `apt install bind9` | Authoritative DNS server | 14 |
| `isc-dhcp-client` | `apt install isc-dhcp-client` | DHCP client | 6 |
| `isc-dhcp-server` | `apt install isc-dhcp-server` | DHCP server | 13 |
| `chrony` | `apt install chrony` | NTP sync | 18 |
| `rsyslog` | pre-installed | Syslog daemon | 17 |

### A5. Security
| Tool | Install | Purpose | Lab |
|------|---------|---------|-----|
| `ufw` | `apt install ufw` | Firewall front-end | 21 |
| `openssh-server` / `openssh-client` | pre-installed | SSH + key auth | 23 |
| `openssl` | `apt install openssl` | Certificates + TLS testing | 22, 36 |
| `nginx` | `apt install nginx` | TLS web server | 22 |
| `wireguard` + `wireguard-tools` | `apt install wireguard wireguard-tools` | Modern VPN | 24 |
| `suricata` + `suricata-update` | `apt install suricata` | Open-source IDS/IPS | 26 |
| `iptables-persistent` | `apt install iptables-persistent` | Save iptables rules | 27 |

### A6. Monitoring
| Tool | Install | Purpose | Lab |
|------|---------|---------|-----|
| `snmpd` | `apt install snmpd` | SNMP agent | 15 |
| `snmp` (`snmpwalk`, `snmpget`) | `apt install snmp` | SNMP client | 15 |
| `snmp-mibs-downloader` | `apt install snmp-mibs-downloader` | Friendly OID names | 15 |

### A7. Misc
| Tool | Install | Purpose | Lab |
|------|---------|---------|-----|
| `git` | `apt install git` | Config version control | 19 |
| `curl` | `apt install curl` | HTTP client / generator | 1, 22, 36 |
| `netcat-openbsd` (`nc`) | `apt install netcat-openbsd` | TCP port test | 27, 36 |
| `jq` | `apt install jq` | JSON parsing | 26 |
| Kernel module `8021q` | `modprobe 8021q` | VLAN tagging | 9 |
| Kernel module `bonding` | `modprobe bonding` | Link aggregation | 10 |
| `ifenslave` | `apt install ifenslave` | Bond helpers | 10 |

---

## Section B — External / Standalone Free Tools (download or browser)

### B1. Subnet & IP calculators (Lab 2, 3, 8, 12, 34)
| Tool | Type | Link |
|------|------|------|
| **TIS IP Calculator** ⭐ used in Labs 2 & 3 | Web | https://alfredang.github.io/ipcalculator/ |
| ipcalc | CLI | `apt install ipcalc` |
| sipcalc | CLI (IPv6 too) | `apt install sipcalc` |
| subnetcalc | CLI (IPv4+IPv6) | `apt install subnetcalc` |
| SolarWinds Advanced Subnet Calculator | Free Windows GUI | https://www.solarwinds.com/free-tools/advanced-subnet-calculator |
| subnet-calculator.com | Web | https://www.subnet-calculator.com |
| jodies.de IP calculator | Web | https://jodies.de/ipcalc |
| CIDR.xyz | Visual web | https://cidr.xyz |
| IPv6 subnet calculator | Web | https://www.site24x7.com/tools/ipv6-subnetcalculator.html |

### B2. Packet capture / analysis (Lab 1, 6, 9, 32)
| Tool | Type | Link |
|------|------|------|
| **TIS PCAP Analyzer** ⭐ used in Lab 32 | Web | https://alfredang.github.io/pcapanalyzer/ |
| Wireshark | GUI Win/Mac/Linux | https://www.wireshark.org |
| tshark | CLI bundled with Wireshark | — |
| Npcap | Windows capture driver | https://npcap.com |
| CloudShark (free tier) | Web pcap viewer | https://www.cloudshark.org |
| PacketTotal | Online pcap analyser | https://packettotal.com |
| A-Packets | Online pcap analyser | https://apackets.com |

### B3. Port scanning / discovery (Lab 4, 25)
| Tool | Type | Link |
|------|------|------|
| Nmap | CLI all OSes | https://nmap.org |
| Zenmap | Official Nmap GUI | https://nmap.org/zenmap |
| Angry IP Scanner | GUI all OSes | https://angryip.org |
| Advanced IP Scanner | Free Windows GUI | https://www.advanced-ip-scanner.com |
| YouGetSignal Open Port Check | Web | https://www.yougetsignal.com/tools/open-ports |

### B4. DNS lookup (Lab 5, 14, 30)
| Tool | Type | Link |
|------|------|------|
| dig / nslookup / host | CLI | bundled with OS |
| DNSChecker | Web (global propagation) | https://dnschecker.org |
| MXToolbox | Web (DNS, MX, blacklist) | https://mxtoolbox.com |
| Google Admin Toolbox – Dig | Web `dig` | https://toolbox.googleapps.com/apps/dig |
| intoDNS | Zone health check | https://intodns.com |

### B5. DHCP / TFTP (Lab 6, 13)
| Tool | Type | Link |
|------|------|------|
| DHCP Server for Windows | Free Win GUI | http://www.dhcpserver.de |
| Tftpd64 | DHCP + TFTP + syslog combo | https://pjo2.github.io/tftpd64 |

### B6. Ping / traceroute / path (Lab 29, 30, 34)
| Tool | Type | Link |
|------|------|------|
| mtr | CLI | `apt install mtr-tiny` |
| WinMTR | Free Windows GUI | https://github.com/White-Tiger/WinMTR |
| PingPlotter Free | GUI Win/Mac | https://www.pingplotter.com |
| Hurricane Electric Looking Glass | Web | https://lg.he.net |
| BGP.HE.NET | BGP / AS lookup | https://bgp.he.net |

### B7. Bandwidth / performance (Lab 20, 35)
| Tool | Type | Link |
|------|------|------|
| iperf3 | CLI all OSes | https://iperf.fr |
| JPerf | Java GUI for iperf | https://sourceforge.net/projects/jperf |
| Speedtest CLI | CLI | https://www.speedtest.net/apps/cli |
| fast.com | Web (Netflix) | https://fast.com |
| LibreSpeed | Self-hosted speed test | https://librespeed.org |

### B8. Wi-Fi survey (Lab 11)
| Tool | Type | Link |
|------|------|------|
| WiFi Analyzer (Matt Hafner) | Free Win/Android | Microsoft Store / Play Store |
| Acrylic Wi-Fi Home | Free Windows | https://www.acrylicwifi.com |
| inSSIDer Lite | Free GUI | https://www.metageek.com/inssider |
| Kismet | CLI Linux/Mac | https://www.kismetwireless.net |
| wavemon + iw | CLI Linux | `apt install iw wavemon` |
| Wireless Diagnostics | Built-in macOS | Option-click Wi-Fi icon |

### B9. VPN / tunnels (Lab 24)
| Tool | Type | Link |
|------|------|------|
| WireGuard | All OSes | https://www.wireguard.com |
| OpenVPN Community | All OSes | https://openvpn.net/community |
| Tailscale (free tier) | Mesh on top of WireGuard | https://tailscale.com |
| strongSwan | IPsec | https://www.strongswan.org |

### B10. SSH / terminal (Lab 23)
| Tool | Type | Link |
|------|------|------|
| PuTTY | Free Windows | https://www.putty.org |
| MobaXterm Home | Free Windows | https://mobaxterm.mobatek.net |
| Windows Terminal | Microsoft Store | free |
| Termius (free tier) | Cross-platform | https://termius.com |

### B11. TLS / certificate (Lab 22, 36)
| Tool | Type | Link |
|------|------|------|
| OpenSSL | CLI all OSes | https://www.openssl.org |
| SSL Labs Server Test | Web | https://www.ssllabs.com/ssltest |
| testssl.sh | CLI script | https://testssl.sh |
| Let's Encrypt + certbot | Free CA + client | https://letsencrypt.org |
| **TIS Cryptography Toolkit** ⭐ | Web | https://alfredang.github.io/cryptography-toolkit/ |
| **TIS Hash Generator** ⭐ | Web | https://alfredang.github.io/hashgenerator/ |

### B12. Monitoring / SNMP / NTP (Lab 15, 16, 17, 18)
| Tool | Type | Link |
|------|------|------|
| PRTG Free (100 sensors) | Windows | https://www.paessler.com/prtg |
| LibreNMS | Self-hosted | https://www.librenms.org |
| Zabbix | Self-hosted | https://www.zabbix.com |
| Cacti | Self-hosted | https://www.cacti.net |
| Grafana OSS + Prometheus | Self-hosted | https://grafana.com |
| iReasoning MIB Browser (Personal) | Free Win/Mac | https://www.ireasoning.com/mibbrowser.shtml |
| NTP Pool | NTP servers | https://www.ntppool.org |

### B13. Security / IDS / Firewall (Lab 21, 25, 26, 27)
| Tool | Type | Link |
|------|------|------|
| Suricata | Open-source IDS/IPS | https://suricata.io |
| Snort 3 | Open-source IDS | https://www.snort.org |
| Security Onion | Free SOC distro | https://securityonionsolutions.com |
| OpenVAS / Greenbone CE | Vulnerability scanner | https://www.greenbone.net |
| fail2ban | SSH brute-force blocker | https://www.fail2ban.org |
| pfSense CE | Free firewall distro | https://www.pfsense.org |
| OPNsense | Free firewall distro | https://opnsense.org |

### B14. Network simulation / topology (revision drills)
| Tool | Type | Link |
|------|------|------|
| Cisco Packet Tracer | Free with NetAcad signup | https://www.netacad.com/cisco-packet-tracer |
| GNS3 | Free emulator (real IOS/Linux images) | https://www.gns3.com |
| EVE-NG Community | Free emulator | https://www.eve-ng.net |
| Containerlab | Container-based topologies | https://containerlab.dev |
| draw.io / diagrams.net | Free network diagrams | https://app.diagrams.net |

### B15. Browser sandboxes (Killercoda alternatives)
| Service | What you get | Link |
|---------|-------------|------|
| Killercoda Ubuntu Playground | Root Ubuntu shell | https://killercoda.com/playgrounds/scenario/ubuntu |
| Play with Docker | Linux VM in browser | https://labs.play-with-docker.com |
| Replit (free tier) | Linux shell + code | https://replit.com |
| JSLinux | x86 emulator in browser | https://bellard.org/jslinux |

---

## Lab → Primary Tool Quick Map

| Lab | Headline tool(s) |
|-----|------------------|
| 1 | tcpdump, curl |
| 2 | ipcalc / sipcalc |
| 3 | ip (iproute2) |
| 4 | nmap, ss |
| 5 | dig (dnsutils) |
| 6 | dhclient, tcpdump |
| 7 | ip netns, bridge |
| 8 | ip route, sysctl |
| 9 | ip link (8021q), tcpdump |
| 10 | bonding driver, ifenslave |
| 11 | WiFi Analyzer / Acrylic / iw / wavemon |
| 12 | iptables NAT, conntrack |
| 13 | isc-dhcp-server |
| 14 | bind9, dig |
| 15 | snmpd, snmpwalk |
| 16 | nfdump, fprobe |
| 17 | rsyslog |
| 18 | chrony |
| 19 | git |
| 20 | iperf3 |
| 21 | ufw |
| 22 | openssl, nginx |
| 23 | ssh-keygen, sshd |
| 24 | wireguard |
| 25 | nmap, ss |
| 26 | suricata, jq |
| 27 | iptables, iptables-persistent |
| 28 | ethtool, ip |
| 29 | ping, traceroute, mtr |
| 30 | dig, resolvectl |
| 31 | arping, ndisc6, ip neigh |
| 32 | tcpdump, tshark, TIS PCAP Analyzer |
| 33 | ping (-M do), ip link |
| 34 | ip route get |
| 35 | tc (netem, tbf), iperf3 |
| 36 | curl, nc, openssl s_client |

---

All tools above are free of charge. The Killercoda VM is also free and disposable, so you can run every lab without spending or installing anything on your own machine — except the optional GUI tools in Section B.
