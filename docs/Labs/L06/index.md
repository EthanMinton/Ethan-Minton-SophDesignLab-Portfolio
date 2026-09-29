# Lab 6 – Design Fits for an Artifact

## Objective

Create a snap fit that can snap fit around a selected object in class. I decided to select the Motor seen below, creating a snap fit design around the end of the shaft so it is able to properly transfer torque to a different system. This was considerably difficult, as PLA plastic is known for having very little yield strength when handling bending. Applying the proper pressure to the shaft without plastic deformation can be considerably difficult. The primary goal is to design the snap fit with the capability to attach itself to the shaft using pressure applied without that same pressure deforming our snap fit.

<img width="4032" height="3024" alt="IMG_5997" src="https://github.com/user-attachments/assets/3ae817a5-9d9e-4868-9ab5-7a3a246823e2" />

### General Idea Sketch 
<img width="569" height="907" alt="Math Scratch Paper (30)" src="https://github.com/user-attachments/assets/c4254f01-3f78-4e75-8ed8-4f7357bd7f75" />


## Parametric Design

### Preplanning 

To preplan, I decided that before actively modeling the design, I wanted to grab some general geometric constraints of the motor itself to make informed decisions that could be utilized when designing the constraints. Starting with the diameter of the bulb at the end of the shaft, I found it to have a diameter of 0.6255 inches. The next measurement performed was the diameter of the inner portion of the shaft at exactly 0.47 inches. The last measurement that I grabbed was the height of the bulb; the reason I grabbed this value was so that the snap fit could snap around this section to increase its grip on the shaft.

<img width="3024" height="4032" alt="IMG_5999" src="https://github.com/user-attachments/assets/7641d9c2-4319-4eaa-ac4e-66ec1aae28b5" />
<img width="3024" height="4032" alt="IMG_6001" src="https://github.com/user-attachments/assets/f29ce9ca-22e4-4f20-8475-a7841e6a7858" />
<img width="3024" height="4032" alt="IMG_6005" src="https://github.com/user-attachments/assets/26395bac-d152-4c85-9b03-b18e923d540d" />

To note, I initially utilized the Calipers in class but found that when applying a second measurement to the motor, the values were extremely different to my original measurements. I decided to utilize my electronic calipers, which had just had their battery replaced, which gave much more accurate and consistent measurements.

### General Sketching Shape

While noting that I will be utilizing the Revolve tool within SolidWorks, I finally decided to make the transition due to some personal grievances. I created an axis that will be used to revolve around; this axis is found where the Front and Right intersect. 

<img width="1917" height="967" alt="Screenshot 2026-09-28 163718" src="https://github.com/user-attachments/assets/a9728162-bfb5-45e6-bceb-4114ab04de61" />

I started by creating a rough general sketch in the design; this was mainly to get a shape I could properly constrain. To note the important geometry, the triangle in the bottom sketch is for the press fit to slide into the motor, and the small notch just above it is the lip that prevents the press fit from pressing any further into the motor. This was designed to give it the rigidity that would be required for what the objective asks for.

<img width="1906" height="992" alt="image" src="https://github.com/user-attachments/assets/5a15b79b-2163-4739-8968-e4eff8b19e96" />

To begin constraining, I first began to utilize the previously recorded geometric constraints of the motors, defining the deflection triangle height by the distance from the Shaft diameter divided by 2 for the radius.This resultedg in a value of 0.2350 inches away from our axis. 

<img width="1918" height="885" alt="image" src="https://github.com/user-attachments/assets/be140229-fb02-4de5-9c9f-019ddbb0e12c" />

The next constraint performed was the gap between the deflection triangle and the lip stopper found above it. This gap is defined by the measured height of the bulb, which was 0.2965 inches. 

<img width="1915" height="883" alt="image" src="https://github.com/user-attachments/assets/76d63262-72f6-42cf-bd8e-19101c106bab" />

