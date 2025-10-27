# Ex.No.8 — StegExpose: Detect Hidden Data in Images

![StegExpose](https://img.shields.io/badge/Tool-StegExpose-green)
![Platform](https://img.shields.io/badge/Platform-Java-orange)
![Type](https://img.shields.io/badge/Analysis-Steganography-blue)

---

## 📑 Table of Contents
- [🎯 Aim](#-aim)
- [🛠️ Prerequisites & Installation](#️-prerequisites--installation)
- [📋 Procedure](#-procedure)
  - [Step 1: Download and Set Up StegExpose](#step-1-download-and-set-up-stegexpose)
  - [Step 2: Select Images for Analysis](#step-2-select-images-for-analysis)
  - [Step 3: Open Command Line or Terminal](#step-3-open-command-line-or-terminal)
  - [Step 4: Run StegExpose on a Single Image](#step-4-run-stegexpose-on-a-single-image)
  - [Step 5: Analyze the Output](#step-5-analyze-the-output)
  - [Step 6: Run Batch Analysis on a Folder](#step-6-run-batch-analysis-on-a-folder)
  - [Step 7: View Advanced Options](#step-7-view-advanced-options)
  - [Step 8: Review and Report Results](#step-8-review-and-report-results)
- [✅ Result](#-result)
- [📝 Notes](#-notes)

---

## 🎯 Aim
To use **StegExpose**, a Java-based tool, to detect hidden data (steganography) in image files by evaluating their statistical properties.

---

## 🛠️ Prerequisites & Installation

1. **☕ Java Runtime Environment (JRE):** StegExpose is a Java-based tool, so ensure you have JRE installed. You can verify your installation by opening a terminal and typing `java -version`.

2. **🔧 StegExpose Tool:** Download the `StegExpose.jar` file from the official GitHub repository.

3. **📁 Case Folder:** Create a dedicated folder for your investigation (e.g., `C:\Forensics_Lab\StegExpose`) and place the `.jar` file and any images for analysis inside it.

---

## 📋 Procedure

### Step 1: Download and Set Up StegExpose
- **📥 Download the tool**: Go to the StegExpose GitHub repository and download the latest `.jar` file.
- **☕ Install Java**: If not already installed, download and install the JRE from the official Java website.
- **🗂️ Prepare environment**: Place the `StegExpose.jar` file into your case folder (e.g., `C:\Forensics_Lab\StegExpose`).

<details>
<summary>📂 View Environment</summary>
<br>
<p align="center">
  <img width="600" alt="Folder containing StegExpose.jar and image files" src="https://github.com/omkarreddy652/digital-forensic-tools_overview/blob/main/images/placeholder.txt?raw=true" />
</p>
</details>

---

### Step 2: Select Images for Analysis
- 🖼️ Collect the images you suspect might have hidden data.
- 📂 Place them in your case folder or a sub-folder (e.g., `C:\Forensics_Lab\StegExpose\Images_to_Analyze`).
- 📷 StegExpose supports formats like `.png`, `.jpg`, `.bmp`, etc.

---

### Step 3: Open Command Line or Terminal
- 💻 Open the Command Prompt (`cmd.exe`) or Terminal.
- 🗂️ Navigate to the folder where you saved the `StegExpose.jar` file.

```bash
C:\Windows\System32> cd C:\Forensics_Lab\StegExpose
```

<details>
<summary>🖥️ View Command Prompt</summary>
<br>
<p align="center">
  <img width="700" alt="Command prompt navigated to StegExpose directory" src="https://github.com/omkarreddy652/digital-forensic-tools_overview/blob/main/images/placeholder.txt?raw=true" />
</p>
</details>

---

### Step 4: Run StegExpose on a Single Image
Use the following command to check a single image for hidden data.

🔍 Replace `test_image.png` with the actual path to your image.

```bash
C:\Forensics_Lab\StegExpose> java -jar StegExpose.jar test_image.png
```

---

### Step 5: Analyze the Output
After running the tool, it will analyze the image and provide a score.

📊 StegExpose calculates a "suspect" score between 0 and 1. The higher the score, the more likely that hidden data is present.

**🎯 Threshold Values:**
- ✅ **Less than 0.2**: Image is likely clean (no hidden data).
- ⚠️ **0.2 - 0.3**: Possibly some hidden data.
- 🚨 **Above 0.3**: Likely that steganography is present.

---

### Step 6: Run Batch Analysis on a Folder
If you have multiple images to check, you can analyze them in bulk by specifying a folder.

📁 Replace `Images_to_Analyze` with the path to your folder.

```bash
C:\Forensics_Lab\StegExpose> java -jar StegExpose.jar Images_to_Analyze
```

<details>
<summary>📊 View Batch Analysis Output</summary>
<br>
<p align="center">
  <img width="800" alt="StegExpose running analysis on a full folder" src="https://github.com/omkarreddy652/digital-forensic-tools_overview/blob/main/images/placeholder.txt?raw=true" />
</p>
</details>

---

### Step 7: View Advanced Options
StegExpose provides additional parameters, such as adjusting the sensitivity and output verbosity.

❓ Use `--help` to see the full list of options.

```bash
C:\Forensics_Lab\StegExpose> java -jar StegExpose.jar --help
```

---

### Step 8: Review and Report Results
- 📋 For each image analyzed, review the score and determine if further investigation is needed.
- 🔍 An image with a high suspect score should be flagged for deeper analysis with other steganography tools.

**📄 Example Output:**
```
Analyzing suspect_image.png...
Result: 0.4
Steganography likely present
```

This output indicates that hidden data is likely present in the image `suspect_image.png`.

---

## ✅ Result

By following these steps, we successfully used StegExpose to analyze one or more images for the presence of hidden data.

🎯 **Key Achievements:**
- ✅ We were able to run the Java-based tool from the command line.
- ✅ We analyzed both single images and batches of images by pointing to a folder.
- ✅ We interpreted the "suspect score" to determine the likelihood of steganography.
- ✅ Images with a high score (e.g., > 0.3) were flagged as likely containing hidden data and requiring further forensic analysis.

---

## 📝 Notes

⚠️ **Detection, Not Extraction**: StegExpose is a detector. It tells you if hidden data is likely present; it does not extract or read the hidden data itself.

📊 **Statistical Analysis**: The tool works by looking for statistical anomalies that are common when data is hidden inside an image, which alters its original properties.

🔍 **Further Analysis**: If StegExpose flags an image, the next step would be to use a tool like StegSolve or Steghide (with a known password) to try and extract the hidden data.

---

**🔗 Related Tools:**
- [Steghide](https://github.com/StefanoDeVuono/steghide) - For extracting hidden data
- [StegSolve](http://www.caesum.com/handbook/Stegsolve.jar) - Advanced steganography analysis
- [Binwalk](https://github.com/ReFirmLabs/binwalk) - Firmware analysis and extraction

---

*📅 Last Updated: October 2025*
*👨‍💻 Author: Digital Forensics Lab*
