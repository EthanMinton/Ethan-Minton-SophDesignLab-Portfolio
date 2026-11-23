# Final Project – [Topic]

## Objectives

# Part 1

### Spiral Design Process

The Spiral Design Process is a method to improve a design through a repeated cycle of planning, risk analysis, engineering, and evaluation. Through each cycle, we use what we have learned to improve the preceding iteration. The primary feature is to understand the biggest risk early, before cost ramps up in the design.

Planning - The Main Attribute for planning is to define the goals, requirements, possible solutions, and limits, such as the budget, cost, materials, and time available. Each iteration, this plan is updated to fit new needs and circumstances.

Risk Analysis - The main attribute here is to identify what could possibly prevent the design from actually working. In this stage, you should compare alternatives and use hand calculations, simulations, or smaller tests to reduce uncertainty. 

Engineering - The main attribute here is to develop the design using sketches, CAD models, calculations, and prototypes. In this stage, we build and test the design using the information gathered during planning and risk analysis.

Evaluation - The main attribute here is to compare the results to the original goals and requirements. We review what worked, what did not, and what needs to change. We then use feedback and test results to guide the next iteration.

For my own project, this process can help us make improvements with a clear purpose. We can identify the biggest risk, build a prototype to test it, and use the results to update the design. Through each cycle, we can document what changed and why. This helps us address problems early and improve the design before spending more time and money on the final version. I actually plan to create a tolerance test to iterate my sliding fit and ensure it works properly without having to completely commit to the design and still have a failing design.

### FDM Anisotropic 

FDM Anisotropy - Anisotropy means that a part has different mechanical properties depending on the direction it is loaded. FDM produces this behavior by depositing melted plastic in lines and stacking them into layers. The connections between these lines and layers are different from the continuous material along each printed line. This generally makes the part stronger along the printed lines and weaker when a force pulls the layers apart. This can be leveraged through different design orientations that provide better flexibility and reduce the likelihood of snapping under applied loads.

Prototype Performance - To elaborate more for our prototype, this means that print orientation can affect how much force the part can withstand. A feature loaded across the layers could separate before the same feature printed in another orientation. We need to consider where forces act and how those forces travel through the part when deciding how to print it. A top priority of my design is to have it operate in a way that forces applied in any direction our model could withstand, which means it will likely require a large amount of material.

Design Decisions - We can use this behavior to our advantage by placing the main tensile loads along the printed lines within the layers. To reduce its limitations, we can add rounded corners and reinforce areas where stress is concentrated. If one orientation does not work for the entire prototype, we could divide it into separate parts and print each in a better orientation. Increasing the number of walls can also improve strength, although it does not eliminate the directional behavior. The key component that will likely require a specific orientation is pins within these fits being printed vertically with greatly increase the chances of failure.

Materials and Process Parameters - Material selection should consider layer adhesion along with the strength needed for the prototype. PETG is one option to investigate because it is less prone to cracking and layer separation during printing than other typical 3D printing filaments. Nozzle temperature and cooling also affect how well the layers bond. Using a temperature within the material’s recommended range and avoiding excessive cooling can improve layer adhesion. These choices should be checked through testing with our actual print settings.

https://www.stratasys.com/contentassets/1a0cc7a8e7d14f29ac972189bfeade4c/dg_fdm_designconsiderationsfdmtooling_0718a.pdf

### SLA Shrinkage

SLA resin can shrink during printing and post-curing as the material becomes more tightly connected. Formlabs describes Grey V5 and Clear V5 as low-shrinkage resins, but the sources reviewed do not provide an exact curing-shrinkage percentage for either material.

For Grey V5, Formlabs reports typical XY dimensional tolerances of ±0.15% for features between 1–30 mm, with a minimum tolerance of ±0.02 mm. These results used 100 µm layers and five minutes of room-temperature post-curing. This describes final dimensional accuracy, not the amount of shrinkage. An independent study using Clear V5 also found that print orientation affected the final dimensions.

Grey V5
| Feature Size | Typical XY Dimensional Tolerance |
| --- | --- |
| 1–30 mm | ±0.15%, with a minimum of ±0.02 mm |
| 31–80 mm | ±0.2%, with a minimum of ±0.06 mm |
| 81–150 mm | ±0.3%, with a minimum of ±0.15 mm |

