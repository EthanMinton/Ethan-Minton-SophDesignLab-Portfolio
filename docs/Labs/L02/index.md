# **Lab #2: Print something Small**

---

## **Objective**

Learn the core foundation of the additive manufacturing process through sourcing standard 3D file formats, configuring slices within PrusaSlicer, and transferring G-code to the 3D printer for fabrication.

---

## **Analyze**

**DfAM Individual Research**: The actions that are required to be taken when performing additive manufacturing must be planned thoroughly to ensure that the process is conducted smoothly and without failure. Plan for post-processing, such as easy access to remove supports and features that allow for better handling. The design phase is the most versatile; use it to ensure the post-processing phase flows smoothly. Failures in the post-design phase can be costly, with money spent and time wasted.

**Source:** [https://additiveplus.com/design-for-additive-manufacturing/](https://additiveplus.com/design-for-additive-manufacturing/)

**FDM Individual Research:** An important design consideration that Engineers must take into account when handling FDM is overhangs. An overhang is a section of a 3d print that is found to be layered outward from structural support, leading to many possible defects that could ruin an overall print. The general rule that engineers follow is the 45-degree rule, which essentially says that as long as the overhang is found to be 45 degrees or less, the print can be successful without the need for supports.

**Source:** [https://www.addmangroup.com/wp-content/uploads/2024/08/ADDMAN_DfAM-Guide2024.pdf](https://www.addmangroup.com/wp-content/uploads/2024/08/ADDMAN_DfAM-Guide2024.pdf)


**Teamate Saniyah:**

Wall thickness is considered extremely important when designing with 3D printers, as it heavily correlates to whether or not a creation is load-bearing. A wall too thin could cause buckling in the creation process, leading to design failure. Thick walls also typically contain infill patterns to save on total material cost and time taken for a print to complete. 

When designing and preparing for additive manufacturing, you must take steps to prevent thermal warping in whatever you are manufacturing. Thermal warping is the unintended distortion of material due to uneven cooling that leads to thermal stress impacting the material. Prevention heavily relies on designing proper chambers that will allow for even cooling through the entire model.

---

## **Decide**

### **Downloading Decision**

The item I chose to download is a Bobby Pin Demo Print. Initially, I selected to print a flat piece of art with 2 cats but decided against it, as I felt that the print would be too flat and lack any real showcase of what the 3D printer could do. I chose the bobby pin because, despite its simplistic shape and nature, it showcases techniques outside of creating a static object. For example, the flexibility of the material we can use, with it bending and having its structure pull it back to its resting place. It shows the precistion of which the printer can print with the material and the smoothness of its edges. It isn't a trinket to carry around, but it does help gather more experience and knowledge with the printer's and materials' capabilities.

**Cat Print Source:** [https://www.printables.com/model/447015-cat-love-for-fabric/files](https://www.printables.com/model/447015-cat-love-for-fabric/files)

<img width="1901" height="988" alt="image" src="https://github.com/user-attachments/assets/50caaa6d-0eec-4412-ad67-cbabfd857809" />

<img width="1916" height="1136" alt="image" src="https://github.com/user-attachments/assets/cfb8d001-e890-499f-9fd0-95e3e911a879" />

**Bobby Pin Print Source:** [https://www.printables.com/model/88337-bobby-pin-demo-print/files](https://www.printables.com/model/88337-bobby-pin-demo-print/files)

<img width="1900" height="982" alt="image" src="https://github.com/user-attachments/assets/578102b2-60d5-484b-b50b-44ff8e9a6145" />

<img width="1917" height="1136" alt="image" src="https://github.com/user-attachments/assets/ba290d43-01db-4408-9d47-cb7cb7328040" />

### **Group Members**
- Jack Welch
- Saniyah Wilson
- Nicholas Brady

### **Orientation**

To print within the lab, we had to form a group of 4 and compile all of our files together within a single PrusaSlicer file. We decided to orient all of the bodies close together so that the 3D printer had less distance to travel between them while printing. In our instructions, we were asked to scale down any large models to ensure that the prints would only take roughly 20 minutes. Nicholas Brady had to scale his down on all axes, as his initial file was well over the design constraints around time. 

**Nicholas' Model Pre-scale:**
<img width="1380" height="1036" alt="Screenshot 2026-08-27 134942" src="https://github.com/user-attachments/assets/79a2f53c-c571-49ef-a657-bdab4970d1f3" />

**Final Set Up for Models:**
<img width="1386" height="1058" alt="Screenshot 2026-08-27 135157 (1)" src="https://github.com/user-attachments/assets/6fa4acc4-a620-41a3-8ca2-17e20e71632b" />

---

### **Settings**

<img width="446" height="1017" alt="Screenshot 2026-08-27 135258" src="https://github.com/user-attachments/assets/72941c37-b190-4370-addd-eb8416659038" />

**3D Printer ID:** PC-13 

**3D Printer Model:** Prusa CORE One 0.4 Nozzle

**Print Value:** 0.15 mm SPEED

**Infill:** 15%

**Material Used:** PETG

**Estimated Time Taken:** 13 Minutes (Normal)

Most of the chosen settings and information were already defined for us, meaning we lacked the option to change any meaningful setting. The one choice we had was the printer number, #13 in this case, which ultimately determined that the material used would be PETG. Once all of the settings had been checked and input, we sliced the models.

**Model Post Slice:**
<img width="1390" height="1058" alt="Screenshot 2026-08-27 135228" src="https://github.com/user-attachments/assets/56f978cc-2e3d-4d25-a2f8-7f60cb741557" />

**G-code File Uploaded to USB Stick:**
<img width="937" height="112" alt="Screenshot 2026-08-27 150748" src="https://github.com/user-attachments/assets/c8d9b286-5448-4a31-903f-272e55d8e037" />

After we sliced the models, we uploaded the G-code to the USB stick and transferred it to the PC-13 3D Printer.

---

### **Print**

Upon initially uploading the file into the 3D printer, we immediately began to face what was considered a software issue with the printer itself, as it claimed that we had selected the wrong constraint for materials, which, as observed in the photo above, contradicts the setting applied. After ensuring our constraint was actually correct, we continued with the print despite its objection.

**Video #1: First Attempt Print**

<video src="https://github.com/user-attachments/assets/586e0056-9ec9-4016-b207-31bb3ef24029" autoplay loop muted playsinline width="100%">
</video>

[Download of Video #1 File](https://github.com/user-attachments/assets/586e0056-9ec9-4016-b207-31bb3ef24029)

If you observe closely, you can see how the printed parts are becoming increasingly turbulent. Eventually, the printer just refused to continue printing, which led to us discovering that the material roll found on the side of the printer had gotten caught, which prevented any of the filament from being properly used. After cleaning the base and restarting the print, we were finally able to continue without issue.

**Video #2: Second Attempt Print**

<video src="https://github.com/user-attachments/assets/66eab676-9780-4e4d-96e4-330309d691d5" autoplay loop muted playsinline width="100%">
</video>

[Download of Video #2 File](https://github.com/user-attachments/assets/66eab676-9780-4e4d-96e4-330309d691d5)

**2 images showing Mid-print Stages:**
<img width="4032" height="3024" alt="IMG_5723" src="https://github.com/user-attachments/assets/a2a00d75-bcfe-47a2-a2d4-c6c504b28657" />

<img width="4032" height="3024" alt="IMG_5727" src="https://github.com/user-attachments/assets/92bdc67f-be33-4f86-8c36-39eb0f3e4286" />

**Platform lowered as Print Finished:**
<img width="4032" height="3024" alt="IMG_5731" src="https://github.com/user-attachments/assets/10d9db03-97bd-4722-927a-9429c5248c6e" />

**Final Results from 3D Printer Screen:**
<img width="4032" height="3024" alt="IMG_5732" src="https://github.com/user-attachments/assets/44d56a2a-35df-42dc-af8b-444d070e7b39" />


## Communicate

### Lessons Learned

After this project was concluded, many lessons and experiences were learned from failures. Three of these lessons were learned directly because of our initial print failure due to the filament getting caught. 

1. For one, you should always check to ensure that the filament can spin freely without any issues. Initially, I remember noticing the filament being positioned in a way that I considered odd, but I did not act on it to fix it. Knowing what I know now, I wouldn't hesitate to reposition it so that it could spin freely.
2.  Always routinely check on print quality and current progress to minimize the time taken by error prints. After the filament had completely stopped printing it took us another roughly 5 minutes before we noticed it wasn't printing layers anymore. If we had caught it sooner, we wouldn't have had to stay after the lab to obtain our 3D prints.
3.  After we had realized that something had failed within the 3D printing process, we had to initially determine the actual cause of the failure. Professor 
Terence Fagan had asked to see the settings and file of the 3D print, but mistakenly, the teammate, Jack Welch, who had set up the G-code file, had to leave the lab for another class afterwards. Eventually, we discovered the real issue, but the lesson was learned nonetheless. The person who programs the file should be checked to ensure that they will be able to stay afterwards if issues arise.
4.  Outside of our failure one of the most important lessons learned is that as a group we need to clear out the main channel to access the 3D printers, repeadily I was not able to reach our 3D printer due to the fact that so many people were in the way as they were watching the printers. It is a good lesson that a select person from each group can actively monitor the printers at a time so that everyone can access and view their printers without crowding or complications.

**Actual Time taken to Print:**  18 Minutes 24 Seconds

### Resources

- DfAM Individual Research: [https://additiveplus.com/design-for-additive-manufacturing/](https://additiveplus.com/design-for-additive-manufacturing/)
- FDM Individual Research: [https://www.addmangroup.com/wp-content/uploads/2024/08/ADDMAN_DfAM-Guide2024.pdf](https://www.addmangroup.com/wp-content/uploads/2024/08/ADDMAN_DfAM-Guide2024.pdf)
- Cat Print: [https://www.printables.com/model/447015-cat-love-for-fabric/files](https://www.printables.com/model/447015-cat-love-for-fabric/files)
- Bobby Pin Print: [https://www.printables.com/model/88337-bobby-pin-demo-print/files](https://www.printables.com/model/88337-bobby-pin-demo-print/files)
- PrusaSlicer: [https://www.prusa3d.com/p/prusaslicer/](https://www.prusa3d.com/p/prusaslicer/)
