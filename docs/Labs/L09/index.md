# Lab #9 - Laser Cutter

Group: Brendan Spinner & Ethan Minton

## Objective

Our objective is to design, laser-cut, assemble, and document a parametric construction kit using Taguchi’s Robust Design principles to engineer reliability. Utilizing calculated, repeatable joint connections that account for machine kerf and material thickness variation across an entire sheet. 

## Analyze


### Thickness Determination

Due to a short time constraint, I decided that it would be best for me to attempt to print a quick 1 inch by 1 inch square to utilize for calculations over the weekend so that I can easily document and calculate all the values I need before coming in on Monday to reduce issues. I will explain how I modeled the square and everything afterwards to ensure everything was carried out. Nevertheless, I actually used the square to measure the first and second measurements, with the remaining measurements being sourced from the sheet itself. I did this to attempt to reduce possible changes that a cut could perform on the square and its measured thickness.

<img width="4032" height="3024" alt="IMG_0274" src="https://github.com/user-attachments/assets/3091686b-77c7-43c2-a2cd-08e3177c7c20" />

| Measurement # | Thickness (in) |
| :--- | :--- |
| Location 1 (square) | 0.1080 |
| Location 2 (square) | 0.1085 |
| Location 3 (sheet) | 0.1075 |
| Location 4 (sheet) | 0.1060 |
| Location 5 (sheet) | 0.1060 |
| Mean | **0.1072** |

To find the average, we add these measured values and divide by 5. This gives us a thickness of 0.1072 inches, which we will use when creating our CAD model and determining certain constraints.

### Kerf Determination 

To test for the Kerf of the laser cutter, I had to create a quick 1 inch by 1 inch sketch in Inkscape that will be able to laser cut the print and grab our measurements with the true sides. 

<img width="1916" height="1141" alt="image" src="https://github.com/user-attachments/assets/325a6715-91ec-4c29-abca-0862ba730616" />

I do want to mention that I did change a setting that I will keep throughout this project, which is called the "Geometric Bounding Box," which generally means that the sketches and models inserted will have the laser line exactly where they were sketched. The "Visual Bound Box" attempts to reduce the Kerf by sketching the outside of this box, which can help reduce this value but makes the estimated values of the sketches larger than they actually are. This can be confusing for design, so I opted for geometric to simplify my understanding. 

<img width="698" height="88" alt="image" src="https://github.com/user-attachments/assets/94f4590b-15d7-4bd4-9af6-38900816da7e" />

To elaborate on what Kerf actually is, it is the width of material that is completely burned away by the laser beam when it follows the cut path. Because the laser burns away this material on both sides, it results in larger fits for holes created than they were modeled to be and tabs/edges becoming smaller than they were intended to be.

I then had the assistance of one of the Lab volunteers with the printing process. Disappointingly, I was not able to get any screenshots of the setup due to this fact, although any significant steps for setup will be documented within the final kit once it is printed. I was however able to catch a video of the print as proof that I was the one to print the square used later. 

<video src="https://github.com/user-attachments/assets/85034c2d-c6f7-4c07-b778-f15f9fbc84d0" controls style="max-width: 100%;">
</video>

The measured values for the nominal 1 inch by 1 inch square were 0.9965 inches for the x-axis and 0.9950 inches for the y-axis. Subtracting these from the nominal values and averaging them gives us a calculated Kerf of roughly 0.00425 inches. This value will be utilized when designing the tolerance and our clearance test.

<img width="4032" height="3024" alt="IMG_0276" src="https://github.com/user-attachments/assets/e96a8b94-4610-4243-8a70-f8cb2c692870" />

<img width="4032" height="3024" alt="IMG_0275" src="https://github.com/user-attachments/assets/8e4d97e1-8e55-4514-8f66-951b9482be1a" />

| Direction / Axis | Nominal Value (in) | Measured Value (in) | Calculated Kerf (in) |
| :--- | :--- | :--- | :--- |
| X Axis | 1.0000 | 0.9965 | 0.0035 |
| Y Axis | 1.0000 | 0.9950 | 0.0050 |
| Mean | - | - | **0.00425** |

