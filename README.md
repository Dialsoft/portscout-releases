# Port Scout

**Find the smart appliances on your network, and see what each one exposes.**

Your fridge, washer, oven, thermostat, robot vacuum and smart plugs are all small computers on your network. Port Scout finds them and shows you exactly what each one has open: every port, its web pages, its encryption, and the commands (API calls) it accepts. It's built for beginners: every button explains itself when you hover over it.

- 🌐 Website, video and screenshots: **https://dialsoft.com/port-scout/**
- 📖 User manual: **https://dialsoft.com/port-scout/manual/**
- ⬇ Download: **[PortScout.exe](https://dialsoft.com/download/portscout)** (always the newest version)
- 📝 What's new: [RELEASE_NOTES.md](RELEASE_NOTES.md)

## How to use it

1. Download `PortScout.exe` and put it on your Desktop or in Documents (not Program Files, so it can update itself).
2. Double-click it. Nothing to install. If Windows says *"Windows protected your PC"*, click **More info → Run anyway**.
3. If Windows Firewall asks, allow Port Scout on **Private networks**.
4. Click **Find Appliances**. Likely appliances appear at the top, marked **LIKELY** or **maybe**.
5. **Double-click** an appliance to scan it, then read the tabs on the right: Open Ports, UPnP / API Calls, Time/SNMP/mDNS and Full Report.
6. **Copy Report** or **Save Report** to share the results.

## What it checks

| | |
|---|---|
| **Finds appliances** | Every device on your network, with the maker of its network chip (the official IEEE list is built in), its name and what it announces. Appliances are listed first. |
| **Open ports** | All 65,535 TCP ports, each explained in plain English. Remote-login and remote-control ports are shown in red. |
| **Web pages** | About 35 common pages on every web server: settings, status and API pages. |
| **Encryption** | Whether each service uses TLS, and its certificate. |
| **UPnP API calls** | Every UPnP service the appliance publishes, and each command it accepts with its inputs and outputs. |
| **Extra checks** | Time (NTP), SNMP and mDNS, which a normal port scan can't see. |

## Requirements

- Windows 10 or 11 (uses the .NET Framework 4.8 built into Windows)
- A PC on the same network as your appliances

## Safe to use

Port Scout only **looks**: it connects and reads, and never logs in, sends commands or changes anything on your appliances. Scan only your own devices, or networks you're responsible for.

## Updates

Port Scout checks this repository's [`latest.json`](latest.json) when it starts and every 6 hours. The title bar shows whether you're up to date. When a new version is out, it shows what's new and asks before installing, and it verifies the download's SHA-256 fingerprint first.

## Files here

| File | What it is |
|---|---|
| `PortScout.exe` | The program (newest version) |
| `latest.json` | Version information Port Scout and dialsoft.com read to find updates |
| `RELEASE_NOTES.md` | What changed in each version |

---

© 2026 Dialsoft LLC, Wharton, New Jersey. Written with Claude by Anthropic. Port Scout is free to use. Brand names belong to their owners; Port Scout is not affiliated with any appliance maker. The source code is not public.
