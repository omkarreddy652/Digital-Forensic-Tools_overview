# Ex.No.2 — Wondershare Recoverit: Data Recovery Tool Overview

![Recoverit](https://img.shields.io/badge/Recoverit-Latest-green)
![Warning](https://img.shields.io/badge/⚠️-Important-red)

---

## Table of Contents
- [Aim](#aim)
- [Installation](#installation)
- [Procedure](#procedure)
  - [Step 1: Create a Log File](#step-1-create-a-log-file)
  - [Step 2: Select the Drive to Analyze](#step-2-select-the-drive-to-analyze)
  - [Step 3: Choose the Partition Table Type](#step-3-choose-the-partition-table-type)
  - [Step 4: Analyze Current Partition Structure](#step-4-analyze-current-partition-structure)
  - [Step 5: Perform a Quick Search](#step-5-perform-a-quick-search)
  - [Step 6: Perform a Deeper Search](#step-6-perform-a-deeper-search)
  - [Step 7: Modify Partition Status](#step-7-modify-partition-status)
  - [Step 8: Write the Partition Table](#step-8-write-the-partition-table)
  - [Step 9: Recover Files](#step-9-recover-files)
  - [Step 10: Exit and Restart](#step-10-exit-and-restart)
- [Notes](#notes)
- [References](#references)

---

## Aim
To use TestDisk step by step to recover a missing partition and repair a corrupted one.

---

## 🛠️ Installation
| OS | Installation |
|----|--------------|
| Windows | Download the executable from the official CGSecurity website |
| macOS (Homebrew) |  brew install testdisk |
| Linux (Debian/Ubuntu) | sudo apt-get install testdisk |

---

## Procedure

### Step 1: Create a Log File
- Launch TestDisk from your terminal or command prompt using sudo testdisk (or testdisk_win.exe on Windows).

- Select the [Create] option to generate a log file of the recovery session. This is helpful for future reference or troubleshooting.
<details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec1.png" alt="Recoverit Launch" width="600">
</details>

---

### Step 2:Select the Drive to Analyze
- TestDisk will display a list of all detected storage devices.

- Use the Up/Down arrow keys to highlight the drive that contains your lost data.

<details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec2.png" alt="Select Recovery Mode" width="600">
</details>

- Select [Proceed] to move to the next step.
---

### Step 3:hoose the Partition Table Type
- TestDisk will automatically suggest the most likely partition table type (e.g., Intel/PC, EFI GPT).

- The default value is usually correct. Confirm the selection by pressing Enter. ⏳

<details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec1.png" alt="Recoverit Launch" width="600">
</details>

---

### Step 4:  Analyze Current Partition Structure
- From the main menu, choose [Analyse] and press Enter.
- 
<details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec4.png" alt="Scan Progress Animation" width="600">
</details>

- This will display the current partition table and check for errors or missing partitions.

---

### Step 5: Perform a Quick Search
- After the analysis, you will be prompted to perform a [Quick Search]. 🔍

<details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec3.png" alt="Preview Files Animation" width="600">
</details>

- Select it and press Enter to scan the drive for lost partitions.

- Once a partition is found, you can press p to list its files. Deleted files and folders often appear in red.

- Press q to return to the search results.
---

### Step 6: Perform a Deeper Search
- If the Quick Search fails to find your lost partitions, select [Deeper Search].
- 
  <details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec3.png" alt="Preview Files Animation" width="600">
</details>

- This process can take a long time, as it scans the entire drive, block by block, to find remnants of partition structures.

- Again, use p to preview files and confirm if a found partition is the one you are looking for.
---

### Step 7:  Modify Partition Status
- After finding the correct partitions, use the Left/Right arrow keys to set their status.

- Use **Left/Right arrow keys** to change status:  
  - **P**: Primary  
  - ***:** Bootable  
  - **L**: Logical  
  - **D**: Deleted
<details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec3.png" alt="Preview Files Animation" width="600">
</details>
- Ensure that the partitions you want to recover are marked as Primary or Logical (and not deleted).
---
### Step 8:  Write the Partition Table
- Once you are confident the partition structure is correct, select [Write] from the menu.
<details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec3.png" alt="Preview Files Animation" width="600">
</details>
- Confirm the operation by pressing y (for yes). This will write the new partition table to your disk.
<details>
<summary>View Screenshot / Animation</summary>
<img src="../assets/rec3.png" alt="Preview Files Animation" width="600">
</details>
- WARNING: This is a permanent change. Double-check your selections before writing.
---
### Step 9:  Recover Files
- If you just need to recover a few files without fixing the partition table, you can do so from the file list (after pressing p).

- Navigate to the folder containing your desired files.

- Use the colon : key to select the files you want to recover.

- Press the uppercase C key to copy the selected file(s).

- Navigate to a safe destination on a different storage device and press uppercase C again to paste.  
---
### Step 10:  Exit and Restart
- Once your task is complete, select [Quit] to exit the program.

- If you wrote a new partition table to the drive, it is recommended to restart your computer to allow the operating system to recognize the changes.
---

## Notes
> ⚠ **Important:** Always recover files to a **different drive** to avoid overwriting data.  
> ✅ Preview files before recovery to ensure integrity.  
> ⏳ Deep Scan may take longer but recovers more files.  
> 💾 Keep a backup of important recovered files.

---

## References
- [Wondershare Recoverit Official Website](https://recoverit.wondershare.com/)  
- Recoverit User Guide / Documentation
