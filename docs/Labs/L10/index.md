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

With this in mind, I decided to refer back to the document from the beginning of the year that gave general allowances for different types of 3D printing. Since we handle Stereolithography, we have general clearance for "Connecting/ Moving Parts" set to roughly 0.5 mm, or just under 20 thou. With my knowledge from all of the information I have been given, I decided that it would be best for me to pick a clearance of around 20 thou.

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

I first measured the outside diameter of the ring using digital calipers. The measurement was approximately 0.9625 in. I used this to select a 1.00 in inside diameter, or 0.50 in radius, for the holder so the ring would have room to fit.

<img width="4032" height="3024" alt="IMG_0299" src="https://github.com/user-attachments/assets/db309d78-2705-42a7-ac40-78fbc4ef54a4" />

I then measured the height of the ring, which was approximately 0.2410 in. I used this measurement to select a 0.25 in inside height for the holder. These measurements allowed me to design a simple holder around one actual ring.

<img width="4032" height="3024" alt="IMG_0300" src="https://github.com/user-attachments/assets/14324f3e-9ffe-4bf5-8007-ee01a1875091" />

I sketched the side profile of the holder with a 0.50 in inside radius and 0.25 in inside height based on the ring measurements. I also included the 0.35 in radius at the bottom opening, a 0.10 in base thickness, and the stepped area near the top for the puck cap. The other dimensions found here are not significant to the sliding fit and rather provide strucuture.

<img width="1617" height="962" alt="image" src="https://github.com/user-attachments/assets/5aec8996-673e-471d-8666-aa71fb0f57af" />

I used a 360-degree revolve around the center axis to turn the sketch into the round holder. This created the walls, lower opening, and internal steps from one sketch.

<img width="1621" height="958" alt="image" src="https://github.com/user-attachments/assets/70a63785-4a1f-47f2-b632-153ba29caa37" />

I created a centered rectangle on the Top Plane measuring 1.15 in long and 0.20 in wide. This sketch defines the opening that lines up with the rectangular feature on the puck.

<img width="1615" height="957" alt="image" src="https://github.com/user-attachments/assets/70f11805-382f-47aa-9e43-e204ccaee2ff" />

I used a Through All extruded cut to remove the material inside the rectangle. This created the opening for the matching feature on the puck cap.

<img width="1616" height="956" alt="image" src="https://github.com/user-attachments/assets/44d3f7cc-e157-418c-9ec1-d6cda0159b8f" />


### Puck Cap

I created a global variable named "CLEARANCE" and set it to 0.020 in. I applied the clearance by reducing the puck dimensions while keeping the holder dimensions fixed. Linking these dimensions to one variable makes it easier to adjust the fit later.

<img width="1251" height="523" alt="image" src="https://github.com/user-attachments/assets/4e3a9aad-71a2-4305-ab7a-242a85d23830" />

I sketched the puck profile with a 0.48 in radius and a 0.25 in height. The radius is 0.020 in smaller than the holder’s 0.50 in inside radius to provide space for the parts to slide together. This gives a puck diameter of 0.96 in and a total diameter clearance of 0.040 in.

<img width="1616" height="952" alt="image" src="https://github.com/user-attachments/assets/92a11ecb-4a54-4ae3-a23c-f1d739c4bd76" />

I revolved the profile 360 degrees around the center axis to create the round puck. This forms the main body of the removable cap.

<img width="1616" height="958" alt="image" src="https://github.com/user-attachments/assets/b7e92818-8368-41ba-818b-d1830ce5ac9b" />

I sketched the rectangular feature across the puck and set its length using the equation 1.15 − 2 × CLEARANCE. With CLEARANCE set to 0.020 in, the length becomes 1.11 in. This makes it shorter than the holder’s 1.15 in opening, leaving 0.020 in at each end when centered. This was to ensure that this very thin piece would have plenty of room to fit and slide without breaking or being obstructed.

<img width="1617" height="957" alt="image" src="https://github.com/user-attachments/assets/6ed06de2-70bd-4d91-8bc3-52385fb77694" />

I set the rectangle’s width using the equation 0.20 − CLEARANCE, giving a width of 0.18 in. Compared with the holder’s 0.20 in opening, this provides 0.020 in of total width clearance, or 0.010 in on each side when centered.

<img width="1616" height="961" alt="image" src="https://github.com/user-attachments/assets/e6c66f45-e231-4c9d-b06c-6c6981fd6ca2" />

I used a boss extrusion to add the rectangular feature to the puck and merged it with the round body. The extrusion height uses the equation 0.05 − CLEARANCE, giving a height of 0.03 in. This applies the printing allowance to the puck’s raised feature as well.

<img width="1616" height="951" alt="image" src="https://github.com/user-attachments/assets/b326bdfd-c92b-40b2-b8fa-ca3dbcbf2f42" />

### Assembly 
Assembled View
<img width="1617" height="955" alt="image" src="https://github.com/user-attachments/assets/51063712-e09b-4fe8-b9c2-16a1f48af021" />

Showing the Locking Mechanism
<img width="1612" height="961" alt="image" src="https://github.com/user-attachments/assets/4abc14ec-fd3f-4523-9709-cbd38ccfaf74" />

Exploded View
<img width="1620" height="951" alt="image" src="https://github.com/user-attachments/assets/bdfda143-d9e1-402e-8929-e741c869fc5e" />

### Fit Comparison 

I used a 1.00 in nominal size for the circular fit between the ring holder and puck. I applied the printing allowance by reducing the puck dimensions while keeping the holder dimensions fixed.

| Mating feature | Holder dimension (in) | Puck dimension (in) | Total CAD clearance (in) |
|---|---:|---:|---:|
| Circular diameter | 1.00 | 0.96 | 0.040 |
| Rectangular opening width | 0.20 | 0.18 | 0.020 |
| Rectangular opening length | 1.15 | 1.11 | 0.040 |

The puck radius was reduced from 0.50 in to 0.48 in. This provides 0.020 in of clearance on each side, giving a total diameter clearance of 0.040 in.

For the 1.00 in nominal circular fit, the Machinery’s Handbook gives an RC2 clearance range of 0.00030–0.00120 in. My CAD clearance is larger because I allowed extra space for printing variation. After printing and curing, I will measure both parts and compare the actual clearance with the RC2 range. I will also check whether the puck slides smoothly without too much play.
