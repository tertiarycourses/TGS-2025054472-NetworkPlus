# Lab 17 — Centralised Logging with Rsyslog

Most network gear can forward log events over UDP/514 (or TCP/514) to a central collector. In this lab you will configure rsyslog to both **send** and **receive** on the same VM (loopback), proving the forwarding pipeline.

Run on https://killercoda.com/playgrounds/scenario/ubuntu

**Required software (free, pre-installed):**
- `rsyslog`

---

## Step 1 — Enable the TCP receiver

```bash
sed -i 's/#module(load="imtcp")/module(load="imtcp")/' /etc/rsyslog.conf
sed -i 's/#input(type="imtcp" port="514")/input(type="imtcp" port="514")/' /etc/rsyslog.conf
```

The `imtcp` input module makes rsyslog listen on TCP/514.

---

## Step 2 — Add a forwarding rule

```bash
echo '*.* @@127.0.0.1:514' > /etc/rsyslog.d/50-forward.conf
```

The double `@@` means TCP (a single `@` would mean UDP).

---

## Step 3 — Restart rsyslog

```bash
systemctl restart rsyslog
ss -tlnp | grep 514
```

You should see rsyslog listening on `:514`.

---

## Step 4 — Generate a test event

```bash
logger -p local0.info "Network+ Lab 17 test event"
```

---

## Step 5 — Verify the event landed

```bash
grep "Lab 17 test" /var/log/syslog
```

---

## Step 6 — Inspect severity and facility

Rsyslog uses `facility.severity` selectors. Examples:
- `auth.warning` — authentication warnings
- `*.emerg` — emergency-level messages from any facility
- `mail.*` — every mail-related message

---

## What you learned
- Syslog forwarding uses UDP/514 by default, TCP/514 for reliability, TCP/6514 for TLS.
- `imtcp`/`imudp` are rsyslog input modules that open the listening socket.
- `logger` is the easiest way to inject test events.