The last of these sets is the distance from the flat surface of the gap between the 2 previously mentioned geometries; this used the measured bulb diameter divided by 2 to obtain the radius. This results in a value of 0.3128 inches, defining how far the snap-fit and the motor should snap together. 

<img width="1917" height="881" alt="image" src="https://github.com/user-attachments/assets/302cdb79-3ef7-4bda-8433-e178b6e3e1ba" />

I want to note that these values are without any tolerances initially; this is primarily because a core concept for this snap fit is that it needs to be tight enough to properly grasp the shaft and transfer applied torque. If any iterations are applied to improve the design, they will be mentioned and applied to the model to ensure success. I just wanted to note that this is supposed to be extremely tight to apply pressure properly.

The step of the model is to define our geometric assumptions to calculate the length of the model. Starting with the thickness or the width of the beam, I initially chose to define the thickness as 0.15 inches. I assigned it to both dimensions, as you see in the screenshot below. I want to preface that assigning this dimension was extremely frustrating, as I attempted to make them both equal to each other, but every troubleshooting step altered something else. I spent roughly 25 minutes on this until I just decided to constrain both with the thickness value; it equates to the same parametric models when altered or regenerated. This value was selected to not require an overly thick model that would be too bulky when in use. 

<img width="1916" height="840" alt="image" src="https://github.com/user-attachments/assets/82d93b5f-eeb0-498a-aef3-c50541d2f4b7" />

The Base of the model is not a constraint that is defined by the predetermined geometry, with it being roughly the circumference of the cylinder divided by 4; the reason for the division will be elaborated on later. But the way we find the radius of the model is just by adding the bulb's diameter and the thickness of the model. When multiplied by Pi divided by 2, we find that the base is 1.22 inches.

To calculate the length, we were required to make a couple of more assumptions, such as the Modulus of Elasticity, which I assumed to be roughly around 200,000 PSI. This is based on the previous assignment, where I found that the 340,000 PSI was a measure that overestimated its Modulus. It repeatedly gave a length way over what was actually able to be bent without plastic deformation. I selected a reduced value to prevent this issue. If more information is gathered from any test prints, it will be noted for future projects. Deflection was defined by the difference between the bulb and shaft diameters divided by 2; due to using a revolve feature, this is the best way to find this value, which equated to 0.08 inches. The final variable to assume for the length is the force applied; similar to the previous project, I assumed the force to be 1.5 lbf, a very small value that could be realistically applied by a human finger.

The equation below was used previously to calculate the length of a snap-fit, written out as "= ( ( "BASE" * "ELONG" * "THICK" ^ 3 * "DEFL" ) / ( 4 * "FORCE" ) ) ^ ( 1 / 3 )". This equation takes all the previously mentioned values and equates to a length of 2.2 inches.

Now, before I input this length, I want to mention the addition of an offset for the length. If our calculated value of length really means the distance that is required to bend our deflection value, meaning we must consider an additional length within our sketch to create an assumed rigid body that the "beam" will attach to and bend with. I was primarily concerned when deciding this value that the part could break into 2 if any force was applied that would cause deflection. I decided to set this value at 0.5 inches and added it to our calculated length to create the true length of the sketch.

<img width="1916" height="1010" alt="image" src="https://github.com/user-attachments/assets/1a2fd430-d36b-4833-897a-b6f9ed7be44c" />

Once fully defined, I then revolved the sketch around our originally created axis to form the product below.

<img width="1917" height="1016" alt="image" src="https://github.com/user-attachments/assets/b093298b-9f6b-4dc4-baf6-ed66391f5bc8" />

### Cut Extrusions

The next step of the model was to perform 2 cut extrusions that will give our model flexibility to be properly snap-fitted. Create 2 identical sketches below that are centered using the midpoint constraint tool with an assigned width of 0.2 inches and a height of the calculated length of 2.2 inches. This value for length is used here, as this determines what in our model actually flexes. 