For our prototype, dimensional changes could affect how holes, shafts, and other mating parts fit together. We can print a fit coupon, measure it after washing and curing, and adjust the clearances based on the results. PreForm already compensates for expected shrinkage, so additional adjustments should address the remaining measured error.

https://formlabs-media.formlabs.com/datasheets/2401898-TDS-ENUS-0.pdf?utm

### Laser Cut Kerf

Kerf is the width of material removed by the laser during cutting. Without compensation, outside dimensions become smaller and holes or slots become larger. Kerf varies with the material, sheet thickness, focus, power, and cutting speed.

We can compensate by adjusting dimensions in CAD or applying a cutting-path offset in the laser software. From past experience a Kerf variation of around 1.5 your Kerf value on the component. This creates a tight sliding fit. Meaning increasing this value will create a looser fit and lowering this value creates a tighter fit. For our prototype, uncompensated kerf could create loose joints that move or pull apart. Excessive compensation could make assembly difficult or cause parts to crack. We can measure the actual sheet thickness and cut a fit coupon with several slot widths before cutting the final parts. The coupon should use the same material and cutting settings as the prototype. Thankfully with past efforts we are able to consider the information we gather to apply to future needs.

https://docs.lightburnsoftware.com/latest/Guides/Test-KerfOffset/

## Problem Selection

### Modular Storage 

Something that I have always wanted to create and design is a modular storage system that could be modified to fit a person's unique needs. Small items such as screws, electronic components, different parts, or even Lego can become mixed and difficult to find. Standard storage containers may have compartments that are too large or too small, which wastes space and makes organization difficult.

The problem I would like to solve is how to create storage that can change as the items being stored change. The modularity would be its strength in design, allowing different compartments and attachments to be printed out and utilized without replacing the entire system. This would be considered the simpliest in engineering decisions as it will all hingle on a single sliding fit connection that could be universal to the entire design. 

### Force Directional Change 

Another problem that interests me is how to change the direction of an applied force when there is limited space to move or pull an object. For example, lifting an object directly upward can be difficult if there is no convenient place to grip it or stand above it. This is actually a problem I have previously attempted to design a pulley to close my closet door, but I ran into the issue of not being able to use it easily, requiring a specific setup.

Outside of my door, a pulley system could allow a person to pull in a more accessible direction while moving the object in the direction needed. The design would need to keep the rope aligned, allow the pulley to rotate freely, and provide a secure mounting point. Depending on the pulley arrangement, the system could also reduce the force required to lift the object.


### Ball Bearing 

Another problem I would like to explore is how to support smooth rotation in a prototype when a standard bearing does not fit the available space. Purchased bearings come in specific sizes, which can require changing other parts of the design or waiting for the correct bearing to arrive.

A 3D-printed ball bearing could allow the dimensions to be modified around the needs of the prototype; especially if completed parametrically, the design could be modified and applied universally to all parts. The main challenge would be creating enough clearance for the balls to move freely while keeping them contained and limiting unwanted movement. This would require testing the fit, friction, and wear to determine how well the bearing works. This would likely be the most difficult of the 3 problems to complete, with the most testing being required to iterate the design.

### Selected Problem

#### Force Directional Change

I wanted to take another crack at the pulley system that I created and improve on the flaws I had with the original design. The primary reason I want to solve this problem is that I was disappointed in the work I was able to produce and the lack of versatility the pulley actually had. Having to print another version just to get the pulley to work was frustrating. I want to use what I learned from that experience to create a design that is easier to assemble, modify, and use.

The problem I want to address is how to change the direction of an applied force while allowing the pulley system to work in different arrangements. A pulley that only works with one mounting position or one specific setup has limited use. I would like to explore interchangeable mounting parts and different pulley sizes so the system can be adapted without redesigning and printing the entire assembly. Hopefully, this design is able to finally tackle the door that constantly wakes me up throughout the night.

This problem can be addressed using the manufacturing processes used in class. FDM printing would allow me to create the pulley and support components, while smaller fit coupons could be used to check clearances before printing the full assembly. SLA can be used to create the pin, with its smooth surface and 100% infill it is able to structurally hold up and allow for the pulley wheel to freely spin.

The goal is to create a pulley that rotates freely, keeps the rope aligned, and mounts securely.

## Video Describing Problem
NEED TO DO PROTO VIDEO

## CAD Design 

### Pulley Support CAD

