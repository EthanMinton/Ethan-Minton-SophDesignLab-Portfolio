# Lab #9 - Laser Cutter

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

The measured values for the nominal 1 inch by 1 inch square was 0.9965 inches for the x-axis and 0.9950 inches for the y-axis subtracting these from the nominal values and averaging them gives up calculated Kerf of roughly 0.00425 inches.

<img width="4032" height="3024" alt="IMG_0276" src="https://github.com/user-attachments/assets/e96a8b94-4610-4243-8a70-f8cb2c692870" />

<img width="4032" height="3024" alt="IMG_0275" src="https://github.com/user-attachments/assets/8e4d97e1-8e55-4514-8f66-951b9482be1a" />

| Direction / Axis | Nominal Value (in) | Measured Value (in) | Calculated Kerf (in) |
| :--- | :--- | :--- | :--- |
| X Axis | 1.0000 | 0.9965 | 0.0035 |
| Y Axis | 1.0000 | 0.9950 | 0.0050 |
| Mean | - | - | **0.00425** |
## Decide


## Communicate

