#  Lab 11 – Investigating Browser History

This lab focuses on forensic investigation of **browser history artifacts** from Internet Explorer and Google Chrome. It guides you through recovering browsing behavior and analyzing user activity through cached files and search keywords.

---

##  Objectives

- Understand browser-generated digital evidence at the application layer.
- Extract and analyze Internet Explorer (IE) and Chrome history data.
- Use forensic tools to investigate browser cache, cookies, and history.
- Identify visited URLs and search keywords with timestamps.

---

##  Tools & Environment

| Tool / File | Purpose |
|-------------|---------|
| VirtualBox + Kali 2021.4 | Lab environment |
| `cfreds_2015_data_leakage_pc.dd` | Disk image |
| `losetup`, `mount` | Attach and mount disk image |
| `hivexsh` | Registry hive shell tool |
| `libesedb` | Extract IE WebCache |
| `awk`, `grep` | Text and pattern analysis |

---

##  Lab Tasks

### 🔹 Step 1: Setup

- Attach image as loop device:
  ```bash
  losetup --partscan --find --show --read-only cfreds_2015_data_leakage_pc.dd
  mkdir /mnt/loopdev
  mount -o ro,loop,offset=206848 cfreds_2015_data_leakage_pc.dd /mnt/loopdev
