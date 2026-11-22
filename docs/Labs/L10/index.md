# Lab 10 – RC2 Sliding Fit Ring Holder

## Objective

The objective of this assignment is to design and print a useful pair of parts that demonstrates an RC2 sliding fit. I will make a puck and matching ring holder, research the required clearance, and account for SLA printing and curing. After printing, I will measure the parts and check whether the puck slides into the holder smoothly without too much play. The total print volume, including supports, must stay below 20 mL.

## Research

### Sliding Fits

The Machinery’s Handbook table below shows the values for different running and sliding fits. For this assignment, we were instructed to attempt an RC2 sliding fit. The goal is for the parts to slide together while staying accurately lined up.

<img width="1500" height="882" alt="Machinery’s Handbook running and sliding fit table" src="https://github.com/user-attachments/assets/b67eb348-b377-432d-ae41-637fba9b1dfb" />

The RC2 clearance limits depend on the nominal size of the mating features. The table below covers sizes up to 1 inch. The handbook values are in thousandths of an inch, so I converted them to inches.

| Nominal Size (in) | Minimum RC2 Clearance (in) | Maximum RC2 Clearance (in) |
|---|---:|---:|
| Over 0 through 0.12 | 0.00010 | 0.00055 |
| Over 0.12 through 0.24 | 0.00015 | 0.00065 |
| Over 0.24 through 0.40 | 0.00020 | 0.00085 |
| Over 0.40 through 0.71 | 0.00025 | 0.00095 |
| Over 0.71 through 1.19 | 0.00030 | 0.00120 |

Several students told me that their parts would not slide together even with 0.006 in of clearance in CAD. This made me concerned that using the handbook clearance directly in my model would produce parts that were too tight.

I referred back to the printing guide provided earlier in the semester. It recommends roughly 0.5 mm, or 0.0197 in, of clearance for connecting or moving SLA parts. Based on this guide and the problems other students had, I chose a CLEARANCE variable of 0.020 in. The actual gap depends on how this value is applied to each dimension, as shown in the CAD section.

<img width="1381" height="971" alt="Protolabs design rules for 3D printing" src="https://github.com/user-attachments/assets/189c5234-ea54-4c02-97db-ffb416705d54" />

I also researched how curing could change the dimensions. Formlabs explains that resin can shrink during post-curing as more bonds form in the material. Its material print settings account for the expected shrinkage during printing and curing.

I could not find a specific volume shrinkage percentage in the Clear V5 technical data sheet. Instead of scaling the entire model by an assumed percentage, I allowed extra space between the mating parts. I planned to measure the finished parts and compare them with the CAD dimensions.

### Real-World Application

An RC2 sliding fit can be used for pins that line up parts during assembly. The pin slides into a matching hole without needing to be pressed in, while the small clearance keeps the parts from moving around too much. This allows the parts to be lined up and taken apart when needed. My ring holder uses a similar idea, where the puck cap needs to slide into place while staying aligned with the holder. I also plan to use this type of fit for the pulley in my final project.

### Hand Sketch

This rough hand sketch shows the main sliding fit between the puck and ring holder, along with the space for the ring. The proposed puck diameter is 0.96 in, and the holder opening is 1.00 in, giving 0.04 in of total diameter clearance. These were preliminary dimensions. The final dimensions and remaining features had not been chosen at this stage.

<img width="1640" height="1190" alt="Rough hand sketch of the puck and ring holder" src="https://github.com/user-attachments/assets/4c6acb31-d2b0-4c19-abc1-be16f6b3fc11" />

## CAD Design

### Ring Holder

I first measured the outside diameter of the ring using digital calipers. It measured approximately 0.9625 in. I used this to choose a 1.00 in inside diameter, or 0.50 in radius, for the holder.

<img width="4032" height="3024" alt="Measuring the ring’s outside diameter" src="https://github.com/user-attachments/assets/db309d78-2705-42a7-ac40-78fbc4ef54a4" />

I then measured the ring’s height, which was approximately 0.2410 in. I chose a 0.25 in inside height so the ring would have room to fit.