### Clearance Print 

When designing the clearance test, I was told by the same Lab volunteer that for simplicity, it would be best to use Fusion 360 as the CAD software for this assignment, as it has the least amount of issues when sending DXF files over to Inkscape, which I was completely fine for as it would allow for me to gain more versatility with more CAD software across different branches. 

I just began by creating a simple sketch on the Front surface. And creating 5 equally spaced slits between each of the protrusions; these sliters where set to be 0.30 inches wide, with them all being equalized with the equal constraint. They were also set to a height of 0.70 inches to allow for proper grip ability and easy insertion. I started with the middle constraint, setting it just to our thickness value of 0.1072 inches. 

<img width="1911" height="961" alt="image" src="https://github.com/user-attachments/assets/0272427c-32ba-4408-85ab-1b17ceea80c0" />

I then went to the right of the center and added a single increment of the KEFR variable: 0.00425 inches 

<img width="1911" height="963" alt="image" src="https://github.com/user-attachments/assets/71a52d70-f9db-4dbe-8915-f008f8109dae" />

Going right again to the edge, I then added the THICKNESS to 2 * KERF this was specifically to ensure a better base line to check if I need smoother or longer values for my tolerances. These 2 tabs represent the loose fits.

<img width="1912" height="962" alt="image" src="https://github.com/user-attachments/assets/745804cc-5c1e-4c9b-9e4c-4ea8e708865c" />


I did the same process on the left side, but instead of adding increments of KERF, I decided to subtract increments on this side to represent the tighter fits. This results in the completed Tolerance Test Model below.

<img width="1911" height="962" alt="image" src="https://github.com/user-attachments/assets/ad9ce619-65b5-4c07-b663-6021c1ef8c84" />

Before I uploaded the file to Inkscape, some of my peers told me to try making these fits to test a slot fit, which is what I had initially planned for my final design. I did this by adding a rectangular sketch to the top of the design, as you can see below. All other dimensions remained the same.

<img width="1917" height="966" alt="image" src="https://github.com/user-attachments/assets/8616b7d5-f5de-49f3-9407-2d78b96bfb27" />

Below is the parametric table I utilized for this process with the KERF having 0.00425 inches set to its value, and the THICKNESS being set to 0.1072 inches.

<img width="1498" height="592" alt="image" src="https://github.com/user-attachments/assets/a40a2cd3-bbb7-4981-afac-e31f0556a2d8" />

I then uploaded the file with a DXF file into Inkscape so that the file could be cut.

<img width="1917" height="1137" alt="image" src="https://github.com/user-attachments/assets/7d16f234-237d-4c8c-ae2b-30512e89b34c" />

Video of Cutter being used for Clearance Test.
<video src="https://github.com/user-attachments/assets/e8d18941-5655-46ba-84d5-ab8c84648247" controls style="max-width: 100%;">
</video>

### Clearance Test 

Once the part was obtained, I first started with testing. The first test: the Positive 2 KERF was way too loose; this was an observation I guessed based on how the cutter operates, but nonetheless.
<img width="4032" height="3024" alt="IMG_0358" src="https://github.com/user-attachments/assets/eeb332fe-391e-4122-ad1f-27a342f46a4b" />

The second test was the Positive 1 KERF; this was also observed to be too loose, similar to the prior. 

<img width="4032" height="3024" alt="IMG_0360" src="https://github.com/user-attachments/assets/5ce2e1a4-6bdd-48f4-8db6-ae22dd25017d" />

The third test was neutral, with no variable acting on it to adjust the KERF; this was tighter than the previous 2 but still would slide easily with just a bit of wobbling, which is not optimal for our wanted part.

<img width="4032" height="3024" alt="IMG_0359" src="https://github.com/user-attachments/assets/3a3f17db-59f8-40ba-89bb-823c77173f12" />