<img width="1917" height="1011" alt="image" src="https://github.com/user-attachments/assets/7b1f98e3-dbf2-49ab-8b39-d6399ee40a1d" />

Once each of these sketches was created, they were then extruded through all in both directions to ensure that no part of the model that wasn't wanted was left. This is the reason why we divided the circumference by 4 within our calculation for the base, as each of the beams was divided into 4 sections by the double cut extrusion. The base variable was not used directly anywhere other than to calculate the length of the model. 

<img width="1917" height="1012" alt="image" src="https://github.com/user-attachments/assets/264069b2-0e0d-449f-94cb-c72566f3413a" />

Note that I decided not to include screenshots of the other sketch and cut extrusion of the other gap; it is the same with the same values and constraints. This is just to prevent any bloat; if further inspection is needed, you can easily find the CAD model within the resources.
### Finalized Model

**Finalized CAD model for Prusa.**
<img width="1916" height="1012" alt="image" src="https://github.com/user-attachments/assets/6ad4e7a7-8869-4e46-a061-4563fa36a8aa" />

**Finalized CAD Parameters and Variables**
The list of variables below is the whole collection of parameters used when parametrically modeling our design. Each has a short attributed description describing what it is and how they were derived. To note, the Tolerance variable is currently unused, as for my hypothetical snap fit to function correctly, it must be a tight fit. If iterated, the tolerance variable will be used as needed, whether to shrink the model or increase it. The engineered allowance was therefore based on allowing the snap-fit arms to deflect over the larger 0.6255-inch bulb while returning toward the smaller 0.47-inch shaft diameter after installation. Rather than adding a large dimensional clearance, I chose to rely on the calculated 0.08-inch deflection so the part could maintain contact with the shaft and transfer torque. The tolerance parameter was left available in the model so it can be adjusted after physical testing if the initial fit is too tight or too loose.

The main values that changed during the design process were the measured motor dimensions and the assumed modulus of elasticity. The motor dimensions were remeasured using electronic calipers after inconsistent measurements were obtained with the classroom calipers, while the modulus of elasticity was reduced from the previously used 340,000 psi assumption because it produced an unrealistically long snap-fit as previously tested. If the initial print is found to contain a failure, I will decide to iterate these variables to ensure that the model is properly scaled.


<img width="1815" height="267" alt="image" src="https://github.com/user-attachments/assets/46f7f9ae-6ed0-4c46-9180-12ff8275cba4" />

**Uploading to PrusaSlicer **

By saving the model in SolidWorks as a STEP file, I am able to transfer the CAD model over to the slicer software. As previously stated, this allows for highly accurate models to be transferred over into PrusaSlicer, giving us better overall prints.

<img width="940" height="72" alt="image" src="https://github.com/user-attachments/assets/98e64e2b-1817-41bc-80ac-8556c627be1c" />

## Preprocessing

PLA Plastic Utilized from 3D Printer

Utilizing Prusa Slicer, I began to configure my settings for the Print. First ,I began by inserting the model into Prusa. Initially, I wanted to have the model print vertically, standing up. Primarily because I wanted to prevent any complex supports that might be difficult to remove or damage the model itself. But I opted to print it horizontally for the overall strength benefit that comes with the layer boundaries being parallel to the length of the beams. The placement was considered to be in the middle of the plate to achieve maximum accuracy with the printer itself, avoiding any of the outer edges. The overall size is 0.9255 inches in the x direction, 2.7005 inches in the y direction, and 0.9255 inches in the z direction. 

<img width="1917" height="1125" alt="image" src="https://github.com/user-attachments/assets/90baa600-23a0-4fdf-9e43-54c2ccc07f4a" />

