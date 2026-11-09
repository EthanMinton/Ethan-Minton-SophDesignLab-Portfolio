# Lab #9 - Laser Cutter

Group: Brendan Spinner & Ethan Minton

## Objective

Our objective is to design, laser-cut, assemble, and document a parametric construction kit using Taguchi’s Robust Design principles to engineer reliability. Utilizing calculated, repeatable joint connections that account for machine kerf and material thickness variation across an entire sheet. 

## Research 

Laser Cutting is a manufacturing process that utilizes a high-powered laser to vaporize a material into specified shapes. Often used for industrial manufacturing applications, as they become more affordable to utilize, schools and small businesses are able to access them and use them for projects. Most laser cutters operate by directing the output of the high-power laser through optics that focus the laser beam. The Super Fab Lab specifically utilizes a CO2 Laser that is able to both cut and engrave into the material. It is a viable manufacturing process as it is able to perform its process extremely quickly with uniform and accurate precision. 

Unlike FDM priniting Laser cutting is an extremely  quick process only taking roughly a minute or 2 to completely even the most complex loads given to the machines. FDM printing takes hours upon hours to complete more complex and scaled prints. But this is primarily due to the geometric limits of how each of these manufacturing systems functions, with Laser Cutting operating only within a 2-dimensional plane in which it cuts the parts out of we are limited by the geometries and shapes we can achieve working in flat 2d planes. While FDM operates in a 3-dimensional environment that is able to create complex and rounded geometries simply with the operations it is given. We can work around this with the Laser cutter, but not to the extent that the FDM handles it.


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
I first set CLEARANCE to half of KERF. This gave me a total adjustment of 1.5 times the kerf and a slot dimension of about 0.306 in.
<img width="1917" height="958" alt="image" src="https://github.com/user-attachments/assets/1bd085d0-45f1-4bd5-ac9e-6b02ecdb7543" />

I then changed CLEARANCE to equal KERF to see how the slot would update.
<img width="1497" height="597" alt="image" src="https://github.com/user-attachments/assets/1aee70c4-d8a8-4e60-a1ed-f1bf9e9d5af7" />

After making this change, KERF + CLEARANCE was equal to two kerfs. This increased the slot dimension from about 0.306 in to 0.309 in.
<img width="1915" height="957" alt="image" src="https://github.com/user-attachments/assets/00621004-7eb5-4612-ad3a-116ee2c38767" />


## Machine Setup
<img width="1917" height="1140" alt="image" src="https://github.com/user-attachments/assets/239ab1d5-0b0a-40a9-b480-7a8c5d6ae2a2" />
<img width="1917" height="1130" alt="image" src="https://github.com/user-attachments/assets/f4178995-51cc-4910-bc77-944e3ffaec0d" />

## Communicate