The fourth test had a negative 1 KERF; this was actually the first fit that I would consider pretty optimal for a slot fit, though I would consider it slightly too loose for a good slot fit, as it would still slide out at certain angles of wobble.

<img width="4032" height="3024" alt="IMG_0361" src="https://github.com/user-attachments/assets/7571d899-9771-4313-b925-8aae45e0e514" />

The fifth test had a negative 2 KERF; this was the final test, and I would consider it also pretty optimal for a slot fit if you do not want the part to be taken apart easily. The fit is extremely tight, and although it would be possible to slot and utilize, the fact it is incredibly difficult to remove led me to make an engineering decision. 

<img width="4032" height="3024" alt="IMG_0362" src="https://github.com/user-attachments/assets/a4b2d3c0-22d7-4a07-91aa-b5d1db8a1690" />

Once I had removed the part from the cutter, I found that, in the negative, the 1 KERF was too loose a clearance and that 2 KERF was too tight a clearance, meaning that when it came to programming the final design of the model, I would pick to have our clearance value be roughly 1.5 KERFs to hopefully accommodate the needed clearance.

## Design 

### Unique Part 1

Created sketch on top surface and Set length to "LENGTH2," which was set to 4.50 inches. 
<img width="1916" height="967" alt="image" src="https://github.com/user-attachments/assets/9e3c0fc5-b64d-45ba-9d3f-1a68ba22ed30" />

set width to "WIDTH" which was set to 0.60 inches.

<img width="1911" height="963" alt="image" src="https://github.com/user-attachments/assets/efb1d7de-8be0-4bca-a7b6-ac11a5e10a39" />

I then created 2 rectangles on the interior of the sketch and equalized their side lengths to each other to ensure that any change in the model will parametrically affect the other.

<img width="1915" height="967" alt="image" src="https://github.com/user-attachments/assets/3eaf31ae-d372-4010-832b-46e19f9f8652" />

I then constrained the top of these rectangles with "(WIDTH/2) - (KERF + CLEARANCE)". I included the clearance variable so that any alterations I have to make on Monday can be easily added to the model without directly changing the "KERF" variable. This currently has resulted in a length of 0.296 inches.

<img width="1907" height="965" alt="image" src="https://github.com/user-attachments/assets/13262a1e-3715-4391-863e-1a1f7108fb63" />

I then constrained the height of the smaller rectangles using "THICKNESS - (KERF + CLEARANCE)" for the same reasons. This equates to a value of roughly 0.103 inches.  

<img width="1916" height="952" alt="image" src="https://github.com/user-attachments/assets/1b757759-766d-4b15-8320-aa31fb6dd92e" />

I then constrained each of their lengths from the opposing side to be "LENGTH1" or 4 inches. 

<img width="1915" height="960" alt="image" src="https://github.com/user-attachments/assets/a31af7df-06ee-439e-8c8f-e47a253caaf5" />

I finally aligned the smaller rectangles to the center of the main rectangle, utilizing the collinear constraint.

<img width="1912" height="957" alt="image" src="https://github.com/user-attachments/assets/09020d75-3968-472d-b4e8-a2855a969879" />


### Unique Part 2
Creating the second shape with LENGTH1 4 inches

<img width="1915" height="962" alt="image" src="https://github.com/user-attachments/assets/fd62d537-97e2-4733-af4d-4f826c41ffb5" />

Create the exterior slots to have the same length using the equal constraint and assign it to the value "WIDTH / 2 + ( KERF + CLEARANCE )" giving it a value of 0.307 inches

<img width="1910" height="957" alt="image" src="https://github.com/user-attachments/assets/95300ca1-1a22-425f-8cbb-2faf590104e3" />

I then constrained the width to the sides of the slots, with "WIDTH/4" using the equal constraints, giving a value of 0.15 inches.
<img width="1912" height="958" alt="image" src="https://github.com/user-attachments/assets/4b583cae-b3cf-473b-a345-350101aa7418" />

I constrained the exterior slot height with "WIDTH/2", 0.30 inch.
<img width="1917" height="967" alt="image" src="https://github.com/user-attachments/assets/ed4595c8-a2b3-464c-ae78-10d582a21e4a" />

