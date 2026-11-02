# A10 – Lead Screw Translating System

## Objective


## Research 

Below is the machinery handbook page displaying all of the values for the typical sliding fits; we were instructed to attempt to create an RC 2 sliding fit. This is defined by the assignment as "It is a good choice for locating pins and parts that need to slide into place with minimal play." This is essentially our goal with designing our design and fit.

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

With this in mind, I decided to refer back to the document from the beginning of the year that gave general allowances for different types of 3D printing. Since we handle Stereolithography, we have general clearance for "Connecting/ Moving Parts" set to roughly 0.5 mm, or just under 20 thou. With my knowledge from all of the information I have been given I decided that it would be best for me to pick a clearance of around 15 thou.

<img width="1381" height="971" alt="image" src="https://github.com/user-attachments/assets/189c5234-ea54-4c02-97db-ffb416705d54" />


<img width="1617" height="957" alt="image" src="https://github.com/user-attachments/assets/2bcfa3f5-b77a-4f56-9de1-92ff6946c92a" />


I also researched how shrinking or expansion of the resin prints could affect the fit between my parts. According to Formlabs, resin can shrink during post-curing because the additional connections between the molecules pull the material closer together. However, Formlabs also states that PreForm already compensates for the expected shrinkage when using the correct material settings and recommended curing process.

With this in mind, I decided that adding an assumed shrinkage percentage to the entire model could cause more issues with the fit. I could not find a specific volume shrinkage percentage in the Clear V5 technical data sheet, so I accounted for possible dimensional variation through the clearance between my mating parts instead. After printing and fully curing the parts, I can compare the actual measurements to my model and adjust any dimensions that are preventing the parts from sliding properly.

https://formlabs.com/support/Introduction-to-Post-Curing-Prints/

REMIND CREATE HAND SKETCH

<img width="1917" height="1130" alt="image" src="https://github.com/user-attachments/assets/93bc2e14-98e1-45d9-8792-28a2db3ce421" />
<img width="1423" height="52" alt="image" src="https://github.com/user-attachments/assets/4f2e5410-c31c-454e-9e98-a09fc9201fc5" />

## Analyze


## Decide
_Reference your concept selection (Pugh matrix) here. How does this design follow from that decision?_

## Communicate