I started by creating a rectangle on the Top Plane with dimensions of 4.50 in by 5.00 in. This established the overall size of the base for the pulley support.

<img width="1616" height="960" alt="Base sketch dimensions" src="https://github.com/user-attachments/assets/473bf258-59f2-4596-8caf-5853b2bb4c62" />

I then extruded the rectangle 0.35 in to create the base. This gave me a starting point for adding the mounting holes and the supports above it.

<img width="1616" height="956" alt="Base extrusion" src="https://github.com/user-attachments/assets/995ae45f-4e4c-4a74-8ee9-565bb1f7fc7f" />

I created four mounting holes near the corners of the base. The hole diameter shown is 0.10 in, with the centers positioned 0.30 in from the adjacent edges.

<img width="1617" height="953" alt="Mounting hole sketch" src="https://github.com/user-attachments/assets/e7531670-b24a-4334-b506-7cf9c883d315" />

I used a Through All cut to extend the holes through the base. These holes provide locations for fastening the support to another surface.

<img width="1615" height="957" alt="Mounting hole cut" src="https://github.com/user-attachments/assets/bbba9776-f172-4e70-820f-6c61b6853698" />

I selected the bottom face and used the Shell feature with a thickness of 0.25 in. This removed material from the underside of the base.

<img width="1612" height="957" alt="Shell settings" src="https://github.com/user-attachments/assets/e793077f-7657-45ad-9514-a4b88c563129" />

The underside view shows the recessed area created by the shell. Material remains around the outside edges and the four mounting holes.

<img width="1616" height="957" alt="Shelled underside of base" src="https://github.com/user-attachments/assets/2b86a597-4298-4627-bd63-5d2fc6acf32d" />

I sketched a second rectangle measuring 3.50 in by 5.00 in. I positioned it in the center of the base, leaving a 0.50 in mounting strip along each side.

<img width="1617" height="957" alt="Support body sketch" src="https://github.com/user-attachments/assets/2a92e28a-1c3b-426d-b4bc-8f21cbf34840" />

I extruded this sketch 3.50 in and merged it with the base. I started with a solid body so I could cut away material to create the shape of the pulley support.

<img width="1615" height="957" alt="Support body extrusion" src="https://github.com/user-attachments/assets/ab3f44de-eefe-4326-9b4e-bed87ec798c2" />

I sketched the sloped upper profile and a 0.62 in diameter hole for the pulley shaft. The center of the hole is 0.50 in below the top, and the slopes extend down 1.50 in from the top edge.

<img width="1616" height="957" alt="Upper profile and shaft hole sketch" src="https://github.com/user-attachments/assets/4993e327-834a-4986-8c22-5c6566d9465a" />

I used a Through All cut to remove the upper corners and create the shaft opening. Making these features in the same cut kept the profile consistent through the body.

<img width="1612" height="958" alt="Upper profile cut" src="https://github.com/user-attachments/assets/a26fea71-016d-4935-b8eb-a452893767e2" />

I then created a sketch to remove the center material and shape the two supports. The upper sections are 0.40 in thick with a 0.80 in gap between them. The lower sections widen toward the base.

<img width="1616" height="962" alt="Support spacing and tapered profile sketch" src="https://github.com/user-attachments/assets/36d56b4c-618c-4b85-afe8-19b56b5eab9b" />

I cut these profiles Through All to form the two separate uprights. This opened the space between them for the pulley while leaving wider sections where the supports connect to the base.

<img width="1616" height="958" alt="Cut forming the two supports" src="https://github.com/user-attachments/assets/10c41fb7-ef7a-4f66-8b75-9b2571023943" />

I added a 0.20 in radius fillet to the two inside edges where the supports meet the base. This rounded the sharp transitions to help reduce stress concentrations in these areas.

<img width="1611" height="962" alt="Base connection fillets" src="https://github.com/user-attachments/assets/09977098-9028-4f6a-9c88-9e03cff16f90" />

I sketched triangular openings in the side of the support to remove more material. The lower sketch spans 4.00 in, and the two upper triangular sections each have a horizontal dimension of 1.50 in.

<img width="1612" height="960" alt="Triangular cutout sketch" src="https://github.com/user-attachments/assets/305c7143-b96a-46ae-81fe-f8fc072457c8" />

I used a Through All cut to create the openings. This removed material from the solid side while leaving a frame around the cutouts.