I then created 2 45-degree rotated rectangles and distanced them by "WIDTH/2"; I equalized their distances, giving 0.30 inches.
<img width="1910" height="961" alt="image" src="https://github.com/user-attachments/assets/9c8b15c3-4393-4e86-8e93-9aee40f67e52" />

I constrained their heights on the main part to be "WIDTH/3" at 0.2 inches.
<img width="1906" height="962" alt="image" src="https://github.com/user-attachments/assets/aa6c8b51-23be-4399-a71d-2b4b308245a9" />

I then set the height of both the rectangles to "THICKNESS - ( KERF + CLEARANCE )", roughly 0.1 inches.
<img width="1905" height="960" alt="image" src="https://github.com/user-attachments/assets/4f870ff6-a232-4775-95a3-9ec23a28bd00" />

I then constrained the length of the rectangles to "WIDTH / 2 - ( KERF + CLEARANCE )",0.293 inches
<img width="1901" height="958" alt="image" src="https://github.com/user-attachments/assets/dcb95592-fb14-42b6-9e75-4c34fba989fb" />

### Unique Part 3

I first started by creating the slot extruded part in the sketch with "WIDTH / 2 + ( KERF + CLEARANCE )", giving it a dimension of 0.307 inches.
<img width="1917" height="956" alt="image" src="https://github.com/user-attachments/assets/2d98a916-84c6-426c-a67c-b6c3d6dbbc3b" />

I then created the length of the slot extruded part with "WIDTH / 2", at 0.30 inches

<img width="1911" height="952" alt="image" src="https://github.com/user-attachments/assets/f601959c-9d5b-4f72-8ffa-4a44593b6505" />

I creating a 45 degree angled line and gave it the length of "LENGTH3" at 3.75 inches.

<img width="1915" height="962" alt="image" src="https://github.com/user-attachments/assets/4b52fbc5-c3ed-476c-a033-1060386e213a" />

I created a 90 degree angled line and set it to the "WIDTH" variable at 0.6 inches

<img width="1916" height="963" alt="image" src="https://github.com/user-attachments/assets/7b575b91-f782-4f16-b431-c242c63bc7d4" />

I created another 90 degree turn and created a line that when all the way down until we reached the base of the slot extrusion. I then created a vertical line downward and completed the part.

<img width="1912" height="961" alt="image" src="https://github.com/user-attachments/assets/fa1aefc6-d653-4cb3-9956-0acf76a5f8e7" />

I then created a separate sketch to remove from the Unique Part 3, I first constrained the top end by 0.8 inches downward. And then the width of the sketch to be set to "WIDTH" at 0.60 inches.

<img width="1910" height="968" alt="image" src="https://github.com/user-attachments/assets/b1a5f5e4-780e-4da4-9f5e-81b3bf44eddd" />
With the sketch of the part then having a aligned line at a length of "WIDTH/3" at 0.2 inches. And created a angle line at 45 degress from the length of part to connect up with a horizontal line.

<img width="1912" height="962" alt="image" src="https://github.com/user-attachments/assets/fc506a1a-fdd5-415e-9239-ce78ab40fa4d" />

### Parameter Table

Once I tested the slots, I found that subtracting one kerf left the fit slightly loose, while subtracting two kerfs made it difficult to take apart. I decided to use 1.5 times the measured kerf for the final design. In Fusion 360, I set CLEARANCE to KERF / 2, so adding it to one full kerf gave me a total adjustment of 0.006375 in. I then used THICKNESS − (KERF + CLEARANCE) to subtract that adjustment from the measured sheet thickness of 0.1072 in, giving me a CAD slot width of about 0.1008 in.

<img width="1485" height="592" alt="image" src="https://github.com/user-attachments/assets/94db9005-e739-4858-ad19-8ffbb7e0804e" />

### Before & After 
I first set THICKNESS to the measured sheet thickness of 0.1072 in, which gave me a slot width of about 0.1008 in.

