<p align="center">
  <img src="assets/AppIcon.png" alt="xherpa Logo" width="128" height="128">
</p>

<h1 align="center">Xherpa – IT Dashboard for macOS</h1>

<p align="center">
  A lightweight, brandable IT dashboard for macOS.<br>
  Designed for system visibility, diagnostics, and quick IT access.
</p>

---

## Overview

**Xherpa** provides self-service visibility into macOS system health, compliance, and diagnostics — all within a single lightweight dashboard.  
It runs fully offline, requires no admin privileges, and gathers data using only native macOS frameworks and shell tools in read-only mode.

---

## Dashboard Overview

Xherpa’s interface spans six modular pages, navigable via the arrow buttons at the bottom of the window.

---

### 1. Quick Links
<p align="center">
  <img src="screenshots/1.png" alt="Quick Links Page" width="450">
</p>

A configurable hub for internal or external IT resources.  
Each button can be redefined via a JSON configuration file.

**Default entries include:**
- Homepage  
- Remote Support  
- Company Portal  
- Latest Bulletin  
- IT Policies  
- Service Catalogue  
- Persistent **Go to IT Helpdesk** shortcut

---

### 2. System Info
<p align="center">
  <img src="screenshots/2.png" alt="System Info Page" width="450">
</p>

Displays key system details for quick identification and troubleshooting.

**Displays:**
- Hostname and logged-in user  
- macOS version and build  
- Time zone and uptime  
- RAM and disk utilisation  

All data is gathered locally from system utilities like `system_profiler`, `vm_stat`, and `df`.

---

### 3. Security Status
<p align="center">
  <img src="screenshots/3.png" alt="Security Status Page" width="450">
</p>

Summarises the device’s security and management state for compliance awareness.

**Includes:**
- SIP (System Integrity Protection)  
- FileVault encryption  
- MDM enrollment status  
- VPN, SSH, and Gatekeeper states  
- Admin user count and managed updates  

All values are retrieved using read-only checks (`fdesetup`, `csrutil`, `profiles`).

---

### 4. Network
<p align="center">
  <img src="screenshots/4.png" alt="Network Page" width="450">
</p>

Displays live network information and verifies basic connectivity.

**Displays:**
- Interface type and connection status  
- Local IP configuration, gateway, and DNS  
- Upload/download throughput and latency  

Tests use built-in tools like `networksetup`, `ping`, and `scutil` to avoid external dependencies.

---

### 5. Utilities
<p align="center">
  <img src="screenshots/5.png" alt="Utilities Page" width="450">
</p>

The Utilities module offers a suite of safe, local diagnostic tools — no elevation or internet access required.

#### • Terminal
Launches macOS Terminal for advanced commands.

#### • Screenshot
Opens the native Screenshot utility (`⌘ + ⇧ + 5`) for quick capture.

#### • Disk Health
Performs a read-only scan of mounted volumes using `diskutil` and `df`.  
Provides storage overview, file system status, mount state, and recent error check.

<p align="center">
  <img src="screenshots/disk-health-results.png" alt="Disk Health Results" width="450">
</p>

#### • Memory Info
Analyses current memory state using `vm_stat` and `psutil` bridges.  
Displays free, wired, compressed, and active memory, along with an overall pressure indicator.

<p align="center">
  <img src="screenshots/memory-test-results.png" alt="Memory Test Results" width="450">
</p>

#### • Port Scanner
Runs a targeted scan on localhost, gateway, and common external endpoints to confirm connectivity.  
Validates DNS and HTTPS reachability using native sockets.

<p align="center">
  <img src="screenshots/port-scanner-results.png" alt="Port Scanner Results" width="450">
</p>

#### • System Info
Opens the native macOS **System Information.app** for full hardware and software reports.

---

### 6. Appearance
<p align="center">
  <img src="screenshots/6.png" alt="Appearance Page" width="450">
</p>

Customise Xherpa’s look and feel using the built-in skin system.

**Options:**
- **Choose Skin** – select from built-in professional themes  
- **Customise** – adjust colour palette, depth, and surface gradient  
- **Randomise** – instantly shuffle layout and colour combinations  
- **Save Skin** – store preferences for persistent use  

Changes apply instantly and persist between sessions.

<p align="center">
  <img src="screenshots/theme1.png" alt="Theme 1" width="400">
  <img src="screenshots/theme-2.png" alt="Theme 2" width="400">
</p>

<p align="center">
  <img src="screenshots/theme-3.png" alt="Theme 3" width="400">
  <img src="screenshots/theme-4-appearance.png" alt="Theme 4" width="400">
</p>

---

## Hidden Physics Behaviour

Beyond standard UI transitions, **Xherpa** includes subtle physics-based interactions for a tactile desktop feel.

- **Throw & Bounce:** the window can be flicked across the screen and rebounds off edges.  
- **Dynamic Resizing:** the window scales slightly when moved, creating depth and motion.  
- **Momentum Decay:** motion slows naturally based on velocity and friction.

These behaviours are purely aesthetic and do not impact performance, but add a natural sense of movement and weight.

---

## Internal macOS Tools & Diagnostics

| Category | Tools / Frameworks | Purpose |
|-----------|--------------------|----------|
| **System Health** | `system_profiler`, `ioreg`, `psutil` bridge | Hardware and performance data |
| **Network** | `networksetup`, `ping`, `traceroute`, `scutil`, `ifconfig` | Local and external connectivity diagnostics |
| **Security & Compliance** | `fdesetup`, `profiles`, `mdmclient`, `csrutil` | Reports FileVault, SIP, and MDM status |
| **Disk & Memory** | `diskutil`, `df`, `vm_stat` | Gathers storage and memory statistics |
| **Reporting** | macOS System Information | Launches native diagnostic app |

All commands execute locally in **read-only mode**.

---

## Technology Stack

| Layer | Technologies Used | Description |
|-------|-------------------|-------------|
| **UI Layer** | SwiftUI + AppKit bridge | Native macOS interface with modular panels |
| **Diagnostics Engine** | Swift Concurrency + Process wrappers | Executes system tools asynchronously |
| **Data Handling** | Codable JSON structures | Local data parsing and output |
| **Animation & Physics** | Core Animation, velocity damping, inertia simulation | Subtle motion-based UI effects |
| **Packaging** | Xcode Universal Binary | Unsigned, non-notarised `.app` bundle for manual deployment |

> **Note:** Xherpa is unsigned and not notarised. Intended for internal or educational use only.

---

## Development Notes

- **Platform:** macOS 12.0+  
- **Binary Size:** ~4.5 MB  
- **Memory Footprint:** ~10 MB  
- **Architecture:** Universal (Intel + Apple Silicon)  
- **Permissions:** No elevated privileges required  
- **Offline Operation:** Fully local  
- **Deployment:** Manual install or MDM (Jamf / Intune)

---

## Contact

**cypherhunk@protonmail.com**

---

*xherpa is distributed for demonstration and educational purposes only.  
The software is not notarised or signed for public macOS distribution.*