<img width="1615" height="961" alt="First support cutout" src="https://github.com/user-attachments/assets/34c77618-42fc-4c6e-98d2-c444130ab7d3" />

I copied and pasted the cutout sketch onto the opposite support and used another Through All cut. This gave both supports the same opening pattern.

<img width="1616" height="960" alt="Cutout on the opposite support" src="https://github.com/user-attachments/assets/7ea1d60f-dee6-4223-9f96-e08a1d6904c8" />

This view shows the copied sketch on the opposite side. I positioned it using the same 0.50 in offset so the cutouts would line up between the supports.

<img width="1612" height="958" alt="Copied sketch positioning" src="https://github.com/user-attachments/assets/13b7677a-7d86-4aa7-a4a1-00f931ac4582" />

I added 0.05 in radius fillets to the selected edges around the support openings. These rounded the smaller sharp corners left by the cuts.

<img width="1617" height="961" alt="Small fillets around support openings" src="https://github.com/user-attachments/assets/82b3eae5-c4a0-45dc-a783-a26cd5a6d1af" />

I created a rectangular sketch across the center of the base between the two supports. This defined the area for a shallow recessed channel.

<img width="1616" height="956" alt="Base recess sketch" src="https://github.com/user-attachments/assets/a7d376be-6d3b-4c8b-bb48-82ab29aeedb0" />

I used a Blind cut with a depth of 0.10 in to create the recess. This removed a shallow section of the base without cutting all the way through it.

<img width="1615" height="962" alt="Base recess cut" src="https://github.com/user-attachments/assets/92076c05-2b5a-471c-98a3-68429ad97299" />

I then used the Draft feature to apply a 5-degree taper to four selected faces, using the Top Plane as the neutral plane.

<img width="1620" height="962" alt="Draft feature settings" src="https://github.com/user-attachments/assets/591d2beb-941f-4968-99e0-4544e629eb8d" />

This view shows the support after applying the draft. The selected faces now have a slight taper, while the triangular openings and shaft holes remain in place.

<img width="1616" height="958" alt="Support after applying draft" src="https://github.com/user-attachments/assets/f28e3f73-f322-464c-b3ac-bc8d294491f7" />

### Pulley Wheel CAD

I started by sketching the cross section of the pulley wheel on the Front Plane. The sketch includes a 0.32 in radius for the shaft opening and a groove that is 0.19 in wide and 0.50 in deep. The material on each side of the groove is 0.29 in thick.

<img width="1612" height="998" alt="Pulley cross section sketch" src="https://github.com/user-attachments/assets/f797aafb-6fbb-446b-889a-7b252835a120" />

I used the Revolve feature to rotate the sketch 360 degrees around the centerline. This created the circular wheel, shaft opening, and outer groove in one feature.

<img width="1616" height="957" alt="Pulley revolve" src="https://github.com/user-attachments/assets/a3adb08b-d58f-44ea-82ba-6fabdcbcd599" />

I added a 0.10 in symmetric chamfer to four circular edges around the rim. This removed the sharp edges along the outside of the wheel and the groove.

<img width="1615" height="958" alt="Pulley rim chamfers" src="https://github.com/user-attachments/assets/65314853-8b58-4f17-bb26-80bf6fc8bcc9" />

I then sketched three openings around the center of the wheel. Each opening spans 100 degrees, with an outer radius of 2.30 in and a radial length of 1.50 in. The material between the openings forms the three spokes.

<img width="1605" height="965" alt="Pulley opening sketch" src="https://github.com/user-attachments/assets/59784729-0781-4e51-9709-5b5701e92f0b" />

I used a Through All cut to remove the three sections. This reduced the amount of material in the wheel while keeping the center hub connected to the outer rim.

<img width="1616" height="955" alt="Pulley openings cut" src="https://github.com/user-attachments/assets/50ddd0ec-d6c5-4525-9d24-746cbd73f6ff" />

I created another sketch using two concentric circles around the shaft opening. These circles defined the area between the center hub and the outer rim for the next cut.

<img width="1615" height="961" alt="Recess sketch around the hub" src="https://github.com/user-attachments/assets/5c151c8c-978d-4f39-953a-b8abf1476235" />

I used a Blind cut with a depth of 0.20 in to recess this area and reduce the thickness of the spokes. I repeated the same sketch and cut on the opposite side so both sides had the same recess.

