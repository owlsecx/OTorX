# 🦉 OTorX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OwlSec-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OTorX** — OTorX — OwlSec security tool

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OTorX is a Tor and onion-network reconnaissance and auditing suite that routes traffic through the Tor SOCKS proxy for anonymized assessment. It checks Tor connectivity, fetches and analyses .onion services, verifies circuit isolation and inspects exit-node behaviour. It is intended strictly for authorized research on services you own or are permitted to test.

---

## ✨ Features


- Tor connectivity and SOCKS-proxy verification before any task runs
- Onion-service fetching and metadata analysis
- Circuit-isolation checks and new-identity (NEWNYM) control
- Exit-node inspection and anonymity validation
- Timeout and retry handling tuned for high-latency Tor circuits
- Offline --self-test for safe verification without a live Tor daemon

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OTorX
./OTorX --self-test
./OTorX --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
