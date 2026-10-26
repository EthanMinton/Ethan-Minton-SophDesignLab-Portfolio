# Lab #9 - Laser Cutter
Brendan Spinner & Ethan Minton
## Objective

Our objective is to design, laser cut, assemble, and document a parametric construction kit using Taguchi’s Robust Design principles to engineer reliable. Utilizing calculated, repeatable joint connections that account for machine kerf and material thickness variation across an entire sheet. 

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

### Clearance Determination 

When designing the clearance test I was told by the same Lab volunteer that for simplicity it would be best to use Fusion 360 as the CAD software for this assignment as it has the least amount of issues when sending DXF files over to Inkscape, which I was completely fine for as it would allow for me to gain more versatility with more CAD softwares across different branches. 

I just began by creating a simple sketch on the Front surface. and creating 5 equally spaced slits between each of the protrusions; these sliters where set to be 0.30 inches wide with them all being equalized witht he equal constraing. They were also set to a height of 0.70 inches to allow for proper grip ability and easy insertion. I started with the middle constraint, setting it just to our thickness value of 0.1072 inches. 

<img width="1911" height="961" alt="image" src="https://github.com/user-attachments/assets/0272427c-32ba-4408-85ab-1b17ceea80c0" />

I then went to the right of the center and added a single increment of the KEFR variable: 0.00425 inches 

<img width="1911" height="963" alt="image" src="https://github.com/user-attachments/assets/71a52d70-f9db-4dbe-8915-f008f8109dae" />

Going right again to the edge, I then added the THICKNESS to 2 * KERF this was specifically to ensure a better base line to check if I need smoother or longer values for my tolerances. These 2 tabs represent the loose fits.

<img width="1912" height="962" alt="image" src="https://github.com/user-attachments/assets/745804cc-5c1e-4c9b-9e4c-4ea8e708865c" />


I did the same process on the left side, but instead of adding increments of KERF, I decided to subtract increments on this side to represent the tighter fits. This results in the completed Tolerance Test Model below.

<img width="1911" height="962" alt="image" src="https://github.com/user-attachments/assets/ad9ce619-65b5-4c07-b663-6021c1ef8c84" />

I then decided to upload the file to Inkscape so that it could be uploaded to the laser cutter.

<img width="1917" height="1140" alt="image" src="https://github.com/user-attachments/assets/bf00fc67-7068-4709-a875-ef58b9c693c9" />

FINISH LASER CUT AND MAKE DETERMINATIONS OF WHAT FIT

Below is the parametric table I utilized for this process with the KERF having 0.00425 inches set to its value, and the THICKNESS being set to 0.1072 inches.

<img width="1498" height="592" alt="image" src="https://github.com/user-attachments/assets/a40a2cd3-bbb7-4981-afac-e31f0556a2d8" />


REMIND FINISH ITERATION 

<img width="1917" height="966" alt="image" src="https://github.com/user-attachments/assets/8616b7d5-f5de-49f3-9407-2d78b96bfb27" />

<img width="1917" height="1137" alt="image" src="https://github.com/user-attachments/assets/7d16f234-237d-4c8c-ae2b-30512e89b34c" />

## Design 
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


SECOND SHAPE
Creating the second shape with LENGTH1 4 inches



<img width="1915" height="962" alt="image" src="https://github.com/user-attachments/assets/fd62d537-97e2-4733-af4d-4f826c41ffb5" />

REMIND CLEARANCE OF 0.001 INCH which chhanges everything.

<img width="1917" height="1140" alt="image" src="https://github.com/user-attachments/assets/239ab1d5-0b0a-40a9-b480-7a8c5d6ae2a2" />
<img width="1917" height="1130" alt="image" src="https://github.com/user-attachments/assets/f4178995-51cc-4910-bc77-944e3ffaec0d" />

## Communicate

