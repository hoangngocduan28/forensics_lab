#  Lab 6 – Update Sequence Number (USN) Journaling

This lab focuses on **extracting and analyzing the USN Journal** (`$UsnJrnl`) to investigate file system events such as renaming, deletion, and access.

---

##  Objectives

- Understand how the **USN Journal** logs changes to NTFS volumes.
- Extract and convert `UsnJrnl.bin` to human-readable format (`.csv`).
- Analyze events such as **RENAME_OLD** and correlate with timestamps and MFT references.

---

##  Tools & Resources

| Tool/Resource | Purpose |
|---------------|---------|
| VirtualBox + Kali Linux 2021.4 | Lab environment |
| `UsnJrnl2Csv` tool | Converts `.bin` to `.csv` |
| `usncarve`, `usnparser` | Python tools for parsing USN data |
| Image `.dd` from Lab 5 | Disk image for analysis |

###  Downloads
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)  
- [Kali 2021.4](https://old.kali.org/kali-images/kali-2021.4/)  
- [ExtractUsnJrnl (GitHub)](https://github.com/jschicht/ExtractUsnJrnl)  
- Dropbox data source: [link](https://www.dropbox.com/sh/3lyzpi7vyod0pfs/AADh2b3TnmMqWZHB1Uzv9_ma?dl=0)  
- SharePoint data (if required): [link](https://ubaltmy.sharepoint.com/:f:/g/personal/id31ga53_ubalt_edu/EoJThlUPE85Hm7592HB5sjIBGo4Ht9drLxt9XnwDdnf3PA?e=4Okj4m)

---

##  Lab Tasks

### 🔹 Scenario 1: Using UsnJrnl2Csv

1. Install `UsnJrnl2Csv` tool.
2. Convert `UsnJrnl.bin` → `.csv`.
3. Extract and filter events:
   - Show only `RENAME_OLD` actions on `.jpg` files.
   - Display only 3 columns: `FileName`, `Timestamp`, `Reason`.
4. Analyze events surrounding a **specific time** using the **same MFT reference number**.

### 🔹 Scenario 2: Using Python Tools

1. Install and verify:
   - `usncarve` tool
   - `usnparser` tool
2. Run:
   ```bash
   usncarve.py -f input_file -o output.csv
   usn.py -f input_file -o output.csv
