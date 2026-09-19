# Lab #5: Design a Snap Fit

## Objective

For this week's lab, we were assigned to create a snap-fit that considers factors such as mechanical properties, geometric considerations, tolerance management, and load-bearing requirements. Once calculated, we must create a parametric snap-fit model that can be physically printed for testing. If issues arrise we must iterate if possible.

## Assumptions

This week's lab requires several assumptions that we must make to create a snap-fit design that works as intended. This is where our issues first begin to arise. After researching the behavioral properties of PLA plastic, I found that the Modulus of Elasticity and the Yield Strength both have great ranges of values attributed to the complex process that eventually makes up its production and determines these properties. Such as production grade, the quality of the printer being used, and even infill percentage. All details that make our assumptions much more difficult to detail without real-world testing. I decided to keep it simple with the assumptions here, as I expect to be making modifications to the model itself based on results found with the prototype.

The Value selected for the Modulus of Elasticity was 340,000 PSI (E = 340,000 PSI), a converted, rounded average for the listed value below of 2.35 GPa (340838.7 PSI). The value selected for Yield Strength was 6,555.7 PSI, the average listed below, converted from 45.2 MPa. The value for the yield strength will be divided by our safety factor of 3.5, providing a Strength allowed of 1,873.1 PSI.

<img width="1885" height="637" alt="image" src="https://github.com/user-attachments/assets/d98d86e4-e2fd-4f47-874e-41fb25b2be26" />

The next set of assumptions are the geometric assumptions that we are asked to make. These include the max deflection, the width, and the base of the feature. Respectively, the values selected were 0.08 inches for deflection, the width (or as I labeled it, thickness) of 0.14 inches, and a base of 0.5 inches.

The last assumptions made we with the assumptions of the force applied; these assumptions would determine the stresses that are applied to different parts of the components. The transverse load determines the bending stress applied to the parts, and the axial stress determining the axial stress and shear stress of the obstruction preventing the snap-fit from slipping. The transverse load applied was selected to be 1.5 lbf, mainly with needing to require adequate strength to "open" while not requiring more strength than the PLA could handle due to the bending stress. The axial force selected was the max 10 lbf, primarily due to the fact it should be able to easily withstand the force and any attempt to brute-force pull them away from each other.

## Calculations 

I want to preface this section by saying that most of the calculations are based on assumptions that are likely to not reflect most of how the actual nature of how the Snap-fit should actually perform, the biggest being the modulus of elasticity and the Yield Strength. Both of these values were provided in huge ranges that encompass an entire range of possibilities. To work around this, I planned on printing a prototype and iterating based on the results I find there.

### Solving for Length 

We are asked to solve for the length of our Snap-fit based on our previous assumptions. I initially began by taking the deflection max formula below and plugging in the 2nd Moment of Inertia and the Transverse force variables into the equation. Once completed, I then isolated the variable L to find the length that would be required. After isolating L, I plugged in all known values and assumptions and obtained a value of 1.84 inches.

<img width="820" height="493" alt="Math Scratch Paper (25)" src="https://github.com/user-attachments/assets/a4000d4d-a61d-4080-b06f-74ca4a63d0b9" />

## Solving for Stresses 

### Bending

The next set of calculations solves for the different stresses that will be applied to our snap-fit. As is known from Solid Mechanics, the greatest impact of stress often comes from bending applied to our structures. The fact remains true here: as we formulate the bending stress and solve with our now-known values, we find that the stress is calculated to be around 1,689.8 PSI, just under our limit of 1873.1 PSI.

<img width="820" height="482" alt="Math Scratch Paper (26)" src="https://github.com/user-attachments/assets/e302af4a-8406-4f21-ab6b-5e1b24f87cb4" />

### Axial 

This calculation is to measure whether or not the snap fit can properly take the applied load of 10 pounds of force being applied to its end in tension. I expected the part to be able to properly handle such stress, as the strength was considered extremely high for the max load to be applied. Another factor to note with axial loading is that the 10 lbf of force will be equally distributed to 2 sides of the clip, as both will be attached as 1 when the force is applied. Taking this into consideration for our calculations by halving the force, we find an axial stress applied at 71.43 PSI. 

<img width="820" height="183" alt="Math Scratch Paper (27)" src="https://github.com/user-attachments/assets/1847f598-7950-418a-b1a4-0a3c9d211ecb" />

### Shear 

This calculation is to measure whether or not the Snap fit can properly take the applied load of 10 pounds of force on the interface between the deflection triangle and the rest of the structure to be bent. Due to 2 of the interfaces being found on the model similar to our axial stress being applied, we also divide this value by 2. Note that the value of T_L is 0.12 inches. This value was grabbed from a rough sketch of the model I was working on simultaneously to determine the cross-sectional area of the interface. Once we plugged in our values we found the average shear stress to be roughly 83.3 PSI.

<img width="820" height="264" alt="Math Scratch Paper (28)" src="https://github.com/user-attachments/assets/5cdb3c92-7334-4798-9f71-95fad9332972" />

## Print Prototype - Eyeballed