<img width="1617" height="956" alt="Pulley face recess" src="https://github.com/user-attachments/assets/47d31070-200d-4c55-a2dd-2d9ea84bc637" />

I added 0.30 in radius fillets to six edges where the spokes connect to the center hub. This rounded the inside corners to help reduce stress concentrations at these connections.

<img width="1612" height="956" alt="Spoke connection fillets" src="https://github.com/user-attachments/assets/0beab6b1-480c-4635-a1a1-65adc44f3730" />

This view shows the wheel after adding the cuts and fillets. The three spokes connect the shaft hub to the outer rim, and the groove runs around the outside to guide the rope.

<img width="1616" height="960" alt="Pulley wheel after cuts and fillets" src="https://github.com/user-attachments/assets/3f852bdd-314e-485d-93a1-c173893bf874" />

### Pulley Pin CAD

I started by sketching a circle centered at the origin with a diameter of 0.60 in. This is slightly smaller than the holes in the supports and wheel to leave clearance for assembly.

<img width="1616" height="956" alt="Pulley pin sketch" src="https://github.com/user-attachments/assets/e0edbcd3-9a7b-4180-8669-2820e0fd28c7" />

I extruded the circle 1.60 in to create the pin. This length allows it to pass through both supports and the pulley wheel.

<img width="1616" height="956" alt="Pulley pin extrusion" src="https://github.com/user-attachments/assets/a9928648-210b-494b-b90d-6cfbfdc98a83" />

This view shows the completed pin model. The pin will act as the axle for the pulley wheel, with the fit and rotation needing to be checked after manufacturing.

<img width="1620" height="955" alt="Completed pulley pin model" src="https://github.com/user-attachments/assets/73612dd4-7b42-4092-bd96-413330add1af" />

## PreProcessing

These settings will be used for all FDM prints in this project. I set both the layer height and first layer height to 0.20 mm.

<img width="1646" height="110" alt="Layer height settings" src="https://github.com/user-attachments/assets/1426aff6-0a9d-40eb-ae77-71b4278f526c" />

I selected 30% gyroid infill to provide internal support without making the parts solid. This also reduces the material used compared to printing with 100% infill.

<img width="1648" height="253" alt="Infill settings" src="https://github.com/user-attachments/assets/049ca562-c0eb-4dbc-8571-35e2bb431329" />

I set the skirt loops and brim width to zero, so neither will be generated. The draft shield is also disabled.

<img width="1666" height="327" alt="Skirt and brim settings" src="https://github.com/user-attachments/assets/faac9d5f-42a3-4b66-acdb-0883d8999191" />

I enabled automatically generated organic supports with an overhang threshold of 40 degrees. Supports are limited to the build plate, and no raft will be used.

<img width="1645" height="345" alt="Support settings" src="https://github.com/user-attachments/assets/cee87c03-7e60-4c8e-8147-7410a428c61d" />

The overall setup uses the modified 0.20 mm STRUCTURAL profile, Prusa PETG filament, and the Prusa CORE One printer with a 0.4 mm nozzle.

<img width="497" height="222" alt="Printer and filament settings" src="https://github.com/user-attachments/assets/1e1e2b1b-6952-42ac-baf6-2b234c1d0202" />

## Fit-Test

To check the fit between the pin, support structure, and pulley wheel, I modified the CAD models to print only the areas around the holes. This allowed me to test the clearances without using the time and material needed for the full parts. The pin was left unchanged.

### CAD Modifications

I started by sketching a 1.00 in wide section around the shaft hole in the support. The larger rectangle covered the surrounding structure so I could remove the material outside the test section.

<img width="1617" height="961" alt="Support fit-test sketch" src="https://github.com/user-attachments/assets/3c90bf64-ebe2-446f-9afa-164683e349c6" />

I used a Through All cut in both directions to remove the rest of the structure. This kept the original hole size and support thickness for the fit test.

<img width="1612" height="956" alt="Support fit-test cut" src="https://github.com/user-attachments/assets/ca213ac4-80b6-4df8-b596-3fafeb57c1f1" />

The modified model left two small test pieces containing the support holes. These would allow me to check how the pin fits through both supports.

<img width="1616" height="957" alt="Support hole test pieces" src="https://github.com/user-attachments/assets/212b33b6-3c76-46a9-802a-63989015cf1a" />

