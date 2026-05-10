# Lab 32 — Packet Capture and Filtering with tcpdump and tshark

When ping and traceroute don’t find the answer, packet capture does. In this lab you will capture only DNS queries from one host, save them to a `.pcap`, then read them with tshark.

Run on https://killercoda.com/playgrounds/scenario/ubuntu

**Required software (free, installed via apt):**
- `tcpdump`
- `tshark` (text Wireshark)

> **Tip:** For graphical analysis on your laptop, install **Wireshark** (free) from https://www.wireshark.org and open the .pcap there.

---

## Step 1 — Install both tools

```bash
apt update && apt install -y tcpdump tshark
```

When tshark asks whether non-root users may capture, answer **No** for the lab.

---

## Step 2 — Capture 10 DNS packets from this host

```bash
tcpdump -i eth0 -nn -w /tmp/dns.pcap 'udp port 53 and src host 127.0.0.1' -c 10 &
sleep 1
for d in example.com cloudflare.com github.com; do dig +short @1.1.1.1 $d; done
wait
```

`-w` writes binary pcap; the BPF filter limits it to UDP/53 from loopback.

---

## Step 3 — Read the file with tshark

```bash
tshark -r /tmp/dns.pcap -Y "dns" -T fields \
  -e frame.time_relative -e dns.qry.name -e dns.qry.type
```

This prints just the queried name and record type per row.

---

## Step 4 — Filter only response packets

```bash
tshark -r /tmp/dns.pcap -Y "dns.flags.response==1"
```

---

## Step 5 — Generate a friendly summary

```bash
tcpdump -nn -r /tmp/dns.pcap | head
```

---

## Step 6 — Open in Wireshark for deep analysis

Copy the pcap to your laptop:

```bash
ls -lh /tmp/dns.pcap
# scp it to your machine, then File → Open in Wireshark
```

In Wireshark, use the display filter `dns.qry.name == "example.com"`.

---

## What you learned
- The difference between a **capture filter** (BPF) and a **display filter** (Wireshark/tshark `-Y`).
- How to capture once and analyse many times by writing to a `.pcap`.
- Where to download Wireshark for a graphical front-end.