Configuring the Basic Settings: I decided to set the perimeter value to 3, similar to all previous lab experiments. I did this because I wanted to utilize the infill pattern while also having enough thickness within the wall that any friction or rubbing from the motorwon'tt easily chip or break the surface of the print itself. If it is too thick,nk the surface could chip easily,ily exposing the infill beneath; eath if it was too thick, it could reduce its ability to bend and properly function as a snap fit. With a 0.4 mm nozzle, the perimeter of 3 provides a 1.2 mm wall thickness, enough material around the outside of the snap-fit while still allowing the flexible sections to bend.

<img width="1612" height="192" alt="image" src="https://github.com/user-attachments/assets/f65188dd-b9fa-427b-a9fc-28b54ebbde05" />

Once we set our perimeter value, we moved on to setting the infill pattern and percentage, utilizing the Gyroid pattern at 30% infill. I chose these constraints similar to the previous lab, as it gave positive results when tested. Enough area to bend and succeed without having plastic deformation that would ruin the overall design.

<img width="1638" height="100" alt="image" src="https://github.com/user-attachments/assets/96dfaa21-39b7-40c4-bf82-885c0d80f191" />

The layer height was set to 0.3 mm, with the first layer being 0.35 mm; these settings were kept this way to primarily find the cost/benefit analysis based on time taken to print, compared to the benefit of accuracy. I can dedicate a lot more time to printing by reducing these values, but it will mean I will have to spend much more time on them. For the sake of a simple model, these values work perfectly fine.

<img width="1612" height="97" alt="image" src="https://github.com/user-attachments/assets/a12c1862-a53e-418a-be48-403bbf45ce29" />

The last major setting was the dedication to support materials; due to the selected orientation of print, my parts printed  horizontally, which causes a great overhang that would almost definitely fail if supports were not used. I decided to utilize the organic support structure, as I find it easiest to remove without much complication,n and due to how the model is structured, the process for removal is already going to be a very difficult issue to tackle. So the structure requires a lot of bulky supports to support the large overhang while also avoiding interactions with the rest of the model. Another setting altered was turning off the "Don't Support Bridge" setting, as it was preventing the supports from supporting the large overhangs that required them. 

<img width="1618" height="767" alt="image" src="https://github.com/user-attachments/assets/61e4d940-e007-41e3-b782-f2d4040a655e" />

Once sliced,d we are able to observe a few key details that PrusaSlicer was able to give. Such as the Build volume being found at 0.86 inches cubed, costing around 17.56 grams of filament. With a total of 78 layers of print,t it was estimated that print time would take around 1 hour and 7 minutes. Over 20% of the time was taken just for the support material alone. This makes sense, as in the image below we can see how much of an overhang there is and all of the structures that require supports.

<img width="1897" height="1117" alt="image" src="https://github.com/user-attachments/assets/4d00880b-3b8a-4fe7-8e79-7c82bbb92be9" />

Once sliced, I then uploaded the G-code to the 3D Printer.

<img width="937" height="90" alt="image" src="https://github.com/user-attachments/assets/6073b360-b787-4163-995b-d87fad1fbfa5" />

## Print 

Using Printer Number 14 within the lab, a PRUSA CORE ONE 0.4 nozzle Printer. I uploaded the G-code and began the print.

Below you can find a photo of the Print at the Start, showing the base of the entire model with the structure and the support materials. I already knew that removing the supports would be difficult, but this wasn't a pretty sight to see. 

<img width="4032" height="3024" alt="IMG_6007" src="https://github.com/user-attachments/assets/2fd81f5a-9b4f-4fed-9ff5-2da8763514ee" />

The video shows a mid-state of the Print with the Printer printing the infill, the walls, and the supports. 

<video src="https://github.com/user-attachments/assets/326993e6-08b8-42d6-bca5-9342f4a7cde4" controls style="max-width: 100%;">
</video>

The final photo shows the final print with the model and support structure. 

<img width="4032" height="3024" alt="IMG_6009" src="https://github.com/user-attachments/assets/4bb3d61d-eb0e-44f9-8b6d-7350856a05f1" />


