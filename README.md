# EZ-IP

A Windows desktop utility for managing network adapter settings without memorizing PowerShell syntax. Switch between saved profiles, toggle DHCP, assign static IPs, manage routes, and run bandwidth tests — all from one compact, always-elevated window.

---

## Features

- **Adapter management** — list all adapters with live status, enable/disable via right-click
- **IP configuration** — toggle DHCP / Static with a confirmation diff before applying
- **Extra IPs** — add or remove secondary IP addresses on any adapter
- **Route management** — view, add, and remove IPv4 routes
- **Profiles** — save any adapter config as a named profile and apply it in one click
- **Tray icon** — apply profiles and check adapter IPs without opening the app
- **Transfer** — Share profiles and routes with other machines running EZ-IP
- **Terminal** — run PowerShell network commands directly in-app
- **Network Test** — Test internet, open ports, and local LAN speed tests using iPerf3
- **Auto-update** — notified when a new version is available and installs with one click

---

## Download

Grab the latest installer from the [Releases](../../releases) page.

The app requests administrator elevation at launch (UAC prompt). This is required to read and write network configuration.
