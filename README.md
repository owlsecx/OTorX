# 🦉 OTorX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OCore%20%2F%20Privacy-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/Requires-Tor-blueviolet?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-2.0-cyan?style=flat-square"/>
</p>

> **OTorX** opens any URL in Firefox through Tor using a hardened temporary profile — no system-wide proxy changes, DNS routed through Tor, WebRTC disabled, fingerprinting resistance enabled, profile auto-deleted on exit.

---

## 📌 Overview

OTorX creates an isolated Firefox profile with all privacy settings pre-configured, verifies the Tor circuit is active before launching, then opens Firefox with the target URL fully routed through the Tor network. When Firefox closes, the temporary profile is deleted automatically.

---

## 🖥️ Menu

| Option | Description |
|--------|-------------|
| **[1] Open URL via Tor** | Verify Tor circuit → create hardened profile → launch Firefox through Tor |
| **[2] Check Tor Status** | Test SOCKS5 port reachability, systemd service status, and circuit verification via `check.torproject.org` |
| **[3] Exit Node Info** | Fetch exit node IP, country, region, city, ISP/org, and hostname — compare against real IP |
| **[4] Settings** | Change Tor host, port, and browser binary |

The menu header displays a live **● ACTIVE / ● OFFLINE** Tor status indicator on every load.

---

## 🔒 Privacy Profile

OTorX writes a hardened `user.js` to a temporary profile directory. Every Firefox launch gets a fresh isolated profile with these settings enforced:

| Feature | Setting |
|---------|---------|
| **SOCKS5 proxy** | Routed through `127.0.0.1:9050` (configurable) |
| **DNS via Tor** | `socks_remote_dns = true` — no DNS leaks |
| **DNS prefetch** | Disabled — no background DNS lookups |
| **WebRTC** | Fully disabled — no local IP leaks via `media.peerconnection.*` |
| **Fingerprint resistance** | `privacy.resistFingerprinting = true` |
| **Tracking protection** | Enabled including social tracking |
| **First-party isolation** | `privacy.firstparty.isolate = true` |
| **Geolocation** | Disabled |
| **Disk & memory cache** | Disabled — no local traces |
| **Browsing history** | Disabled |
| **Telemetry & health report** | Fully disabled |
| **Safe browsing** | Disabled (prevents data to Google) |
| **Referrer policy** | Cross-origin referrer trimmed |
| **Battery API** | Disabled (fingerprinting vector) |
| **Ping tracking** | `browser.send_pings = false` |

The temporary profile directory is auto-deleted when Firefox closes.

---

## 🌐 Supported Browsers

OTorX auto-detects the first available browser in this order:

`firefox` · `firefox-esr` · `iceweasel` · `librewolf` · `waterfox`

The active browser can be changed in **[4] Settings**.

---

## ⚙️ Settings

| Setting | Default | Description |
|---------|---------|-------------|
| Tor Host | `127.0.0.1` | SOCKS5 proxy host |
| Tor Port | `9050` | SOCKS5 proxy port (Tor Browser uses `9150`) |
| Browser | `firefox` | Browser binary name |

---

## 🔧 Tor Setup

```bash
# Install Tor
sudo apt install tor

# Start Tor service
sudo systemctl start tor

# Enable on boot
sudo systemctl enable tor

# Check status
sudo systemctl status tor
```

---

## ⚙️ Requirements

- **Linux** (any modern distro)
- **Tor** installed and running
- **Firefox** (or compatible browser) installed
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OTorX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
