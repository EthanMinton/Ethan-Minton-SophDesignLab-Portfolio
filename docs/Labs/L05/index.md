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


## Analyze

Mention deflection in a real-life test. and saw the slippage due to the rounded edges of prints.

## Decide


## Communicate