As stated prior, I wanted to gather real data so that I could iterate and understand how the PLA from our specific printers behaves with their mechanical processes. To note, the math performed above was done simultaneously with this print.  When performing a rough sketch of the math previously, I had assumed a much higher force would be applied, which had led to a much larger length of around 2.4 inches. Once printing this rough sketch of the snap-fit, I immediately noticed a problem when applying force to the part that had caused it to permanently deform. If we look at the formulas we had calculated above, length has a great impact on the amount of bending stress. I found that, when calculating the stress applied was roughly 6500 PSI with the assumption of only 5 lbf being applied. This was well over the limit of Stress allowed at 1,873.1 PSI.

Remind: Image of original Clip model

Remind: Image showing Clip deformation of prototype

Remind: Video of Print

Due to the deformation, the Clip would begin to easily slip out of the houser and rendered the build relatively useless. This is where I decided to make the assumption that the force applied was much lower to reduce the amount of length and bending stress applied to our build. This would result in the calculations you find above. 

## Parametric Design

### Primary Clip

The first model we worked on was the Primary model, or the Clip. This model was designed to take into account the failures of the prototype while applying our mathematics found above. Starting with defining the basic dimensions we selected and assigning them to variables. 

These include the thickness variable defined by T = 0.14 inches. This particular variable was used to define the width of each of the 2 beam compoents, using the equal constraint; any change to T will impact both of the beams simultaneously.

<img width="1275" height="725" alt="image" src="https://github.com/user-attachments/assets/9f2ae42c-fb61-43b5-aec2-365f66bfa26a" />

The next variable that was selected was the max deflection defined by DEFL = 0.08 inches. This variable was selected to define the width of the triangle lips found at the end of each of the 2 components, with the dimensions equalized: any alteration to DEFL will impact both beams' lips.

<img width="1367" height="997" alt="image" src="https://github.com/user-attachments/assets/5b517157-4848-4b19-a604-534302b46dd4" />

The variable for Base was assigned to the variable B a value of 0.5 inches; the value was applied to the extrusion of the sketch so that any altercation to the base will then result in the entire sketch model being redefined.

<img width="647" height="133" alt="image" src="https://github.com/user-attachments/assets/0ab08176-c004-49c1-bb44-aba1bb0b6640" />

Going back to the initial sketch, I then defined the Length of the model with a combination of all of the defined variables: Base B = 0.5 inches, thickness T = 0.14 inches, the max deflection DEFL = 0.08, and the variable F_T = 1.5 lbf for the transverse force applied. All combined into "((DEFL * E * B* (T^3))/(4 * F_T))^(1/3)" allows for any change in the values listed above to directly alter the length upon regeneration. As proven by our previous calculations. The length was found to be roughly 1.84 inches long. Similar to the thickness, this length was applied using the equal constraints to both the left and right components, so any changes to the variables derived would change both lengths simultaneously.

<img width="1367" height="1002" alt="image" src="https://github.com/user-attachments/assets/972fce68-56ff-4c3d-94ff-02eaca0cc9f9" />

The next handful of dimensions were not defined parametrically mainly due to the fact that no other dimension of the model relies on their values, such as how the length of the model relies on the base, thickness, the max deflection, the Modulus of Elasticity, and the transverse force applied. Meaning they could be changed without much issue or external effect. The special case for this is the distance between the beams of the model. Being defined as 1.58 inches. This value was selected directly by the width of the mouth for the Secondary Housing model, this will be elaborated more within the next section but if these models were modeled within the same design, they would almost directly be defined parametrically with each other. 

<img width="1367" height="1000" alt="image" src="https://github.com/user-attachments/assets/a0e6faf6-ea80-4c44-a0eb-0ab7074d2390" />

The next step of the part model was defining the connection found at the very bottom of the model that would allow for easy application of force when needed. With the highlighted lines below all being equalized, the situation where the set value of 0.25 inches is altered will impact the whole structure. 0.25 was selected primarily for being a good medium to grab onto without being to obstructive. If you wanted more of an area to grab onto, you could alter the value to, for example, 0.4 inches, giving a better area to apply the force. For the simplicity of printing, I decided to keep our value at 0.25 inches.

<img width="807" height="187" alt="image" src="https://github.com/user-attachments/assets/a3afcf81-cb5a-4f26-82fd-e172145a1237" />

<img width="793" height="190" alt="image" src="https://github.com/user-attachments/assets/02423d3f-0b67-4cb4-bccb-c950715f7b9e" />

The next 2 parameters were selected to define the piece of our part that would help deflect, such as the "sharpness" of the triangle and its length. Each of these parameters was equalized to the other side so that any changes would be uniform. The value selected for the length was 0.2 inches, and the gap from which the angled edge meets the end of the length of the beam was 0.05 inches. These values were defined this way based on an observation from the prototype print that such a large value for the gap between the angled line and the length would result in the part getting stuck and not sliding into place when force was applied; I opted to shrink this value to 0.05 inches to allow for easier ability to push through the part.

<img width="1360" height="997" alt="image" src="https://github.com/user-attachments/assets/024e605f-7582-434d-8300-622697954fa4" />

MENTION ROUND and how the prototype needed something to reduce perminate deformation.

### Parametric Design 
## Analyze

Mention deflection in a real-life test. and saw slippage due to the rounded edges of prints.

Mention Changing deflection variable to DEFL_ID for deflection iteration 
## Decide


## Communicate

