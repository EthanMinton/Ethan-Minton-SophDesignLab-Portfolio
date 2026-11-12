# A10 – Lead Screw Translating System

## Objective

The objective of this assignment is to design and print a useful pair of parts that demonstrates an RC2 sliding fit. I will create a puck and matching holder, research the required clearance, and account for variation from SLA printing and curing. After printing, I will measure the mating features and test whether the puck slides into the holder smoothly while maintaining accurate alignment. The total print volume, including supports, must remain below 20 mL.

## Research 

### Sliding Fits
Below is the machinery handbook page showing the values for typical sliding fits; we were instructed to attempt an RC 2 sliding fit. The assignment defines this as "It is a good choice for locating pins and parts that need to slide into place with minimal play." This is essentially our goal with designing our design and fit.

<img width="1500" height="882" alt="image" src="https://github.com/user-attachments/assets/b67eb348-b377-432d-ae41-637fba9b1dfb" />

An RC2 sliding fit would be used in applications such as locating pins in assembly fixtures or removable parts that need to slide into position while maintaining accurate alignment. The small clearance allows the parts to move together without requiring a press, while limiting unwanted movement. This is similar to the goal of my design, where the puck needs to slide into the holder with minimal play.

According to Table 8a in the Machinery’s Handbook, the RC2 clearance limits depend on the nominal size of the mating features. Since my fit sizes are 1 inch and below, the following ranges apply. The handbook values are given in thousandths of an inch; I converted them to inches below.

| Nominal Size (in) | Minimum RC2 Clearance (in) | Maximum RC2 Clearance (in) |
|---|---:|---:|
| Over 0 through 0.12 | 0.00010 | 0.00055 |
| Over 0.12 through 0.24 | 0.00015 | 0.00065 |
| Over 0.24 through 0.40 | 0.00020 | 0.00085 |
| Over 0.40 through 0.71 | 0.00025 | 0.00095 |
| Over 0.71 through 1.19* | 0.00030 | 0.00120 |

Very quickly, the consensus of the design is that the values from the Machinery's handbook were not optimized for the Resin Printers. I encountered multiple students who had specifically pointed out that even measurements of 6 thou for their clearance were creating fits that would be considered interference fits that would not allow any amount of sliding. This caused me to greatly readjust my interpretation of the clearance in order to ensure that my part is printed correctly.

With this in mind, I decided to refer back to the document from the beginning of the year that gave general allowances for different types of 3D printing. Since we handle Stereolithography, we have general clearance for "Connecting/ Moving Parts" set to roughly 0.5 mm, or just under 20 thou. With my knowledge from all of the information I have been given, I decided that it would be best for me to pick a clearance of around 15 thou.

<img width="1381" height="971" alt="image" src="https://github.com/user-attachments/assets/189c5234-ea54-4c02-97db-ffb416705d54" />


<img width="1617" height="957" alt="image" src="https://github.com/user-attachments/assets/2bcfa3f5-b77a-4f56-9de1-92ff6946c92a" />


I also researched how shrinking or expansion of the resin prints could affect the fit between my parts. According to Formlabs, resin can shrink during post-curing because the additional connections between the molecules pull the material closer together. However, Formlabs also states that PreForm already compensates for the expected shrinkage when using the correct material settings and recommended curing process.

With this in mind, I decided that adding an assumed shrinkage percentage to the entire model could cause more issues with the fit. I could not find a specific volume shrinkage percentage in the Clear V5 technical data sheet, so I accounted for possible dimensional variation through the clearance between my mating parts instead. After printing and fully curing the parts, I can compare the actual measurements to my model and adjust any dimensions that are preventing the parts from sliding properly.

https://formlabs.com/support/Introduction-to-Post-Curing-Prints/

### Real-World Application

<img width="1917" height="1130" alt="image" src="https://github.com/user-attachments/assets/93bc2e14-98e1-45d9-8792-28a2db3ce421" />
<img width="1423" height="52" alt="image" src="https://github.com/user-attachments/assets/4f2e5410-c31c-454e-9e98-a09fc9201fc5" />

### Hand Sketch

REMIND CREATE HAND SKETCH

## CAD Design 
### Ring Holder 
<img width="1617" height="962" alt="image" src="https://github.com/user-attachments/assets/5aec8996-673e-471d-8666-aa71fb0f57af" />

<img width="1621" height="958" alt="image" src="https://github.com/user-attachments/assets/70a63785-4a1f-47f2-b632-153ba29caa37" />

<img width="1615" height="957" alt="image" src="https://github.com/user-attachments/assets/70f11805-382f-47aa-9e43-e204ccaee2ff" />

<img width="1616" height="956" alt="image" src="https://github.com/user-attachments/assets/44d3f7cc-e157-418c-9ec1-d6cda0159b8f" />


### Puck Cap

<img width="1251" height="523" alt="image" src="https://github.com/user-attachments/assets/4e3a9aad-71a2-4305-ab7a-242a85d23830" />

<img width="1616" height="952" alt="image" src="https://github.com/user-attachments/assets/92a11ecb-4a54-4ae3-a23c-f1d739c4bd76" />

<img width="1616" height="958" alt="image" src="https://github.com/user-attachments/assets/b7e92818-8368-41ba-818b-d1830ce5ac9b" />

<img width="1617" height="957" alt="image" src="https://github.com/user-attachments/assets/6ed06de2-70bd-4d91-8bc3-52385fb77694" />

<img width="1616" height="961" alt="image" src="https://github.com/user-attachments/assets/e6c66f45-e231-4c9d-b06c-6c6981fd6ca2" />

<img width="1616" height="951" alt="image" src="https://github.com/user-attachments/assets/b326bdfd-c92b-40b2-b8fa-ca3dbcbf2f42" />