<img width="1502" height="597" alt="image" src="https://github.com/user-attachments/assets/9c1feec3-a3e2-4956-ae1a-db93cff7a907" />
<img width="1907" height="957" alt="image" src="https://github.com/user-attachments/assets/e1d74c9c-ff3d-4cd8-8c23-8b2ffafa4b8e" />

I then changed THICKNESS to 0.1200 in to see how the slot would update. With the kerf and clearance settings kept the same, the slot width increased to about 0.1136 in. I then changed the thickness back to 0.1072 in for the final design.

<img width="1498" height="595" alt="image" src="https://github.com/user-attachments/assets/fdcff53c-4522-425e-9ca7-7567cdf3f0fd" />
<img width="1887" height="947" alt="image" src="https://github.com/user-attachments/assets/85b7f6d2-512a-4583-9da0-355c5643bb51" />

## Manufacturing

I arranged the eight pieces in Inkscape with the four straight pieces stacked above the four angled pieces. I moved the pieces closer together so the layout would take up less of the wood sheet. I then used the bed camera in the Epilog Dashboard to make sure the entire layout was on the sheet before cutting.

<img width="1917" height="1140" alt="image" src="https://github.com/user-attachments/assets/239ab1d5-0b0a-40a9-b480-7a8c5d6ae2a2" />

| Setting | Kerf coupon | Fit coupon | Final cut |
| --- | --- | --- | --- |
| Laser cutter (name or number) | Little_Boy_SFL_LA-5 | Little_Boy_SFL_LA-5 | Little_Boy_SFL_LA-5 |
| Material type | Wood sheet | Wood sheet | Wood sheet |
| Nominal thickness | 1/8 in | 1/8 in | 1/8 in |
| Measured thickness (mean) | 0.1072 in | 0.1072 in | 0.1072 in |
| Speed | 20% | 20% | 20% |
| Power | 100% | 100% | 100% |
| Frequency or PPI (if applicable) | 20% frequency | 20% frequency | 20% frequency |
| Number of passes | 1 | 1 | 1 |
| Focus method and how you confirmed it | Used the metal focus rod to set and check the height manually. | Same as kerf coupon | Same as kerf coupon |
| Air assist on? Exhaust on? | Both on with valves fully open. | Same as kerf coupon | Same as kerf coupon |
| How you set origin and alignment | Used the bed camera to position the cut layout on the sheet. | Same as kerf coupon | Same as kerf coupon |

<img width="1917" height="1130" alt="image" src="https://github.com/user-attachments/assets/f4178995-51cc-4910-bc77-944e3ffaec0d" />

I ran the cut with the air assist and exhaust fully open. The smoke cleared quickly while the laser was running, and all eight pieces cut through easily. The edges were mostly smooth with a few small imperfections. The cut edges were darker brown, but there were no major burn marks. I was able to use the parts as they came off the cutter without sanding or cleanup. So no sanding or cleanup was required to smooth the edges.

<img width="4032" height="3024" alt="IMG_0364" src="https://github.com/user-attachments/assets/a60f5779-8d3e-4cc9-a2c9-1bc7b8f6cc05" />
<img width="3024" height="4032" alt="IMG_0277 (2)" src="https://github.com/user-attachments/assets/8a577732-a80a-49f4-b82e-2eaedd25a4ee" />

I connected the two copies of Part 1 and the two copies of Part 2 to form a square base. I then inserted the four angled copies of Part 3 into the slots near the middle of the Part 2 pieces. The angled pieces meet at the center above the base, giving the finished kit a pyramid shape.

<img width="4032" height="3024" alt="IMG_0363 (1)" src="https://github.com/user-attachments/assets/99c336ea-13c4-4cc1-b1a2-45d9a6dbfc47" />

### Process Research 

