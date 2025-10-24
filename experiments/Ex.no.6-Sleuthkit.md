# Ex.No.6 — The Sleuth Kit (TSK): Command-Line Digital Forensics

![The Sleuth Kit](https://img.shields.io/badge/The_Sleuth_Kit-4.12.1-blue)
![Platform](https://img.shields.io/badge/Platform-Windows%2FLinux%2FmacOS-lightgrey)
![Warning](https://img.shields.io/badge/⚠️-Command_Line-red)

---

## Table of Contents
- [Aim](#aim)
- [Prerequisites & Installation](#prerequisites--installation)
- [Procedure](#procedure)
  - [Step 1: Acquire Disk Image](#step-1-acquire-disk-image)
  - [Step 2: Start Analysis (List Partitions)](#step-2-start-analysis-list-partitions)
  - [Step 3: Examine File System Details](#step-3-examine-file-system-details)
  - [Step 4: List Files and Directories](#step-4-list-files-and-directories)
  - [Step 5: Analyze File Metadata](#step-5-analyze-file-metadata)
  - [Step 6: Recover a Deleted File](#step-6-recover-a-deleted-file)
  - [Step 7: Create an Event Timeline](#step-7-create-an-event-timeline)
- [Result](#result)
- [Notes](#notes)

---

## Aim
To use **The Sleuth Kit (TSK)**, a collection of command-line tools, to analyze a disk image, examine its file system, and recover digital evidence.

---

## 🛠️ Prerequisites & Installation

1.  **Download Sleuth Kit:**
    * Visit the official Sleuth Kit website or the Google Drive link provided to download the latest version for Windows.
2.  **Install Sleuth Kit:**
    * Run the installer and follow the on-screen instructions. Add the installation's `bin` directory to your system's PATH environment variable to run TSK commands from any terminal.
3.  **Acquire Evidence Image:**
    * You must have a disk image to analyze (e.g., `.E01`, `.dd`, `.raw`). For this lab, we will use the `4Dell Latitude CPi.E01` files.

<details>
<summary>View Installation Folder Screenshot</summary>
<img width="800" alt="Sleuth Kit bin folder with executables" src="https://github.com/user-attachments/assets/placeholder-image-url" />
</details>

---

## Procedure

### Step 1: Acquire Disk Image
- Before analysis, ensure you have the evidence files (`.E01`, `.E02`, etc.) in a dedicated case folder.
- For this experiment, we will use the sample image: `4Dell Latitude CPi.E01`.

---

### Step 2: Start Analysis (List Partitions)
- Open **Command Prompt (CMD)** as Administrator.
- Navigate to your case folder.
- Use the `mmls` (list partitions) command to view the partition table of the disk image. This helps you find the offset of the partition you want to analyze.

```bash
# mmls [image_file_name]
mmls "4Dell Latitude CPi.E01"

---

@echo off
:: This script runs the full Sleuth Kit analysis for Experiment 6.
:: It must be run as Administrator.

echo Moving to Sleuth Kit directory...
cd C:\Users\sleuthkit-4.14.0-win32\bin

echo [STEP 1] Running mmls (List Partitions)...
mmls.exe "C:\Forensics_Lab\4Dell Latitude CPi.E01"

echo.
echo [STEP 2] Running fsstat (File System Stats)...
fsstat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\filesystem_info.txt

echo [STEP 3] Running fls (List All Files)...
fls.exe -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\file_list.txt

echo [STEP 4] Running istat (Get Metadata for Inode 9871)...
istat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\metadata_Mr_Evil.txt

echo [STEP 5] Running icat (Recover File for Inode 9871)...
icat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\RECOVERED_Mr_Evil.bmp

echo [STEP 6] Running fls (Create Timeline Body File)...
fls.exe -m / -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\body.txt

echo [STEP 7] Running mactime (Generate Final Timeline)...
mactime.pl -b C:\Forensics_Lab\body.txt > C:\Forensics_Lab\timeline.txt

echo.
echo =========================================================
echo ANALYSIS COMPLETE.
echo All output files are saved in your C:\Forensics_Lab folder.
echo =========================================================
pause
