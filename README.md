<p align="center">
  <img src="assets/AppIcon.png" alt="xherpa Logo" width="128" height="128">
</p>

<h1 align="center">Xherpa – IT Dashboard for macOS</h1>

<p align="center">
  A lightweight, brandable IT dashboard for macOS.<br>
  Designed for system visibility, diagnostics, and quick IT access.
</p>

---

<p align="center">
  <img src="screenshots/hero-dashboard.png" alt="Hero – System Info" width="850">
</p>

## Overview

**Xherpa** is a macOS application providing real-time system diagnostics, compliance checks, and instant access to IT resources — all from a single local interface.  
It’s designed for environments where transparency and simplicity matter, without requiring network connectivity or admin privileges.

---

## Key Features

### Self-Service Diagnostics
- Real-time CPU, RAM, and disk usage  
- System uptime, macOS version, and hardware info  
- Local-only diagnostic output with no data transmission  

### IT Access Hub
- Configurable quick links to internal tools and portals  
- Launches scripts, support URLs, or documentation  
- Single configuration file for easy enterprise branding  

### Security & Compliance
- Displays FileVault, SIP, Gatekeeper, and MDM status  
- Read-only checks for encryption and device management  
- Designed for visibility, not enforcement or policy control  

### Network Diagnostics
- Displays local IP configuration, DNS servers, and latency  
- Built-in reachability and speed test tools  
- No network logging or external service dependency  

<p align="center">
  <img src="screenshots/network.png" alt="Network Diagnostics" width="450">
  <img src="screenshots/security-status.png" alt="Security Compliance" width="450">
</p>

---

## Built-in Utilities

Each utility runs safely in user space using system tools and APIs.

| Utility | Description | Screenshot |
|----------|--------------|-------------|
| **Port Scanner** | Scans open TCP ports on a target host for quick connectivity testing. | <img src="screenshots/port-scanner-results.png" width="300"> |
| **Memory Test** | Runs a short stress test and shows free/used memory at a glance. | <img src="screenshots/memory-test-results.png" width="300"> |
| **Disk Health** | Reads disk usage and SMART status using built-in `diskutil`. | <img src="screenshots/disk-health-results.png" width="300"> |
| **System Report** | Opens the macOS **System Information** app directly for full hardware and software reporting. | <img src="screenshots/system-info.png" width="300"> |

---

## Appearance & Themes

The **Appearance** module provides a custom theme engine allowing users to tailor Xherpa’s look to their workspace or corporate brand.

### Features:
- **Randomise Theme** – instantly switches between curated colour palettes and layout variants  
- **Save Preset** – store and reload preferred theme configurations  
- **Live Editor** – adjust accent hues, window transparency, and module layout  
- **Professional Defaults** – includes 11 accessible, high-contrast options  
- **Real-time Preview** – visual changes update immediately across panels  

<p align="center">
  <img src="screenshots/appearance.png" alt="Appearance Module" width="500">
</p>

<p align="center">
  <img src="screenshots/theme1.png" alt="Theme 1" width="400">
  <img src="screenshots/theme-2.png" alt="Theme 2" width="400">
</p>

<p align="center">
  <img src="screenshots/theme-3.png" alt="Theme 3" width="400">
  <img src="screenshots/theme-4-appearance.png" alt="Theme 4 Appearance" width="400">
</p>

---

## Hidden Physics Behaviour

Beyond its practical dashboard features, **Xherpa** includes subtle motion logic for an interactive desktop feel.

- **Throw & Bounce:** the main window can be “thrown” across the screen and will bounce softly off edges.  
- **Dynamic Resizing:** the window dynamically expands or contracts slightly while being moved, simulating depth and weight.  
- **Momentum Decay:** motion eases out naturally, using velocity-based damping curves.  
- **Elastic Boundaries:** subtle scaling when colliding with screen edges, creating a tactile physics effect.

These details don’t affect functionality but add a satisfying, tactile responsiveness uncommon in standard macOS utilities.

---

## Internal macOS Tools & Diagnostics

| Category | Tools / Frameworks | Purpose |
|-----------|--------------------|----------|
| **System Health** | `system_profiler`, `ioreg`, `psutil` bridge | Hardware, process, and performance data |
| **Network** | `networksetup`, `ping`, `traceroute`, `scutil`, `ifconfig` | Network, DNS, and gateway diagnostics |
| **Security & Compliance** | `fdesetup`, `profiles`, `mdmclient`, `csrutil` | FileVault, MDM, and system protection status |
| **Disk & Memory** | `diskutil`, `df`, `vm_stat` | Storage and memory statistics |
| **Reporting** | Launches macOS System Information app | Detailed hardware/software reporting |

All operations are **read-only**, local, and safe for use in managed enterprise environments.

---

## Technology Stack

| Layer | Technologies Used | Description |
|-------|-------------------|-------------|
| **UI Layer** | SwiftUI + AppKit bridge | Native interface with flexible layout and theme engine |
| **Diagnostics Engine** | Swift Concurrency + Process wrappers | Executes local system commands safely |
| **Data Handling** | Codable JSON structures | Efficient local parsing and exports |
| **Animation & Physics** | Core Animation, custom easing, velocity decay | Provides dynamic motion and tactile feedback |
| **Packaging** | Xcode Universal Binary | Unsigned, non-notarised `.app` for manual installation |

> **Note:** This build is unsigned and not notarised. Intended for demonstration or internal distribution.

---

## Development Notes

- **Platform:** macOS 12.0+  
- **Binary Size:** ~4.5 MB  
- **Memory Footprint:** ~10 MB  
- **Architecture:** Universal (Intel + Apple Silicon)  
- **Permissions:** None required beyond user space  
- **Network:** Fully local execution  
- **Distribution:** Manual, MDM, or internal deployment  

---

## Contact

For technical collaboration or documentation:  
**cypherhunk@protonmail.com**

---

*xherpa is distributed for demonstration and educational purposes only.  
The software is not notarised or signed for public macOS distribution.*
