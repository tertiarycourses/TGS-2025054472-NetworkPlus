# Lab 2 — IPv4 Subnetting and CIDR

In this lab you will take a single `/24` network and break it into four equal `/26` subnets. You will use the `ipcalc` utility to verify the math, then assign one of the resulting addresses to a virtual interface on Linux. Subnetting is one of the highest-weighted Network+ skills because every router, firewall, and cloud VPC requires correct CIDR planning.

Run all commands on https://killercoda.com/playgrounds/scenario/ubuntu

---

## Step 1 — Install ipcalc

`ipcalc` is a small calculator that shows network, broadcast, host range, and netmask for any CIDR you give it.

```bash
apt update && apt install -y ipcalc
```

---

## Step 2 — Understand the parent network

Start with `192.168.10.0/24`. The `/24` means the first 24 bits identify the network and the last 8 bits identify hosts, giving 256 addresses total (254 usable).

```bash
ipcalc 192.168.10.0/24
```

Look at the **Network**, **HostMin**, **HostMax**, and **Broadcast** values.

---

## Step 3 — Split into four /26 subnets

Adding two bits to the network portion (24 → 26) creates 4 subnets, each with 64 addresses (62 usable).

```bash
ipcalc 192.168.10.0/26
ipcalc 192.168.10.64/26
ipcalc 192.168.10.128/26
ipcalc 192.168.10.192/26
```

Verify each subnet has:
- 64 total addresses
- A unique network and broadcast address
- 62 usable host addresses

---

## Step 4 — Assign an IP from subnet 2 to your interface

We will give your interface a secondary IP that sits inside `192.168.10.64/26`.

```bash
ip addr add 192.168.10.65/26 dev eth0 label eth0:1
```

The `label eth0:1` creates a virtual sub-interface so the new address does not replace the primary one.

---

## Step 5 — Verify

```bash
ip -4 addr show eth0
```

You should see `inet 192.168.10.65/26 ... eth0:1` in the output.

---

## Step 6 — Clean up

```bash
ip addr del 192.168.10.65/26 dev eth0
```

---

## What you learned
- How to verify subnet boundaries using `ipcalc`.
- How a `/24` divides into four `/26` networks with 62 usable hosts each.
- How to assign and remove a CIDR-formatted IP on Linux.
