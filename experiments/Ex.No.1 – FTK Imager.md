# Ex.No.1 — FTK Imager: Forensic Imaging Tool Overview
![FTK Imager](https://img.shields.io/badge/FTK_Imager-4.5-blue)

---
## Table of Contents
- [Volatile Memory (RAM)](#volatile-memory-ram)
- [Non-Volatile Memory (Disk Image)](#non-volatile-memory-disk-image)
- [Notes](#notes)
- [References](#references)

---
## Volatile Memory (RAM)

Steps to capture RAM using FTK Imager:

### Step 1: Run as Administrator
- Open **FTK Imager** with administrative privileges.  
- Right-click the icon → **Run as administrator**  
📁 **Tip:** Always run as admin to avoid permission issues.

<img src="https://github.com/user-attachments/assets/739f9871-3976-41c3-be50-b8a8da805b63" alt="FTK Imager Memory Capture" width="600">

---

### Step 2: Initiate Memory Capture
- Click **File → Capture Memory...**

 <img src ="https://github.com/omkarreddy652/Digital-Forensic-Lab-experiments/blob/main/images/ftk%201.png?raw=true">

---

### Step 3: Configure Destination
- **Destination Path:** Use an external drive.  
- **Destination Filename:** Default or descriptive name.  
- **Include pagefile.sys:** Optional but recommended.  
- **Create AD1 file:** Optional container.

<details>
<summary>View Screenshot</summary>
<img width="1424" height="747" alt="image" src="https://github.com/user-attachments/assets/1af97ba6-6bec-4a63-84ae-afc72fc069ff" />

</details>

---

### Step 4: Start Capture
- Click **Capture Memory** button to start.  
- ⏳ Progress depends on RAM size.

<img width="1421" height="727" alt="image" src="https://github.com/user-attachments/assets/fcb8ca77-99d4-441c-9502-7f84db4a365f" />


---
### 5. Wait for Completion
- A progress bar will indicate the capture status.  
- Capture time depends on the system’s RAM size.  
- Once finished, the memory dump file will be available in the destination folder.
---
<br>

## Non-Volatile Memory (Disk Image)

### Step 1: Start the Process
- Go to **File → Create Disk Image...**  

<img width="1422" height="729" alt="ftk 4" src="https://github.com/user-attachments/assets/63d4f83f-9204-4845-bef2-7f7067d39b31" />


---

### Step 2: Select Source Type
| Type | Description |
|------|-------------|
| Physical Drive | Entire disk including partitions, unallocated space, MBR |
| Logical Drive | Specific partition (e.g., C:) |
| Image File | Copy/convert existing image |
| Folder Contents | Only a specific folder |

---

### Step 3: Select Source Drive
- Connect via **write-blocker** → select drive → **Finish**

<img width="606" height="460" alt="ftk 5" src="https://github.com/user-attachments/assets/d98fab54-e878-4723-9163-5944cebe151d" />


---

### Step 4: Configure Destination
- Click **Add...** → choose **Image Type** and **Destination**  

| Image Type | Description |
|------------|-------------|
| E01 | EnCase format, compresses data, includes metadata |
| Raw (DD) | Bit-for-bit copy, no extra features |
| AFF | Open forensic format, supports compression |

- Fill in **Evidence Info**: Case details, examiner name, description.  
- **Image Fragment Size:** Set 0 for single file.

<details>
<summary>View Screenshot</summary>
<img src="../assets/ftk7.png" alt="Disk Destination" width="600">
</details>

---

### Step 5: Start Imaging
- Click **Finish**, check **Verify images after creation**, click **Start**  
- ⏳ Time depends on drive size.

<img width="607" height="513" alt="ftk 8" src="https://github.com/user-attachments/assets/31a5904d-a249-42d0-b028-12ea5cb2fe76" />

---

### Step 6: Completion and Hash Verification
- FTK Imager shows **MD5** and **SHA1** for source & image  
- ✅ Matching hashes confirm integrity.
<img width="591" height="482" alt="ftk 7" src="https://github.com/user-attachments/assets/19a10071-5c2f-4eb0-9b58-36d3e73aed5e" />

---

## Notes
> ⚠ Always use a **write-blocker**  
> ✅ Hash verification ensures chain-of-custody  
> 📁 Image fragmentation helps with large drives  

---

## References
- [FTK Imager Official Website](https://accessdata.com/product-download/ftk-imager-version-4-5)  
- FTK Imager Documentation