<img width="4032" height="3024" alt="Measuring the ring’s height" src="https://github.com/user-attachments/assets/14324f3e-9ffe-4bf5-8007-ee01a1875091" />

I sketched the holder’s side profile using the 0.50 in inside radius and 0.25 in inside height. I also added a 0.35 in radius at the bottom opening, a 0.10 in bottom thickness, and the stepped area near the top. The groove allows the puck tabs to turn beneath the upper lip.

<img width="1617" height="962" alt="Dimensioned holder profile" src="https://github.com/user-attachments/assets/5aec8996-673e-471d-8666-aa71fb0f57af" />

I revolved the sketch 360 degrees around the center axis to create the round holder.

<img width="1621" height="958" alt="Revolving the holder profile" src="https://github.com/user-attachments/assets/70a63785-4a1f-47f2-b632-153ba29caa37" />

I created a centered rectangle on the Top Plane measuring 1.15 in long and 0.20 in wide. This defines the opening for the rectangular feature on the puck.

<img width="1615" height="957" alt="Sketching the holder’s rectangular opening" src="https://github.com/user-attachments/assets/70f11805-382f-47aa-9e43-e204ccaee2ff" />

I used a Through All extruded cut to remove the material inside the rectangle.

<img width="1616" height="956" alt="Cutting the rectangular opening" src="https://github.com/user-attachments/assets/44d3f7cc-e157-418c-9ec1-d6cda0159b8f" />

### Puck Cap

I created a global variable named CLEARANCE and set it to 0.020 in. I applied the allowance by reducing the puck dimensions while keeping the holder dimensions fixed. This lets me adjust the linked dimensions by changing one value.

<img width="1251" height="523" alt="Puck clearance equations" src="https://github.com/user-attachments/assets/4e3a9aad-71a2-4305-ab7a-242a85d23830" />

I sketched the puck with a 0.48 in radius and a 0.25 in height. The radius is 0.020 in smaller than the holder’s 0.50 in inside radius. This gives a puck diameter of 0.96 in and a total diameter clearance of 0.040 in.

<img width="1616" height="952" alt="Dimensioned puck profile" src="https://github.com/user-attachments/assets/92a11ecb-4a54-4ae3-a23c-f1d739c4bd76" />

I revolved the profile 360 degrees to create the round puck.

<img width="1616" height="958" alt="Revolving the puck profile" src="https://github.com/user-attachments/assets/b7e92818-8368-41ba-818b-d1830ce5ac9b" />

I sketched the rectangular feature across the puck. Its length uses the equation 1.15 − 2 × CLEARANCE, giving a length of 1.11 in. This leaves 0.020 in at each end when centered in the holder’s 1.15 in opening.

<img width="1617" height="957" alt="Applying clearance to the rectangular feature’s length" src="https://github.com/user-attachments/assets/6ed06de2-70bd-4d91-8bc3-52385fb77694" />

The width uses the equation 0.20 − CLEARANCE, giving a width of 0.18 in. This provides 0.020 in of total width clearance, or 0.010 in on each side when centered.

<img width="1616" height="961" alt="Applying clearance to the rectangular feature’s width" src="https://github.com/user-attachments/assets/e6c66f45-e231-4c9d-b06c-6c6981fd6ca2" />

I used a boss extrusion to add the rectangular feature to the puck. The extrusion height uses the equation 0.05 − CLEARANCE, giving a height of 0.03 in. I merged it with the round body.

<img width="1616" height="951" alt="Extruding the rectangular feature" src="https://github.com/user-attachments/assets/b326bdfd-c92b-40b2-b8fa-ca3dbcbf2f42" />

### Assembly

**Assembled View**

I used concentric and coincident mates to line up the puck and holder. The tabs pass through the openings, then turn beneath the upper lip to hold the cap in place. To remove the cap, the tabs must line up with the openings again.

<img width="1617" height="955" alt="Assembled puck and holder" src="https://github.com/user-attachments/assets/51063712-e09b-4fe8-b9c2-16a1f48af021" />

**Showing the Locking Mechanism**

