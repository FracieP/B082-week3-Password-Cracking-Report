# NetworkWalks B082 — Week 3 · Password Cracking

**W3-PM | CYBERSECURITY & ETHICAL HACKING | NETWORKWALKS**

This repository documents the password-cracking activities completed during Week 3 of my Cybersecurity & Ethical Hacking Internship with NetworkWalks, Batch B082.

The week consisted of two related activities:
* **PM1:** Password Cracking with JTR using John the Ripper and Johnny
* **PM2:** Password Cracking with NetworkWalks Tools using the NetworkWalks Hash Calculator and Password Cracker

All activities were performed using the practice PDF files provided for the internship and within the authorized training environment.

---

## 1. Liability Disclaimer

All activities documented in this repository were performed for educational and authorized cybersecurity training purposes.
The password-cracking techniques were used only against the practice files provided by NetworkWalks. No unauthorized systems, accounts, or third-party files were targeted.
The information in this repository should only be used in environments where proper authorization has been obtained.

---

## 2. Introduction

The purpose of this week's activities was to perform a controlled password-cracking exercise against a password-protected PDF.

I have previous knowledge and experience with password-cracking concepts and John the Ripper. This project allowed me to apply that existing knowledge through a hands-on exercise using both JTR and NetworkWalks' browser-based tools.

The activities involved extracting the password hash from a protected PDF, preparing the hash for the cracking tool, running the password-cracking process, and verifying the recovered password by unlocking the protected file.

---

## 3. Tools Used

| Tool | Purpose |
| :--- | :--- |
| **John the Ripper** | Password-cracking tool |
| **Johnny** | Graphical interface for John the Ripper |
| **Online PDF Hash Extractor** | Extracted the password hash from the protected PDF |
| **NetworkWalks Hash Calculator** | Extracted the PDF password hash |
| **NetworkWalks Password Cracker** | Performed the password-cracking process through the browser |
| **Notepad** | Used to save the extracted hash |
| **Windows PC** | Lab environment |

---

## 4. W3-PM1: Password Cracking with JTR

### Objective
The objective was to use John the Ripper and Johnny to recover the password of the NetworkWalks-provided protected PDF.

### Step 1: Download John the Ripper
John the Ripper was downloaded for Windows from the official Openwall website. After downloading the package, it was extracted and prepared for use. The `john.exe` executable required for Johnny was located inside the `run` folder.

![Downloading John the Ripper](images/fig01_jtr_download.png)
*Figure 1: John the Ripper installation folder and directory structure.*

### Step 2: Install and Configure Johnny
Johnny was downloaded and installed as the graphical interface for John the Ripper. After opening Johnny, the Settings option was used to select the `john.exe` file from the John the Ripper `run` folder. Johnny was then ready to use the John the Ripper cracking engine.

![Configuring Johnny Path](images/fig02_johnny_settings.png)
*Figure 2: Configuring the path to john.exe inside Johnny settings.*

### Step 3: Extract the PDF Hash
The protected PDF provided by NetworkWalks was uploaded to the PDF hash extraction tool. The tool generated the password hash of the protected PDF beginning with the `$pdf$` prefix. The complete hash was copied for use with John the Ripper.

![PDF Hash Extraction](images/fig03_pdf_hash_extraction.png)
*Figure 3: Extracting the $pdf$ password hash from the protected file.*

### Step 4: Save the Hash
The extracted hash was pasted into Notepad and saved as `hash1.txt`. The hash was checked to make sure the complete value was included and that the `$pdf$` prefix was present.

![Saving Hash in Notepad](images/fig04_hash1_notepad.png)
*Figure 4: Extracted PDF hash saved as hash1.txt in Notepad.*

### Step 5: Load the Hash into Johnny
Johnny was opened and the **Open password file** option was selected. The previously created `hash1.txt` file was loaded into Johnny.

![Loading Hash into Johnny](images/fig05_johnny_hash_loaded.png)
*Figure 5: Password hash successfully loaded into Johnny GUI.*

### Step 6 & 7: Start Attack and Review Recovered Password
After loading the hash, **Start new attack** was selected. John the Ripper processed the PDF hash and attempted to recover the corresponding password. Upon completion, Johnny displayed the recovered plain-text password for the practice PDF.

