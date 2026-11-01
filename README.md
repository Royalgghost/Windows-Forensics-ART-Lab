# 🔍 Windows Forensics: Incident Response & Artifact Analysis

## 📌 Overview

This repository documents a Digital Forensics and Incident Response (DFIR) investigation conducted on a Windows 10 virtual machine. The goal was to simulate adversary behaviors using Atomic Red Team and capture volatile and non-volatile evidence while adhering to the Order of Volatility (RFC 3227).

- **Investigator:** Nouamane Azzat
- **Date:** October 17, 2026
- **Target Environment:** Windows 10 VM (`ilyas` user profile)

---

## 🛠️ Toolchain Used

- **Simulation:** Atomic Red Team (Invoke-AtomicRedTeam)
- **Acquisition:** FTK Imager 3.1.2.0 (RAM & Pagefile)
- **Triage & Parsing:** KAPE (Kroll Artifact Parser and Extractor), EvtxECmd, PECmd
- **Analysis:** Registry Explorer, Timeline Explorer

---

## 🎯 MITRE ATT&CK Mapping & Key Findings

| Technique | Name | Artifact Analyzed | Status | Result |
|---|---|---|---|---|
| **T1059.001** | PowerShell Execution | Prefetch (`POWERSHELL.EXE-CA1AE517.pf`) | **OBSERVED** | Execution confirmed via PECmd. |
| **T1547.001** | Registry Run Keys | `NTUSER.DAT\...\CurrentVersion\Run` | **NOT DETECTED** | Analyzed post-transaction log replay; no persistence value found. |

---

## 📜 Evidence Integrity (Chain of Custody)

- **Memory Dump:** `victime_ram.mem` (10 GB)
- **SHA-256 Hash:** `F3A1A563E5D0A167BDECC47D653FFDF00EBEE7D4D9A51BCFE6021BA36F62769E`

---

## 📑 Full Report

The complete detailed report in French is available here: [`docs/rapport_forensic.pdf`](docs/rapport_forensic.pdf)

---

## 📸 Evidence Snapshot

<div align="center">
  <img src="screenshots/Capture%20d%27%C3%A9cran%202026-11-01%20032300.png" width="700" alt="Forensic artifact screenshot 1" />
</div>

<div align="center">
  <img src="screenshots/Capture%20d%27%C3%A9cran%202026-11-01%20032320.png" width="700" alt="Forensic artifact screenshot 2" />
</div>

<div align="center">
  <img src="screenshots/Capture%20d%27%C3%A9cran%202026-11-01%20032331.png" width="700" alt="Forensic artifact screenshot 3" />
</div>

<div align="center">
  <em>A selection of screenshots captured during the investigation workflow and evidence collection process.</em>
</div>
