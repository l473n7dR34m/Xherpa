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
  <img src="screenshots/1.png" alt="Hero – Dashboard Overview" width="850">
</p>

## Overview

**Xherpa** is a macOS application providing local system diagnostics, compliance checks, and fast access to IT resources — all without requiring network connectivity or admin privileges.  
It’s built for managed environments where transparency and usability are key, offering immediate visibility into system health and support readiness.

---

## Key Features

### Self-Service Diagnostics
- Real-time system metrics and health overview  
- No admin rights or elevated access required  
- Read-only system interaction — safe in all environments  

### IT Access Hub
- Quick navigation to IT portals, helpdesk, or remote support  
- Configurable JSON-based layout for full customisation  
- Persistent helpdesk shortcut available on every screen  

### Security & Compliance
- Displays FileVault, SIP, MDM, and Gatekeeper status  
- Shows enrolled device state without policy modification  
- Helps end users verify their system is compliant before escalation  

### Dynamic Interface
- Modular six-page layout with arrow-based navigation  
- Built-in motion physics for interactive window behaviour  
- Fully themable — appearance can be customised, saved, and randomised  

---

## Dashboard Overview

Xherpa’s dashboard is divided into six pages, each dedicated to a different aspect of system visibility and IT access.

---

### 1. Quick Links
<p align="center">
  <img src="screenshots/1.png" alt="Quick Links Page" width="450">
</p>

Central hub for IT resources and web tools. Each button is customisable via a JSON configuration file.

**Default entries include:**
- Homepage  
- Remote Support  
- Company Portal  
- Latest Bulletin  
- IT Policies  
- Service Catalogue  
- Go to IT Helpdesk (persistent shortcut)

Links can point to internal portals, SharePoint pages, or support URLs.

---

### 2. System Info
<p align="center">
  <img src="screenshots/2.png" alt="System Info Page" width="450">
</p>

Displays live system information to assist with diagnostics and ticket triage.

**Shows:**
- Hostname and current user  
- macOS version and build number  
- Time zone and current time  
- System uptime  
- RAM and storage usage (live readouts)

All data is gathered locally using built-in macOS commands like `system_profiler` and `vm_stat`.

---

### 3. Security Status
<p align="center">
  <img src="screenshots/3.png" alt="Security Status Page" width="450">
</p>

Provides instant visibility into core macOS protection features and management status.

**Includes:**
- SIP (System Integrity Protection)  
- FileVault (encryption status)  
- MDM enrollment  
- VPN connectivity  
- Gatekeeper and SSH states  
- Admin users and update policies  

Designed for clarity during compliance checks or troubleshooting sessions.

---

### 4. Network
<p align="center">
  <img src="screenshots/4.png" alt="Network Page" width="450">
</p>

Summarises local and external connectivity status.

**Displays:**
- Active network interface (Wi-Fi or Ethernet)  
- IP configuration, gateway, and DNS  
- Upload/download throughput  
- Latency (Ping) and connection status  

All tests run locally using macOS utilities such as `networksetup`, `scutil`, and `ping`.  
No external services or data uploads are involved.

---

### 5. Utilities
<p align="center">
  <img src="screenshots/5.png" alt="Utilities Page" width="450">
</p>

A suite of local diagnostic tools to support first-line troubleshooting.  
Each runs safely in user space and requires no elevated permissions.

#### • Terminal
Launches the macOS Terminal app for command-line diagnostics.  

#### • Screenshot
Opens the native Screenshot utility (`Command + Shift + 5` equivalent).  

#### • Disk Health
Displays current disk usage and SMART status using `diskutil` and `df`.  

#### • Memory Info
Shows total, used, and free memory with data from `vm_stat`.  

#### • Port Scanner
Runs a lightweight TCP port scan on a chosen target host using Swift concurrency and native networking calls.  

#### • System Info
Opens the **System Information.app** for detailed hardware and software reports.

---

### 6. Appearance
<p align="center">
  <img src="screenshots/6.png" alt="Appearance Page" width="450">
</p>

Defines the visual and layout style of Xherpa.  
Themes can be customised, randomised, or saved for reuse.

**Options:**
- **Choose Skin** – select from curated default themes  
- **Customise** – adjust colours, gradient, and layout style  
- **Randomise** – shuffle between palette and theme variations instantly  
- **Save Skin** – store current configuration for persistence  

Changes apply immediately across all modules and remain between sessions.

---

## Hidden Physics Behaviour

While primarily functional, Xherpa’s interface includes subtle motion and interaction effects for a tactile desktop experience:

- **Throw & Bounce:** the main window can be “thrown” across the screen and bounces off edges with realistic deceleration.  
- **Dynamic Resizing:** panels subtly scale during movement, creating a sense of physical weight.  
- **Momentum Decay:** motion slows naturally based on velocity and screen boundary resistance.  
- **Elastic Edges:** collisions trigger soft compression and rebound for a satisfying visual response.  

These features are purely aesthetic — they don’t affect performance but make Xherpa feel organic and responsive.

---

## Internal macOS Tools & Diagnostics

| Category | Tools / Frameworks | Purpose |
|-----------|--------------------|----------|
| **System Health** | `system_profiler`, `ioreg`, `psutil` bridge | Hardware, process, and performance data |
| **Network** | `networksetup`, `ping`, `traceroute`, `scutil`, `ifconfig` | Network, DNS, and gateway diagnostics |
| **Security & Compliance** | `fdesetup`, `profiles`, `mdmclient`, `csrutil` | Reads FileVault, MDM, and protection status |
| **Disk & Memory** | `diskutil`, `df`, `vm_stat` | Storage and memory statistics |
| **Reporting** | Launches macOS System Information | Opens native detailed report interface |

All commands execute in **read-only** mode, ensuring safety in managed environments.

---

## Technology Stack

| Layer | Technologies Used | Description |
|-------|-------------------|-------------|
| **UI Layer** | SwiftUI + AppKit bridge | Native macOS interface with modular layout |
| **Diagnostics Engine** | Swift Concurrency + Process wrappers | Executes local system utilities safely |
| **Data Handling** | Codable JSON structures | Local parsing and export |
| **Animation & Physics** | Core Animation, velocity damping, inertia | Provides interactive motion behaviour |
| **Packaging** | Xcode Universal Binary | Unsigned, non-notarised `.app` bundle for manual deployment |

> **Note:** This build is unsigned and not notarised. Intended for demonstration or internal deployment.

---

## Development Notes

- **Platform:** macOS 12.0+  
- **Binary Size:** ~4.5 MB  
- **Memory Footprint:** ~10 MB  
- **Architecture:** Universal (Intel + Apple Silicon)  
- **Permissions:** None required beyond user space  
- **Network:** Fully offline, local execution  
- **Distribution:** Manual or via MDM tools (Jamf, Intune)

---

## Contact

For technical documentation or collaboration:  
**cypherhunk@protonmail.com**

---

*xherpa is distributed for demonstration and educational purposes only.  
The software is not notarised or signed for public macOS distribution.*
