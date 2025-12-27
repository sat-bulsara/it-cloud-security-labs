# Lab 00 — Environment Setup & Baseline Images

## 1. Title + Goal

**Goal:** Build clean, reproducible baseline virtual machines for Windows and Linux on Apple Silicon (Parallels Desktop) to support all future IT, cloud, and cybersecurity labs.

---

## 2. Architecture / Context

* Host: Apple Silicon Mac
* Hypervisor: Parallels Desktop
* Guest OS 1: Windows 11 Pro (ARM)
* Guest OS 2: Ubuntu Desktop LTS (ARM)
* Both systems are snapshotted as clean baselines

---

## 3. Prerequisites

* Apple Silicon Mac
* Parallels Desktop installed
* Sufficient disk space (at least 40–60 GB free)
* GitHub repository initialized: `it-cloud-security-labs/`

---

## 4. Checklist Steps

* [ ] Create fresh Windows 11 Pro (ARM) VM
* [ ] Verify Windows version and edition (`winver`)
* [ ] Capture Windows clean baseline snapshot
* [ ] Rename Windows host to lab standard
* [ ] Capture post-rename Windows snapshot
* [ ] Create Ubuntu Desktop LTS (ARM) VM
* [ ] Complete Ubuntu first login
* [ ] Capture Ubuntu clean baseline snapshot

---

## 5. Commands & Outputs

### Windows

```text
winver
```

### Ubuntu

*No commands executed at baseline stage.*

---

## 6. Screenshots Required

> All screenshots are stored in `00-setup/screenshots/`

* [ ] `00_Windows11_FreshVM_Setup.png`
* [ ] `00_Windows11_Baseline_Snapshot.png`
* [ ] `00_Windows11_WinVer.png`
* [ ] `00_Windows11_System_Properties.png`
* [ ] `00_Windows11_PC_Rename.png`
* [ ] `00_Windows11_Renamed_Snapshot.png`
* [ ] `00_Ubuntu_VM_Setup.png`
* [ ] `00_Ubuntu_First_Login.png`
* [ ] `00_Ubuntu_Baseline_Snapshot.png`

---

## 7. Validation / Completion Criteria

* Windows 11 Pro (ARM) VM boots successfully
* Ubuntu Desktop (ARM) VM boots successfully
* Baseline snapshots exist for both systems
* Screenshots captured and committed to GitHub

---

## 8. What I Learned

* How to build ARM-compatible lab environments on Apple Silicon
* Importance of clean baseline snapshots before configuration changes
* Differences between host OS and guest VM responsibilities
* Why Ubuntu LTS and Windows Pro are preferred for lab environments

---

## 9. Troubleshooting

* **Windows installs as Home edition** → Recreate VM and select Pro
* **Ubuntu black screen on first boot** → Wait 60 seconds or reboot VM
* **Snapshot fails** → Ensure VM is running and retry
* **Low RAM performance** → Adjust Parallels VM memory allocation

---

## 10. Security Notes

* Baseline VMs contain no sensitive data
* No domain joins or cloud credentials added
* Snapshots allow rapid rollback after misconfiguration
* Principle of least change applied before hardening labs

---

📌 **Next Labs:** All future labs will start by reverting to one of these baseline snapshots.