![Password Cracked in Johnny](images/fig06_johnny_cracked_password.png)
*Figure 6: Attack completion displaying the successfully recovered password.*

### Video Demonstration 1: John the Ripper & Johnny Cracking Process
Watch the recorded walkthrough of extracting the hash, loading `hash2.txt`(I was not able to record hash1.txt) into Johnny, running JTR, and recovering the password:

https://github.com/user-attachments/assets/demo01_jtr_johnny_cracking.mp4

> **Note:** If viewing on GitHub, you can click the direct link below to download or view the video demo file:  
> 🎬 [Watch Demo Video 1: JTR & Johnny Execution](videos/demo01_jtr_johnny_cracking.mp4)

---

## 5. W3-PM2: Password Cracking with NetworkWalks Tools

### Objective
The second activity involved applying the same password-cracking workflow using the browser-based tools provided by NetworkWalks and verifying the recovered password on the protected PDF.

### Step 1: Download the Practice PDF
The target protected PDF was downloaded from the NetworkWalks project task page into the local environment.

![NetworkWalks Lab Setup](images/fig07_networkwalks_lab.png)
*Figure 7: Accessing the NetworkWalks practice lab and downloading the protected PDF.*

### Step 2: Extract PDF Hash via Hash Calculator
The NetworkWalks Hash Calculator was opened in a web browser. The protected PDF file was uploaded to the calculator, which processed the document and generated the PDF password hash starting with `$pdf$`.

![NetworkWalks Hash Calculator](images/fig08_networkwalks_hash_calculator.png)
*Figure 8: Protected PDF uploaded to NetworkWalks Hash Calculator to generate the $pdf$ hash value.*

### Step 3: Crack Password via NetworkWalks Cracker
The generated `$pdf$` hash value was copied and pasted into the NetworkWalks Password Cracker tool. Clicking **Start Cracking** initiated the process, which successfully retrieved the target PDF password.

![NetworkWalks Password Cracker Execution](images/fig09_networkwalks_password_cracker.png)
*Figure 9: Hash value pasted into the NetworkWalks Password Cracker to recover the password.*

### Step 4: Verify Password and Access Protected PDF
To confirm the accuracy of the recovered password, the original protected PDF was opened. Entering the cracked password successfully unlocked the file and granted access to its contents.

![Successfully Opened Protected PDF](images/fig10_pdf_unlocked.png)
*Figure 10: Target PDF opened successfully using the recovered plain-text password.*

### Video Demonstration 2: NetworkWalks Online Tools Workflow
Watch the recorded walkthrough of using the NetworkWalks Hash Calculator, running the online Password Cracker, and unlocking the PDF:

https://github.com/user-attachments/assets/demo02_networkwalks_tools_cracking.mp4

> **Note:** If viewing on GitHub, you can click the direct link below to download or view the video demo file:  
> 🎬 [Watch Demo Video 2: NetworkWalks Tools Execution](videos/demo02_networkwalks_tools_cracking.mp4)

---

## 6. Lessons Learned

* **Applied Experience:** Reinforced existing concepts of John the Ripper and hash extraction by performing end-to-end cracking in a structured environment.
* **Format Requirements:** Verified the critical importance of ensuring exact string preservation (including prefixes like `$pdf$`) when saving hashes into target text files.
* **Tool Versatility:** Successfully executed parallel workflows comparing local CLI/GUI tools (JTR + Johnny) with cloud-based/web-based utility sets (NetworkWalks Hash Calculator & Cracker).
* **End-to-End Validation:** Demonstrated full password recovery validation by taking the output of the hash cracking tools and applying it to successfully remove access restrictions on the protected target file.

---

## 7. Conclusion

For Week 3 of the NetworkWalks Cybersecurity & Ethical Hacking Internship, I completed the password-cracking activities using John the Ripper, Johnny, and NetworkWalks Tools.

This project provided practical application of techniques I was already familiar with while giving me additional hands-on experience working with password-protected PDF files, hash extraction pipelines, cracking mechanisms across multiple platforms, and final document access validation.

---

## 8. Mentor

**Waqas Karim (CCIE)**  

This laboratory was completed under the technical guidance of Waqas Karim, providing an opportunity to reinforce existing cybersecurity knowledge through practical environment setup and hands-on networking configuration.

Thank you for the guidance and for providing a practical environment to strengthen my cybersecurity skills.

---
*End of Report*