For the pulley wheel, I sketched a 1.20 in diameter circle around the center hole. This defined the outside of the test piece while keeping the original shaft opening.

<img width="1616" height="960" alt="Pulley hub fit-test sketch" src="https://github.com/user-attachments/assets/8aaec923-01be-4d91-8b2a-6eafb0bd6953" />

I used a Through All cut to remove the material outside this circle. This removed the rim and spokes, leaving only the section needed to test the pin fit.

<img width="1617" height="956" alt="Pulley hub fit-test cut" src="https://github.com/user-attachments/assets/7f63b2d3-82f8-4b2c-9311-4b7e48aba40e" />

The remaining piece kept the wheel’s original hole diameter and hub thickness. I used this smaller piece to check the clearance between the wheel and pin.

<img width="1616" height="961" alt="Pulley hub test piece" src="https://github.com/user-attachments/assets/7092e3ba-6f0b-46b5-a162-7816b79ca4f4" />

### Slicer

I arranged the two support pieces upright with their holes horizontal, placed the pulley hub flat with its hole vertical, and laid the unchanged pin horizontally. The preview shows supports beneath the pin and inside the horizontal support holes.

For this fit test, the slicer used Prusa PETG, 20% infill, and supports set to Everywhere with no brim. The selected printer profile was the Prusa CORE One HF with a 0.4 mm nozzle. The estimated print time was 1 hour and 28 minutes, using 21.63 g of filament.

<img width="1917" height="1031" alt="Fit-test slicer preview" src="https://github.com/user-attachments/assets/09126d24-ad8c-490d-838d-70b9c1530f7c" />

### Print

The completed print took 1 hour and 40 minutes, with the printer reporting 22 g of PETG used. This was 12 minutes longer than the slicer estimate.

<img width="4032" height="3024" alt="Completed fit-test print information" src="https://github.com/user-attachments/assets/c4ca1513-5724-48fb-afbe-3d6d16139eff" />

The video below documents the fit test between the printed pin, support pieces, and pulley hub.

<video src="https://github.com/user-attachments/assets/9b3e9981-7534-444e-b843-2e7fb205d04e" controls style="max-width: 100%;">
</video>

## Prototype Print

### FDM Print

I placed the pulley wheel flat on the build plate with the shaft hole vertical and laid the pin horizontally beside it. I used PETG with a 0.20 mm layer height, 30% infill, and supports set to Everywhere. Supports were generated beneath the wheel’s overhangs and the pin. The estimated print time was 5 hours and 46 minutes, using 124.33 g of filament.

<img width="1910" height="1031" alt="Pulley wheel and pin slicer preview" src="https://github.com/user-attachments/assets/46bc7fd4-d87d-4b60-a1f9-11b4e8d26ece" />

I placed the support structure upright with its base flat on the build plate. This provided a large contact area, but supports were needed for the shaft holes and overhanging sections. I used PETG with a 0.20 mm layer height, 30% infill, and supports limited to the build plate. The estimated print time was 10 hours and 19 minutes, using 186.31 g of filament.

<img width="1912" height="1036" alt="Support structure slicer preview" src="https://github.com/user-attachments/assets/2fa083de-8568-4af4-b12b-4c9dbbb9f3e9" />

This image shows the printed support structure on the build plate with the organic supports still attached. These supports needed to be removed before assembling the wheel and pin.

<img width="1912" height="1036" alt="Printed support structure before support removal" src="https://github.com/user-attachments/assets/2514f2e6-7eb4-469e-9bbe-a38fb9ce4c6d" />

The video below shows the printed pulley wheel and pin.

<video src="https://github.com/user-attachments/assets/b9be64c3-99b0-4c61-80d9-e80f7d2095d5" controls style="max-width: 100%;">
</video>

### SLA Pin

I used the same CAD file for the SLA pin as the FDM pin, keeping the diameter and length unchanged. The pin was printed using Clear V5 resin, allowing me to use a second manufacturing process in the prototype.

I was unable to retrieve the SLA print information, even after a friend helped me try to find it. Because of this, I could not include screenshots or confirm the orientation, support settings, layer height, print time, or resin volume used. The printed SLA pin will appear in the assembly section, where you can check its fit with the pulley wheel and support structure. The final SLA print will be showcased fully once completed.

## Assembly and Test of the Prototype
NEED TO SHOWCASE AND DOCUMENT



# Part 2
