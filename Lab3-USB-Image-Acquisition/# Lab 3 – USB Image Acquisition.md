#  Lab 3 – USB Image Acquisition

This lab focuses on **acquiring forensic disk images from a USB drive** using tools like FTK Imager and `dd`. It is part of a series of digital forensics practice labs.

---

##  Objectives

- Use **FTK Imager** to acquire a forensic image of a USB flash drive.
- Use **`dd` utility** to acquire a raw image of USB storage.
- Understand and document the imaging process for integrity and admissibility.

---

## 🛠️ Tools Used

| Tool          | Description                         |
|---------------|-------------------------------------|
| VirtualBox    | Virtualization environment          |
| Kali Linux    | Digital forensics environment       |
| FTK Imager    | GUI-based forensic imaging tool     |
| `dd` Utility  | Command-line disk duplicator        |
| USB Drive     | Target for acquisition              |

###  Downloads

- 🔗 [VirtualBox](https://www.virtualbox.org/wiki/Downloads)  
- 🔗 [Kali 2021.4](https://old.kali.org/kali-images/kali-2021.4/)  
- 🔗 [FTK Imager v4.5](https://accessdata.com/product-download/ftk-imager-version-4-5)  
- 🔗 [`dd` for Windows](http://www.chrysocome.net/downloads/dd-0.5.zip)

---

##  Lab Steps Summary

### Step 1: Setup
- Install VirtualBox and Kali Linux.
- Install FTK Imager on host machine.
- Prepare USB with files for imaging.

### Step 2: Imaging with FTK Imager
- Select physical device from FTK.
- Acquire forensic image in `.E01` or `.img` format.
- Save metadata and screenshot of acquisition.

### Step 3: Imaging with `dd` Utility
- Identify USB volume using `dd --list`.
- Run `dd` command:
  ```bash
  dd if=\\.\Volume{ID} of=C:\usb.img