After all the heating, the print took 1 hour and 13 minutes to complete.

<img width="4032" height="3024" alt="IMG_6010" src="https://github.com/user-attachments/assets/475dcd49-0c8c-4754-a5dc-5262848aa0ab" />

## Postprocessing 

Once the model was removed I utilized 2 primary tools to remove the Support structure, this was the cutting pliers and the screw driver. Due to the orientation of the model, I was unable to remove the supports simply with my hands. Using the pliers, I was able to cut and reach the inner branches and push them out with the screwdriver. It took roughly 10 minutes to remove all supports, as I was afraid of breaking the model with the pliers. 

After some quick testing, the model worked exactly as expected; the lack of any tolerances to the measured values gave the model a great snap fit that allowed it to tightly grip the model without issue. When I spun the model, the motor shaft spun as well, which was exactly what I intended. If the situation did arise that required modification, I would have used the previously mentioned tolerance variable within the SolidWorks model to either take values away if our tolerances were too loose, or add to if our tolerances were too tight.



## Lessons Learned

Throughout this process, I learned a lot about how difficult it can be to design a snap fit when the material properties and measurements are not perfectly known. The first lesson I learned was how important accurate measurements are when designing a part that needs to fit directly onto another component. When I initially measured the motor using the calipers provided in class, I received values that were considerably different when I attempted to measure the same features again. Because of this, I decided to use my electronic calipers after replacing the battery, which gave me much more consistent measurements. This showed me that even a small difference in measurement can have a significant effect when designing a tight-fitting component.

Another major lesson I learned was how important properly setting up constraints in SolidWorks can be. One of the most frustrating parts of the design was attempting to make the thickness dimensions equal to each other. I spent roughly 25 minutes attempting different methods to make the two dimensions automatically equal, but each troubleshooting method I attempted caused another part of the sketch to change. Instead of continuing to waste time trying to force the dimensions to work, I decided to directly constrain both dimensions using the same thickness value of 0.15 inches. Although this was not the method I originally intended to use, it still created a fully parametric model because changing the thickness value would allow both dimensions to be changed consistently. This taught me that there can be multiple ways to create a parametric model, and sometimes the simplest method is more reliable than trying to force a specific constraint.

I also learned that the assumed material properties can have a major effect on the final design. I initially used a modulus of elasticity of 340,000 PSI based on the previous snap-fit assignment. However, I found that this value resulted in a calculated length that was much larger than what I believed would work based on the actual behavior of the PLA. Because of this, I reduced the assumed modulus to approximately 200,000 PSI. This was done because I wanted the calculation to better represent the behavior I had observed from previous prints and avoid creating a snap fit that would require an unrealistic amount of material to bend.

Another lesson was that designing for a tight fit requires a balance between flexibility and strength. I originally did not include a tolerance in the main dimensions because the purpose of the design was to tightly grip the motor shaft and transfer torque. Instead, I relied on the calculated 0.08-inch deflection of the snap-fit arms to allow the arms to move over the larger bulb of the shaft and return toward the smaller shaft diameter. After printing the part, this approach worked as intended. The snap fit was able to attach to the motor, and when I rotated the printed component, the motor shaft rotated with it. This showed me that the calculated deflection could be used as an engineered allowance rather than simply adding a large amount of dimensional clearance.

A lot of these lessons pertain directly to engineering principles and understanding of how they play out. It is always important to iterate based on past experiences and designs; the reason I was insistent on using PLA plastic for my print was that I already had experience with PLA when designing similar snap fits. I was even able to take my past knowledge and readjust previous mistakes, such as my assumption for the Modulus of Elasticity of PLA plastic. Recently, I struggled with how to properly parametrically model, but this assignment I feel like is my best for it. Taking the directly measured values of the Shaft and utilized them directly within the model and the calculations for the length. It felt like a genuine achievement and lessons to grow from.

Time Taken: 10 Hours and 30 Minutes

## Resources

