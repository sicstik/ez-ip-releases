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
- **Import / Export** — share configs between machines as `.ezip` files
- **Terminal** — run PowerShell network commands directly in-app
- **Network Test** — run iPerf3 bandwidth tests between two machines running EZ-IP
- **Auto-update** — notified when a new version is available and installs with one click

---

## Download

Grab the latest installer from the [Releases](../../releases) page.

> EZ-IP requires **Windows 10 or 11** (x64). The installer includes a WebView2 bootstrapper — if WebView2 is not already installed it will be downloaded automatically.

The app requests administrator elevation at launch (UAC prompt). This is required to read and write network configuration.

---

## Building from Source

### Prerequisites

| Tool | Install |
|---|---|
| Rust + Cargo | https://rustup.rs |
| Node.js 18+ | https://nodejs.org |
| VS C++ Build Tools | https://visualstudio.microsoft.com/visual-cpp-build-tools/ — select **Desktop development with C++** |
| WebView2 Runtime | Pre-installed on Windows 11 / recent Windows 10. Download at https://developer.microsoft.com/en-us/microsoft-edge/webview2/ if missing |

### Run in development

```powershell
npm install
npm run tauri dev
```

> Dev mode runs without elevation. Network commands that require admin rights will fail unless you launch your terminal as Administrator first.

### Build the installer

```powershell
npm run tauri build
```

Outputs an NSIS installer at `src-tauri\target\release\bundle\nsis\EZ-IP_x.x.x_x64-setup.exe`.

---

## Tech Stack

- [Tauri v2](https://tauri.app/) — Rust backend, WebView2 shell, native Windows integration
- [React](https://react.dev/) + [TypeScript](https://www.typescriptlang.org/) — frontend UI
- [Tailwind CSS](https://tailwindcss.com/) — styling
- [Zustand](https://zustand-demo.pmnd.rs/) — state management
- PowerShell — all network operations via the persistent `powershell.exe` session

---

## Data Storage

Profiles and saved routes are stored locally at:

```
%LOCALAPPDATA%\EZ-IP\profiles.json
```

Use the **Import / Export** tab to back up or share configs between machines as `.ezip` files.

---

## Releasing a New Version

See [RELEASE.md](RELEASE.md) for the step-by-step guide covering key generation, version bumping, building a signed installer, and publishing to GitHub Releases.