Laser Cutting is a manufacturing process that utilizes a high-powered laser to vaporize a material into specified shapes. Often used for industrial manufacturing applications, as they become more affordable to utilize, schools and small businesses are able to access them and use them for projects. Most laser cutters operate by directing the output of the high-power laser through optics that focus the laser beam. The Super Fab Lab specifically utilizes a CO2 Laser that is able to both cut and engrave into the material. It is a viable manufacturing process as it is able to perform its process extremely quickly with uniform and accurate precision. 

Unlike FDM priniting Laser cutting is an extremely  quick process only taking roughly a minute or 2 to completely even the most complex loads given to the machines. FDM printing takes hours upon hours to complete more complex and scaled prints. But this is primarily due to the geometric limits of how each of these manufacturing systems functions, with Laser Cutting operating only within a 2-dimensional plane in which it cuts the parts out of we are limited by the geometries and shapes we can achieve working in flat 2d planes. While FDM operates in a 3-dimensional environment that is able to create complex and rounded geometries simply with the operations it is given. We can work around this with the Laser cutter, but not to the extent that FDM handles it.

## Lessons Learned

| Date and time | Time spent on task | Step | What happened | Decision or change made |
| --- | --- | --- | --- | --- |
| Oct. 23, 2026, 4–8 PM and Oct. 26, 2026, 11 AM–8 PM | 5 hours | CAD modeling | I worked on the kit design and learned how to model the fit coupon in Fusion 360. | I asked my teammate and other students for help, then restarted the coupon model. |
| Oct. 23, 2026, 4–8 PM | 2 hours | Coupon testing | I measured the kerf and tested five slot widths. | I chose a slot adjustment of 1.5 times the measured kerf based on the two closest fits. |
| Oct. 26, 2026, 11 AM–8 PM | 2 hours | Final cut | I laid out and cut all eight parts from one wood sheet. | I moved the parts closer together to use less of the sheet. |
| | 8 hours | Documentation | I put together the screenshots, tables, and explanations. | I added before-and-after screenshots showing how changing the sheet thickness updated the slot width. |
| | **17 hours** | **Total** | | |

The part I struggled with most was modeling the fit coupon. I was still getting comfortable with Fusion 360, and I initially misunderstood what the assignment was asking me to show with the coupon. After talking with my teammate and other students, I restarted the model and set up the five slots around the measured sheet thickness. Testing those slots gave me a better idea of how much to subtract in CAD to get the fit I wanted.

<img width="1911" height="962" alt="image" src="https://github.com/user-attachments/assets/4f16c616-d329-489d-aaad-222439135700" />

<img width="1917" height="966" alt="image" src="https://github.com/user-attachments/assets/9092d246-838b-4910-befe-1594c6d32c1e" />

I used one nominal 1/8 in wood sheet that was about a foot and a half across. I used calipers to measure the sheet and kerf coupon, Fusion 360 to model the parts, Inkscape to arrange them, and the Epilog laser cutter and metal focus rod to set up and make the cuts. No sanding or other cleanup was needed.

### Reflections

Measured Vs Expected. I expected the kerf to be around 0.005 in, and I measured an average of 0.00425 in. The wood was labeled 1/8 in, but I measured an average thickness of 0.1072 in. If I had used 0.125 in in the slot equation, the slot would have been drawn 0.0178 in wider, which could have made the joints loose. Using my original kerf estimate with the same equation would have made the slots slightly tighter.

Taguchi’s quality loss. The angled Part 3 pieces fit into the slots in Part 2 and held the pyramid together, but one of the joints had a little more play than I wanted. My target was a snug fit that I could still take apart by hand. Taguchi’s quality loss function says that the loss increases with the square of the distance from the target. For one kit, a little play might only make the pyramid wobble. Across thousands of kits, that same issue could lead to more complaints or parts needing to be remade.

Real product example. A flat-pack plywood stool can use tabs and slots to connect the seat and legs. If the slots are too wide, the stool could wobble. If they are too narrow, the customer might have to force the parts together and could damage a tab.

What I would change. If I had one more cut, I would make four more copies of Part 3 and redesign Part 2 to hold angled pieces on both sides. That would let me try making a diamond shape like the one from The Sims.
