# Port Scout release notes

Download the newest version at **https://dialsoft.com/port-scout/**. Port Scout updates itself; it asks before installing.

## 1.2.0 (November 8, 2026)

**Port Scout is now a home-appliance finder.**

- **Find Appliances** recognizes fridges, washers and dryers, ovens, thermostats, robot vacuums, smart plugs and more, and lists the most likely appliances first, marked **LIKELY** or **maybe**. Click a device to see why.
- New **Looks like** column: appliance maker, smart-home chip, Samsung, TV/media, phone/PC, printer or network gear.
- **Ribbon-style toolbar** with Find, Scan, Scan options, Report and Help groups.
- **Start Here** tab: a beginner's guide, with the words you'll see explained.
- **Detailed tooltips** on every button, box, list and tab.
- **Updates itself**: the title bar shows whether you're up to date; **Check for Updates** any time. Downloads are verified (SHA-256) before installing.
- **Tell a Friend** (email, Facebook, Messenger or copy the link), **What's New**, **About** and **User Manual** buttons.
- Silent ports now explain what "silent" means in plain English.

## 1.1.0

- The maker of every device's network chip, from the full IEEE MAC-address registry built into the program.
- **Also search** box for appliances on another network, such as a guest or IoT Wi-Fi.
- Double-click a device to scan it.

## 1.0.0

- First version: full TCP port scan (all 65,535 ports), greetings ("banners"), web-page probing, TLS certificates, UPnP services and their API calls, NTP/SNMP/mDNS checks, and a report you can copy or save.

---

### Technical details

- Written in **C#** for the **.NET Framework 4.8** (Windows Forms) and compiled into a single portable `PortScout.exe`. No installer, no admin rights.
- Port checks use **asynchronous TCP connections**, hundreds at a time; the number at once and the wait time can be changed live, mid-scan.
- Each open port is probed in order: does it greet you first (banner)? Is it a web server (HTTP)? Is it encrypted (TLS handshake, certificate read)?
- UPnP: SSDP `M-SEARCH` (multicast and unicast) finds description XML files; each service's SCPD file is parsed for actions, arguments, data types and allowed values. Actions are never called.
- UDP checks are hand-built packets: NTP v3 client request, SNMP v1 `GET sysDescr.0` (community `public`), and an mDNS `_services._dns-sd._udp.local` PTR query.
- Device discovery: Windows `SendARP` on the local network (finds devices that ignore ping), ping, SSDP, reverse DNS, and port knocks on other networks.
- Chip makers come from the public **IEEE MA-L registry** (35,000+ entries), gzip-compressed inside the EXE.
- Self-update: reads `latest.json` here, downloads the EXE, checks its SHA-256, renames the running EXE aside and starts the new one.
