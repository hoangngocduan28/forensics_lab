#  Lab 7 – Recycle Bin and Anti-Forensics

This lab explores forensic investigation of **Recycle Bin artifacts** and detects **anti-forensic behavior** on a suspect system by analyzing web history, registry hives, and deleted files.

---

##  Objectives

- Recover deleted files from the Recycle Bin using forensic tools.
- Correlate `$I` and `$R` files to identify deletion metadata.
- Investigate **anti-forensics** activity on the system during the last recorded day.

---

##  Tools & Environment

| Tool/Resource | Purpose |
|---------------|---------|
| VirtualBox + Kali 2021.4 | Virtualized forensic lab |
| `cfreds_2015_data_leakage_pc.dd` | Disk image for analysis |
| `testdisk` | Recycle Bin recovery |
| `fls`, `grep` | File system and keyword analysis |
| `rip.pl` | Registry hive parsing |
| ShimCache parser | Executed programs history |
| IE export data | Web history review |

---

##  Data Sources

- Disk image: `cfreds_2015_data_leakage_pc.dd` from Lab 5
- Registry hives: `SOFTWARE`, `NTUSER_informant.DAT`
- IE history files: `webhistory/IE11.export/Container*`

---

##  Lab Tasks

### 🔸 1. Recycle Bin Forensics

- Examine `$Recycle.Bin` and `$I*` metadata (e.g., timestamp, original path).
- Use `testdisk` to recover deleted files.
- Match file IDs with user-readable filenames.
- Example:
