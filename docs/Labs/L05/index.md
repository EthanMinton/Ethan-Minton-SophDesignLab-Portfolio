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

As stated previously, I wanted to gather real data so that I could iterate and understand how the PLA from our specific printers behaves with their mechanical processes. To note, the math performed above was done simultaneously with this print.  When performing a rough sketch of the math previously, I had assumed a much higher force would be applied, which had led to a much larger length of around 2.4 inches. Once printing this rough sketch of the snap-fit, I immediately noticed a problem when applying force to the part that had caused it to permanently deform. If we look at the formulas we had calculated above, length has a great impact on the amount of bending stress. I found that, when calculating the stress applied was roughly 6500 PSI with the assumption of only 5 lbf being applied. This was well over the limit of Stress allowed at 1,873.1 PSI.

<img width="1367" height="997" alt="image" src="https://github.com/user-attachments/assets/755d042f-16fd-4f5c-9a45-061b308fe24d" />


<video src="https://github.com/user-attachments/assets/58a5f42c-ebf1-4d15-baf9-7bca7458cf26" controls style="max-width: 100%;">
</video>

Due to the deformation, the Clip would begin to easily slip out of the housing and render the build relatively useless. This is where I decided to make the assumption that the force applied was much lower to reduce the amount of length and bending stress applied to our build. This would result in the calculations you find above. 

## Parametric Design

### Primary Clip

The first model we worked on was the Primary model, or the Clip. This model was designed to take into account the failures of the prototype while applying the mathematics found above. Starting with defining the basic dimensions we selected and assigning them to variables. 

These include the thickness variable defined by T = 0.14 inches. This particular variable was used to define the width of each of the 2 beam compoents, using the equal constraint; any change to T will impact both of the beams simultaneously.

<img width="1275" height="725" alt="image" src="https://github.com/user-attachments/assets/9f2ae42c-fb61-43b5-aec2-365f66bfa26a" />

The next variable that was selected was the max deflection defined by DEFL = 0.08 inches. This variable was selected to define the width of the triangle lips found at the end of each of the 2 components, with the dimensions equalized: any alteration to DEFL will impact both beams' lips.

<img width="1367" height="997" alt="image" src="https://github.com/user-attachments/assets/5b517157-4848-4b19-a604-534302b46dd4" />

The variable for Base was assigned to the variable B a value of 0.5 inches; the value was applied to the extrusion of the sketch so that any altercation to the base will then result in the entire sketch model being redefined.

<img width="1362" height="997" alt="image" src="https://github.com/user-attachments/assets/f91149e5-a608-4faa-86d6-c156e940515d" />


Going back to the initial sketch, I then defined the Length of the model with a combination of all of the defined variables: Base B = 0.5 inches, thickness T = 0.14 inches, the max deflection DEFL = 0.08, and the variable F_T = 1.5 lbf for the transverse force applied. All combined into "((DEFL * E * B* (T^3))/(4 * F_T))^(1/3)" allows for any change in the values listed above to directly alter the length upon regeneration. As proven by our previous calculations. The length was found to be roughly 1.84 inches long. Similar to the thickness, this length was applied using the equal constraints to both the left and right components, so any changes to the variables derived would change both lengths simultaneously.

<img width="1367" height="1002" alt="image" src="https://github.com/user-attachments/assets/972fce68-56ff-4c3d-94ff-02eaca0cc9f9" />

The next handful of dimensions were not defined parametrically mainly due to the fact that no other dimension of the model relies on their values, such as how the length of the model relies on the base, thickness, the max deflection, the Modulus of Elasticity, and the transverse force applied. Meaning they could be changed without much issue or external effect. The special case for this is the distance between the beams of the model. Being defined as 1.58 inches. This value was selected directly by the width of the mouth for the Secondary Housing model, this will be elaborated more within the next section but if these models were modeled within the same design, they would almost directly be defined parametrically with each other. 

<img width="1367" height="1000" alt="image" src="https://github.com/user-attachments/assets/a0e6faf6-ea80-4c44-a0eb-0ab7074d2390" />

The next step of the part model was defining the connection found at the very bottom of the model that would allow for easy application of force when needed. With the highlighted lines below all being equalized, the situation where the set value of 0.25 inches is altered will impact the whole structure. 0.25 was selected primarily for being a good medium to grab onto without being to obstructive. If you wanted more of an area to grab onto, you could alter the value to, for example, 0.4 inches, giving a better area to apply the force. For the simplicity of printing, I decided to keep our value at 0.25 inches.

<img width="807" height="187" alt="image" src="https://github.com/user-attachments/assets/a3afcf81-cb5a-4f26-82fd-e172145a1237" />

<img width="793" height="190" alt="image" src="https://github.com/user-attachments/assets/02423d3f-0b67-4cb4-bccb-c950715f7b9e" />

The next 2 parameters were selected to define the piece of our part that would help deflect, such as the "sharpness" of the triangle and its length. Each of these parameters was equalized to the other side so that any changes would be uniform. The value selected for the length was 0.2 inches, and the gap from which the angled edge meets the end of the length of the beam was 0.05 inches. These values were defined this way based on an observation from the prototype print that such a large value for the gap between the angled line and the length would result in the part getting stuck and not sliding into place when force was applied; I opted to shrink this value to 0.05 inches to allow for easier ability to push through the part.

<img width="1360" height="997" alt="image" src="https://github.com/user-attachments/assets/024e605f-7582-434d-8300-622697954fa4" />

Once the model had been extruded, the final edit that I made was the rounding of all of the inner corners where the beams meet the base piece. I dimensioned it to a value of radius of 0.25 primarily because of how quickly and noticeably it was with the prototype. 

<img width="1360" height="1001" alt="image" src="https://github.com/user-attachments/assets/89681958-67dc-4b76-b279-493535380957" />

### Secondary Base

The Base is the simpler box structure that the clip portion is supposed to press into. I didn't think that it should be overengineered so I kept it simple. 

I first began by creating a simple rectangular sketch, constraining the width of the feature with the constraint of SEC_WID, which is set to the value of 2 inches. I then constrained the length to the variable SEC_LEN, which was set to 0.5 inches. Initially, I wanted to set the length to be longer to mimic more a what a clip would actually look like, but opted for a shorter length for print time.

<img width="1365" height="827" alt="image" src="https://github.com/user-attachments/assets/d5900072-e0f2-4506-85bf-0860e2376876" />

<img width="1370" height="1000" alt="image" src="https://github.com/user-attachments/assets/40f9da8f-7c7e-4cdc-96a5-955cd7936ea5" />

Once the Sketch had been completed, I then decided to constrain the height to a variable called SEC_HI, which was given the value of 1 inch.

<img width="1368" height="998" alt="image" src="https://github.com/user-attachments/assets/e086ce95-6bb2-4ac5-b3ff-0b05a514df6a" />

As seen in the bottom left, I then created a new sketch on the surface of the box previously modeled. I constrained the height of the box with a relation of 2 variables, BASE, which is the same base value we used within the Primary Clip, which was 0.5 inches, and TOL, a tolerance variable that was applied to our dimensions here. This variable was set to 0.02 inches; the value was derived based upon our previous print with the tolerance test, where we found roughly 0.02 inches of tolerance is needed for consistent ability to pass through. This results in a true height of 0.52 inches.

<img width="1917" height="1057" alt="image" src="https://github.com/user-attachments/assets/e2f1d845-ac44-4bde-9070-66ddd1e775e9" />

The next was the width of the mouth of this rectangle. Which was defined by, as seen again in the corner, MOUTH + TOL. MOUTH was a variable that equates to the previous value of the distance between the 2 beams found on our print; it was set to 1.6 inches. TOL, which equates to 0.02 inches, was added to this value to allow for our print to have a fit that wasn't considered too tight to be used. This equates to a total length of 1.62 inches.

<img width="1917" height="1055" alt="image" src="https://github.com/user-attachments/assets/1c33d062-060b-4776-b15e-d4a151270673" />

The 2 distance dimensions found on the top and bottom of the models utilize specialized equations that take into account the full length of the Secondary Part subtracting the length of the hole within its middle. Once subtracted it is then divided by 2. This gives us a product that will automatically center the hole within the model if any specific variable is changed or altered. For the horizontal constraint, the parameter is (SEC_WID - (MOUTH + TOL))/2, which equates to roughly 0.19 inches. The verticle constraint parameter is (SEC_HI - (BASE + TOL) )/2, which equates to roughly 0.24 inches.

<img width="1917" height="1052" alt="image" src="https://github.com/user-attachments/assets/646db02f-d66b-4858-ac67-3eee58bccda8" />

<img width="1916" height="1057" alt="image" src="https://github.com/user-attachments/assets/639588b0-bd08-4b23-8107-ec274b8b1b89" />

Once the sketch was completed, I then dimensioned it so that it extrudes through the material entirely.

<img width="1916" height="1055" alt="image" src="https://github.com/user-attachments/assets/45148fa1-0850-43ca-892c-a16331dd40b4" />

The designs are found below.

<img width="1366" height="996" alt="image" src="https://github.com/user-attachments/assets/58af8a5a-2633-402a-a2f7-fba9d4b8e1ec" />

<img width="1361" height="997" alt="image" src="https://github.com/user-attachments/assets/2ce3fdc5-d98c-449c-bc5f-64873a84940b" />


## Pre-Processing 

### Research 
To initialize, I did some research on 3D printing of Snap-Fits, using a found source from Protolabs Network (linked within resources). Stating that you should avoid ever printing the snap-fit cantilever beams in the vertical/Z-direction, as it introduces anisotropy where the material begins to behave differently depending on the direction of applied load. When printed vertically, tensile bending stresses pull directly across layer interfaces, relying on weak inter-layer adhesion and increasing the risk of delamination. This is supported by research on FDM mechanical properties, which demonstrates that parts printed flat (horizontal orientation) yield significantly higher flexural strength than those printed vertically. Because bending loads place the outer surfaces of the beam under maximum tension, orienting our flexure flat on the build plate ensures these stresses act parallel to continuous filament lines rather than pulling layer bonds apart, aligning directly with literature recommendations for parts under bending load.

### Settings 

Due to time constraints and availability to print, I opted to print the first attempt of the parts separately. While simultaniously keeping the same constraints and settings for simplicity.

Keeping our basic layers and perimeter settings to the basics, with the most notable being the perimeters. I set the perimeters to be at a value of 3, as I felt that when performing the snap-fit, the snapping action and motion would almost definitely result in impacts on the surface that could damage or chip away if repeated enough times. To avoid this, I set it to 3 to give our model enough structure to handle it.

<img width="1617" height="493" alt="image" src="https://github.com/user-attachments/assets/781e6e0a-e16e-43bd-ba23-4d50c3fc0f8e" />

I left the skirt perimeter setting active, mainly because I think it gives a cool look while printing, but it also provides our print with a funnel check to ensure that the printing base is level and that the nozzle is primed to be able to print the actual model. A final test to prevent failure. This was especially important, as this time around I was not able to observe the prints throughout the entire process to prevent any major failures from damaging the print or the final model.

<img width="1630" height="181" alt="image" src="https://github.com/user-attachments/assets/151651c4-c9cd-4839-9ba3-3f8fd4087ca4" />

For infill, I chose the Gyroid setting because it's a print infill pattern I've wanted to use for a while, ever since it was explained in class. I decided to set this at 30% to give the print more structure and to prevent any major plastic deformation that would result from usage. 

<img width="1637" height="97" alt="image" src="https://github.com/user-attachments/assets/758057b7-ad33-4609-9941-2b8c053b9cc3" />

For Supports, there was a setting called "Don't Support Bridge" that had to be disabled; otherwise, supports couldn't actively support the bridges. Once disabled, I was then allowed to have bridges with supports. 

<img width="1575" height="31" alt="image" src="https://github.com/user-attachments/assets/1d788780-aef5-4c71-9252-f2742fc3093b" />

To elaborate on Supports, I selected to use the "Everywhere" setting as I wanted to see how the computer would place them itself. Changing the support structure to be organic. The assignment required us to use supports within our print, and I felt that if I had used supports for the Primary clip, it could lead to imperfections that could cause fractures to become more likely when in use. The supports for the Secondary housing unit would benefit it greatly based on its orientation. As the model standing upright would create a large bridge overhang that could be misprinted without supports. As mentioned prior, there is very little tolerance for the gap between, so any major imperfections could result in a print being rendered completely useless and would require a reprint. Its important to utilize supports to their full potential.

<img width="1593" height="26" alt="image" src="https://github.com/user-attachments/assets/f4c4a043-24b2-4452-83ef-103884677b68" />

### Slicing 

Uploading the Primary Clip to Prusa, we are given a rough time estimate of 25 minutes; no supports needed. 

<img width="1917" height="1048" alt="image" src="https://github.com/user-attachments/assets/4db4dec4-146c-4d37-85eb-37662c16d951" />

Primary G-Code:

<img width="880" height="76" alt="image" src="https://github.com/user-attachments/assets/da649aae-7f7d-4454-87c4-edaf0a427bec" />

Uploading the Secondary Clip to Pruse, we were given a rough time estimate of 45 minutes; supports were added under the bridge and surrounding the model. 

<img width="1886" height="1050" alt="image" src="https://github.com/user-attachments/assets/be1ca8b7-5c3c-4d90-a605-4416c01b95bb" />

Secondary G-Code: 

<img width="892" height="75" alt="image" src="https://github.com/user-attachments/assets/91099e6c-4f04-4fad-90a4-2de133c7fa58" />

## Printing

### Primary 

<img width="4032" height="3024" alt="IMG_5923" src="https://github.com/user-attachments/assets/8989ed65-2eca-4614-8285-f8a4ef8be6c2" />

<video src="https://github.com/user-attachments/assets/e53d8611-d5c4-4081-8c23-c4079d37fe4a" controls style="max-width: 100%;">
</video>

<img width="4032" height="3024" alt="IMG_5928 (1)" src="https://github.com/user-attachments/assets/7b542696-66d9-4803-90cf-46202e5321de" />

Once the primary had completed its print, it took roughly 32 minutes 27 seconds. It was printed without any cause for major issues. 

### Secondary 

<img width="4032" height="3024" alt="IMG_5935" src="https://github.com/user-attachments/assets/87822f85-813f-4cc5-a020-bcd9227db589" />

<img width="4032" height="3024" alt="IMG_5936" src="https://github.com/user-attachments/assets/2e9f0060-5b12-4a52-bc55-c3b86b6162c1" />

Unlike the Primary, the secondary had a lot more issues that caused it to drag further than intended. As the plate for the printer kept requiring readjustments, the print took way longer than expected, at 1 hour and 14 minutes. Another note is that I was unable to obtain a video, as the print issues and then a required class I had to attend left me unable to access the print lab in being able to get a video of the active print.

## Testing and Iteration 

Once the models had been printed, I began to test them. I immediately found a new issue with the current updates to the models themselves. The primary clip deflection value, the value that determines the height of the lip of the model, was too short despite calculations that, when any amount of axial force was applied to the end of the clip, the Primary and Secondary would detach from each other through slippage. I had noticed this same issue with the Prototype model, although I assumed that the issue was due to the plastic deformation of the model and not the actually deflection value itself. This resulted in me changing the variable of the deflection to DEFL_ID, which was set to 0.14 inches in order to iterate and combat the failure of the math previously calculated.


<img width="1360" height="991" alt="image" src="https://github.com/user-attachments/assets/010f1f89-c4c8-440b-b26e-709379a86753" />

The new resulting clip looked like the one below.

<img width="1367" height="1002" alt="image" src="https://github.com/user-attachments/assets/51407036-5180-4f1b-bc7e-4fec33c9e1dd" />

Printing this model again with the same Prusa settings gave us the result we were looking for. The clip was able to withstand axial force applied without slippage and was able to resist any major plastic deformation.

The video below is a showcase of all 3 of the primary clips being performed. The left clip was the prototype clip with the shorter deflection value, no round constraints, and longer length. Observe the plastic deformation applied and how easily it is pulled apart from the secondary part. The middle clip was the first version of the real design, with the shorter deflection value, the round constraints applied to reduce permanent deflection, and the shorter length. Observe how, despite its redesign, it continues to be pulled apart easily. The final clip is the final design with the iterated deflection of 0.14 inches, the same length as 2, and the added rounds. Observe its ability to resist the axial force and keep the overall clip together.

<video src="https://github.com/user-attachments/assets/27dd4cf0-6b03-4739-b9a6-6370d9224fb9" controls style="max-width: 100%;">
</video>


## Lessons Learned 

Honestly, the biggest lesson learned here is that the math doesn't always check out properly and that our assumptions can be completely incorrect and throw off our real-world applications. You can't assume everything to an accuracy without very deep and intensive research. I knew that primarily my assumption for the Material properties of PLA would very likely be considered not entirely accurate for the calculations I was performing. This is why I decided to print the Prototype model to get more of a general understanding of how the PLA used for the print behaves specifically.

The Prototype ended up proving this point almost immediately. The model permanently deformed when force was applied, which showed that the assumptions I had made for the material and geometry did not represent the real behavior of the part very well. Even though the calculations gave me values that I could use to design the part, they did not account for every factor that would affect the actual printed component. Things such as the actual PLA being used, the printing process, layer bonding style, geometry, and the way the force was being applied all played a role in how the part behaved. This showed me that calculations should be used as a starting point for a design rather than being treated as a guarantee that the part will work.

Another major lesson I learned was how important iteration is in engineering. After creating the first actual design based on the calculations, I found that the clip could still slip out of the housing even though the stresses were below the calculated allowable stress. This was another example of how something can appear to work mathematically but still have a problem when it is physically tested. I had originally assumed that the deflection value I calculated would provide enough engagement between the two components, but the physical test showed that this assumption was incorrect. I changed the DEFL variable from 0.08 inches to 0.14 inches, which increased the height of the lip and allowed the final design to stay engaged with the housing.

I also learned that due to the slippage, parametric design becomes much more useful when a design needs to be changed multiple times. Because the important dimensions were controlled by variables, I did not have to completely remodel the part when I discovered the problem with the first design. I could change the variable and allow the model to update itself. This made the iteration process much easier and showed me why parametric modeling is useful for engineering applications where the first design is unlikely to be perfect.

Time spent, including all of the Printing times, is roughly 12 Hours 30 minutes. 
## Resources 

[https://www.hubs.com/knowledge-base/how-design-snap-fit-joints-3d-printing/](https://www.hubs.com/knowledge-base/how-design-snap-fit-joints-3d-printing/)

[https://www.matweb.com/search/DataSheet.aspx?MatGUID=ab96a4c0655c4018a8785ac4031b9278&ckck=1](https://www.matweb.com/search/DataSheet.aspx?MatGUID=ab96a4c0655c4018a8785ac4031b9278&ckck=1)