<img width="1612" height="961" alt="CAD view of the locking mechanism" src="https://github.com/user-attachments/assets/4abc14ec-fd3f-4523-9709-cbd38ccfaf74" />

**Exploded View**

<img width="1620" height="951" alt="Exploded view of the puck and holder" src="https://github.com/user-attachments/assets/bdfda143-d9e1-402e-8929-e741c869fc5e" />

### Fit Comparison

I used a 1.00 in nominal size for the circular fit. The table below shows the clearance created by reducing the puck dimensions.

| Mating feature | Holder dimension (in) | Puck dimension (in) | Total CAD clearance (in) |
|---|---:|---:|---:|
| Circular diameter | 1.00 | 0.96 | 0.040 |
| Rectangular opening width | 0.20 | 0.18 | 0.020 |
| Rectangular opening length | 1.15 | 1.11 | 0.040 |

For the 1.00 in nominal circular fit, the Machinery’s Handbook gives an RC2 clearance range of 0.00030–0.00120 in. My CAD clearance is larger because I added room for printing variation. I planned to check the finished dimensions and sliding movement after printing.

## Pre-Processing

I prepared both parts in PreForm for the Form 4 printer named “HiddenCod” using Clear V5 resin.

<img width="4032" height="3024" alt="Printer — HiddenCod" src="https://github.com/user-attachments/assets/f5b537de-2e37-4bd9-a854-581405cb61c6" />

Since I had limited experience with SLA printing, I was recommended to use PreForm’s automatic orientation tool. I used its suggested orientation. The holder’s opening faced upward, while the puck was tilted near vertical.

<img width="742" height="322" alt="PreForm settings" src="https://github.com/user-attachments/assets/7af71231-2cb0-49db-9b6f-c7d83e0999e2" />

Both parts were placed beside each other on the build plate. Since it was early in the morning, I was unable to share the plate with other students. Only my holder and puck were included in this print.

Supports were added beneath both parts. The settings are shown below.

<img width="472" height="827" alt="Support settings" src="https://github.com/user-attachments/assets/87691d01-511c-42e7-87f7-9cdad12e6b81" />

The holder’s upper lip is 0.05 in thick, and the bottom section is 0.10 in thick. The puck’s tabs are 0.03 in thick after applying the clearance equation, making them the thinnest features of the two parts.

The layer height was 0.100 mm, and PreForm estimated a print time of 46 minutes. The supported setup used 14.44 mL of material, which was 5.56 mL below the 20 mL limit.

<img width="1917" height="1130" alt="PreForm build preview and print settings" src="https://github.com/user-attachments/assets/93bc2e14-98e1-45d9-8792-28a2db3ce421" />

<img width="1423" height="52" alt="Printer status — HiddenCod and Clear V5" src="https://github.com/user-attachments/assets/4f2e5410-c31c-454e-9e98-a09fc9201fc5" />

## Post-Processing

After printing, the parts were still attached to the build plate with their supports.

<img width="4032" height="3024" alt="Finished print attached to the build plate" src="https://github.com/user-attachments/assets/043c6e35-efba-4d51-8112-31d4f1f4ea29" />

I washed the parts to remove leftover resin. The wash cycle was set to 10 minutes, with 9 minutes and 54 seconds remaining when I took the picture.

<img width="3024" height="4032" alt="Washing the printed parts" src="https://github.com/user-attachments/assets/3454e701-4145-4c1f-81b4-8bb603d50038" />

I used a scraper to remove the parts and their support bases from the build plate.

<img width="4032" height="3024" alt="Removing the parts from the build plate" src="https://github.com/user-attachments/assets/73732b1b-f690-4a08-b2e2-318e7354cecd" />

I then used flush cutters to remove the supports. I worked carefully around the thin tabs to avoid damaging them.

<img width="4032" height="3024" alt="Removing the supports" src="https://github.com/user-attachments/assets/8306b19c-6197-4508-9b17-a120188233d5" />

After removing the supports, I cured both parts for 15 minutes using the machine’s default settings.

<img width="3024" height="4032" alt="Curing the printed parts" src="https://github.com/user-attachments/assets/0c64969c-1043-4e8f-9957-70d5fcddd194" />

