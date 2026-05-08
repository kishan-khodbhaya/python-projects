# SecureVault — Python Desktop Encryption Application

> Military-grade file encryption with forensic resistance, stealth operation, and plausible deniability — built entirely in Python.

![Python](https://img.shields.io/badge/Python-Desktop%20App-green)
![AES](https://img.shields.io/badge/AES-Encryption-red)
![PyQt](https://img.shields.io/badge/PyQt-UI-blue)
![Award](https://img.shields.io/badge/Star%20Performer%20of%20the%20Year-2024-gold)
![Status](https://img.shields.io/badge/Status-Production-brightgreen)

---

## Overview

SecureVault is a stealth Windows desktop application for high-security file encryption. It was built for users who need to protect sensitive files while maintaining plausible deniability — the application disguises itself as a normal browser, encrypted files appear as innocent formats, and the entire system is designed to leave no visible trace of its real purpose.

This project earned the Star Performer of the Year award at VedikIn Solutions in 2024 — the first time the award was given in 11 years since the company was founded.

---

## Problem Solved

Standard encryption tools have a visible presence — they appear in app lists, encrypted files have obvious extensions, and anyone inspecting the system can tell that encryption software is being used. For users handling genuinely sensitive data, this visibility itself is a risk.

SecureVault was designed with forensic resistance and plausible deniability as primary requirements — not afterthoughts.

---

## System Architecture

```
Application Launch
        ↓
    Disguised EXE
    (appears as Firefox or selected browser)
        ↓
    No visible UI on open
    Error box appears if clicked normally
        ↓
    Secret key sequence
    (typed without clicking any input box)
        ↓
    Main Application Unlocked
    (requires passcode: user-configured)
        ↓
┌────────────────────────────────────────┐
│           Core Functions               │
│                                        │
│  Encrypt File/Folder                   │
│  → AES encryption                      │
│  → Rename with misleading extension    │
│  → Convert to chosen format            │
│    (image, MP3, MP4, PDF, etc.)        │
│  → Remove original file               │
│  → Store in configured location        │
│                                        │
│  Decrypt File                          │
│  → Restore to original or custom path  │
│                                        │
│  Shortcut App Mode                     │
│  → Double-click shortcut → encrypt     │
│  → Shortcut auto-deletes after use     │
│  → Shortcut reappears on decrypt       │
│                                        │
│  Secure Wipe                           │
│  → Overwrite disk free space           │
│  → Normal (3x) / Hard (6x) /           │
│    Military (12x) algorithms           │
│                                        │
│  Multi-Destination Backup              │
│  → Encrypted copies across             │
│    multiple drives simultaneously      │
└────────────────────────────────────────┘
```

---

## Features

### Core Encryption
- **AES encryption** with password protection
- Encrypted files **renamed with misleading extensions** — unrecognizable without the key
- Encrypted files **converted to innocent formats** — images, MP3, MP4, PDF — chosen by the user
- Original file removed after encryption — no duplicate left behind
- Decryption restores to original path or any custom path

### Stealth Operation
- Application **disguises as a browser** (Firefox or user-selected) — visible in taskbar as normal software
- Opening the file normally shows a realistic error box
- App only opens via **secret key sequence** — typed without clicking anywhere
- Clicking anywhere on screen opens the actual browser — not the app

### Shortcut App Mode
- Create a shortcut for a specific file and default encryption location
- **Double-click shortcut → file instantly encrypted → shortcut auto-deletes**
- Decrypt the file → shortcut reappears exactly as before
- Zero visible trace of encryption activity

### Secure Wipe
- Overwrites disk free space using configurable algorithms:
  - Normal: 3-pass overwrite
  - Hard: 6-pass overwrite
  - Military: 12-pass overwrite — prevents forensic recovery
- Clean-wipe mode for entire drive formatting with same algorithms

### Sub-Applications (6 bundled utilities)
1. **Forgot Password** — secure password recovery flow
2. **License Activation** — system-bound license using model, MAC address, and install path
3. **Master Password** — decrypt any file using master password override
4. **Metadata Changer** — modify file metadata to remove identifying information
5. **Password Manager** — change app access password
6. **Log Viewer** — encrypted access and error log viewer

### License System
- License bound to specific machine (model + MAC + install path)
- Prevents copying and running on unauthorized systems

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python (only) |
| Encryption | AES |
| UI Framework | PyQt + Tkinter (hybrid) |
| File Operations | Python stdlib + OS-level APIs |
| License Binding | MAC address + hardware fingerprint |

No external dependencies beyond Python libraries — entirely self-contained.

---

## Security Considerations

- AES encryption with user-defined password — key never stored
- Multi-pass overwrite uses DoD-standard algorithms for forensic resistance
- Application identity disguise prevents casual discovery
- Secret key entry without input focus prevents keylogger capture of unlock sequence
- License system prevents unauthorized distribution

---

## Results

- Deployed and used in production at VedikIn Solutions for sensitive file handling
- Star Performer of the Year 2024 award — first time given in company's 11-year history
- Zero external libraries required — fully portable Python application


<!-- ## Demo -->

<!-- Add application screenshot here (disguised mode) -->
<!-- Add encryption flow screenshot here -->
<!-- Add demo video link here -->

---

> **Note:** Source code is proprietary. Given the security-sensitive nature of this application, a live demonstration and code walkthrough is available during interview process.