The finished parts kept their overall shape. The surfaces looked cloudy and had visible support marks. Raised spots on the mating surfaces could affect how smoothly the parts slide.

<img width="4032" height="3024" alt="Finished holder and puck" src="https://github.com/user-attachments/assets/25e0e50d-3c82-45ee-b329-41432a818fa4" />

I placed the ring inside the holder to check the space I had designed around its measurements. The ring fit inside as intended.

<img width="4032" height="3024" alt="Ring placed inside the holder" src="https://github.com/user-attachments/assets/27d4f598-9415-4cbf-89e5-dcee6aa3bce0" />

I then placed the puck into the holder. The cap fit into the opening and covered the ring.

<img width="4032" height="3024" alt="Assembled ring holder" src="https://github.com/user-attachments/assets/ff3b5497-3135-4bd6-a5b1-3dace41d1ca4" />

## Fit Test

I measured the printed puck’s outside diameter using digital calipers. It measured 0.9925 in, compared with the CAD diameter of 0.9600 in.

<img width="4032" height="3024" alt="Measuring the puck’s outside diameter" src="https://github.com/user-attachments/assets/b4709d73-4b65-4c2b-a9b0-84c1f88b1a91" />

I measured the holder’s inside diameter using the inside jaws of the calipers. It measured 0.9965 in, compared with the CAD diameter of 1.0000 in.

<img width="4032" height="3024" alt="Measuring the holder’s inside diameter" src="https://github.com/user-attachments/assets/837cf7c5-25bc-4518-90de-88aa4721989b" />

| Feature | CAD dimension (in) | Measured dimension (in) | Difference from CAD (in) |
|---|---:|---:|---:|
| Puck outside diameter | 0.9600 | 0.9925 | +0.0325 |
| Holder inside diameter | 1.0000 | 0.9965 | −0.0035 |

I subtracted the puck diameter from the holder’s inside diameter to find the actual clearance.

**Actual clearance = 0.9965 − 0.9925 = 0.0040 in**

The puck measured larger than designed, while the holder opening measured slightly smaller. This reduced the total diameter clearance from 0.0400 in in CAD to 0.0040 in in the printed parts.

For the 1.00 in nominal fit, the handbook RC2 clearance range is 0.00030–0.00120 in. My measured clearance was above this range, so these measurements do not show an RC2 fit.

## Sliding and Locking

The sliding fit was very inconsistent. Sometimes the puck slid into the holder smoothly and felt nice, while other times it was extremely tight and difficult to move. The parts fit together, but the movement was not consistently smooth.

While I was showing the design to someone, one of the locking arms snapped from careless handling. This was also partially my fault because I made the arms too thin to handle much force. Thankfully, the ring holder still works without the locking mechanism.

If I repeated this project, I would test several clearances and check for rough spots or uneven dimensions before changing the final design. I would also make the locking arms thicker so they could handle normal use without snapping.

I did not sand the parts. Fagan wanted to see parts that could work without needing much post-processing, similar to what would be needed when producing larger quantities.

## Lessons Learned

The biggest challenge was figuring out the SLA machine and choosing the clearance. I spent a lot of time learning the printing process and trying to understand how the printed dimensions would compare with my model. The inconsistent fit showed me that adding clearance does not always make the parts move smoothly.

I also learned that the locking arms needed to be thicker. They fit into the holder, but they were too easy to damage. Next time, I would make the arms stronger and adjust the openings to match.

Before printing another finished design, I would print a small test with several clearances. I would check the fit in different positions to see whether the movement stays smooth. This would give me actual results from the printer and resin before choosing the final dimensions.

I spent approximately 10 hours on this assignment, mostly figuring out the SLA machine and the tolerances needed for the parts to fit together.

## Resources

- [Protolabs — Design Rules for 3D Printing](https://github.com/user-attachments/assets/189c5234-ea54-4c02-97db-ffb416705d54)
- [Formlabs — Introduction to Post-Curing Prints](https://formlabs.com/support/Introduction-to-Post-Curing-Prints/)
- Machinery’s Handbook — Table 8a: Running and Sliding Fits
