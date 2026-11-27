# Final Project – Door-Slowing Pulley System

## Objectives

The goal of this project is to improve my previous pulley design and use it to slow a door before it closes. I will use FDM for the wheel and support structure and SLA for the pin. Fit testing and feedback from classmates will help me figure out what needs to change.

# Part 1

### Spiral Design Process

The Spiral Design Process repeats planning, risk analysis, engineering, and evaluation to improve a design. Each time through the cycle, you use what you learned from the previous version to decide what to change. The idea is to find the biggest problems early, before spending more time and money on the full design.

Planning - This is where you decide what the design needs to do and what limits you have, such as materials, cost, and time. The plan changes as you test the design and find out what works.

Risk Analysis - This is where you look at what could stop the design from working. You can compare different ideas, run calculations, or make smaller test pieces before committing to the full prototype.

Engineering - This is where you make the sketches, CAD models, and prototypes. You build and test the design using what you figured out during planning and risk analysis.

Evaluation - This is where you check whether the prototype does what you wanted. You look at what worked, what failed, and what feedback you received, then decide what to change in the next version.

For my project, I plan to use this process to check the fit before printing the full pulley. I can print smaller sections around the holes, test the pin, and change the clearance if needed. This should help me avoid spending hours printing a full assembly just to find out the parts do not fit. After that, I can use feedback from classmates to decide what else needs to change.

### FDM Anisotropic

FDM Anisotropy - Anisotropy means that a part behaves differently depending on the direction of the force applied to it. FDM builds parts by laying down lines of melted plastic and stacking them into layers. A part is generally stronger along those printed lines than it is when a force tries to pull the layers apart. This means that changing the print orientation can affect how the part bends or breaks.

Prototype Performance - For my pulley, the print orientation matters because the rope puts force on the wheel, pin, and support structure. I need to consider the direction of those forces when placing each part on the build plate. Adding more material can help reinforce the part, but I still need to avoid loading it in a way that pulls the layers apart.

Design Decisions - I can place the main tensile loads along the printed lines, add fillets at sharp corners, and reinforce areas around the pin holes. If one orientation does not work for the whole assembly, I can print the parts separately in different orientations. More walls can also help, although they do not remove the difference in strength between directions. The pin especially needs attention because printing it vertically could make it easier to break between layers when it bends.

Materials and Process Parameters - I considered PETG for its toughness, but the strength of the printed part also depends on how well its layers bond. Nozzle temperature and cooling affect that bond. Printing within the recommended temperature range and avoiding excessive cooling can help with layer adhesion. I still need to check how the parts perform with the settings used for this project.

https://www.stratasys.com/contentassets/1a0cc7a8e7d14f29ac972189bfeade4c/dg_fdm_designconsiderationsfdmtooling_0718a.pdf

### SLA Shrinkage

SLA resin can shrink during printing and post-curing as the resin cures. Formlabs describes Grey V5 and Clear V5 as low-shrinkage resins, but the sources I found did not give an exact curing-shrinkage percentage for either one.

For Grey V5, Formlabs reports typical XY dimensional tolerances of ±0.15% for features between 1–30 mm, with a minimum tolerance of ±0.02 mm. These results used 100 µm layers and five minutes of room-temperature post-curing. This describes final dimensional accuracy, not the amount of shrinkage.

Grey V5

| Feature Size | Typical XY Dimensional Tolerance |
| --- | --- |
| 1–30 mm | ±0.15%, with a minimum of ±0.02 mm |
| 31–80 mm | ±0.2%, with a minimum of ±0.06 mm |
| 81–150 mm | ±0.3%, with a minimum of ±0.15 mm |

For my pulley, small changes in the hole and pin dimensions could make the fit too tight or too loose. I can check this with a fit coupon, measure it after washing and curing, and adjust the clearance based on the result. PreForm already compensates for expected shrinkage, so any extra adjustment should come from the error I measure in the printed part.

https://formlabs-media.formlabs.com/datasheets/2401898-TDS-ENUS-0.pdf

### Laser Cut Kerf

Kerf is the width of material removed by the laser during cutting. Without compensation, outside dimensions become smaller and holes or slots become larger. Kerf varies with the material, sheet thickness, focus, power, and cutting speed.

Kerf can be compensated for by adjusting the CAD dimensions or offsetting the cutting path in the laser software. In my previous kerf tests, I used a slot adjustment of around 1.5 times the measured kerf to get the fit I wanted. That adjustment came from testing with that material and setup. For a future laser-cut part, I would measure the sheet thickness and cut several test slots using the same settings as the final part. A loose joint could move or pull apart, while one that is too tight could be difficult to assemble or crack the material.

https://docs.lightburnsoftware.com/latest/Guides/Test-KerfOffset/

## Problem Selection

### Modular Storage

Something that I have always wanted to create and design is a modular storage system that could be modified to fit a person's unique needs. Small items such as screws, electronic components, different parts, or even Lego can become mixed and difficult to find. Standard storage containers may have compartments that are too large or too small, which wastes space and makes organization difficult.

The problem I would like to solve is how to create storage that can change as the items being stored change. Different compartments and attachments could be printed and added without replacing the entire system. I think this would be the simplest of the three ideas because the design would mainly depend on getting one sliding fit to work across all the parts.

### Force Directional Change

Another problem that interests me is how to change the direction of an applied force when there is limited space to move or pull an object. For example, lifting an object directly upward can be difficult if there is no convenient place to grip it or stand above it. I previously tried making a pulley for my closet door, but it needed a specific setup and was difficult to use elsewhere.

Outside of my door, a pulley system could allow a person to pull in a more accessible direction while moving the object in the direction needed. The design would need to keep the rope aligned, allow the pulley to rotate freely, and provide a secure mounting point. Depending on the pulley arrangement, the system could also reduce the force required to lift the object.

### Ball Bearing

Another problem I would like to explore is how to support smooth rotation in a prototype when a standard bearing does not fit the available space. Purchased bearings come in specific sizes, which can require changing other parts of the design or waiting for the correct bearing to arrive.

A 3D-printed ball bearing could be sized around the needs of the prototype. If I made the design parametric, I could change the dimensions for different projects. The main challenge would be leaving enough clearance for the balls to move freely while keeping them contained and limiting unwanted movement. I would need to test the fit, friction, and wear. This would likely be the most difficult of the three problems and require the most testing.

### Selected Problem

#### Force Directional Change

I wanted to take another crack at the pulley system that I created and improve on the flaws I had with the original design. The primary reason I want to solve this problem is that I was disappointed in the work I was able to produce and the lack of versatility the pulley actually had. Having to print another version just to get the pulley to work was frustrating. I want to use what I learned from that experience to create a design that is easier to assemble, modify, and use.

The problem I want to address is how to change the direction of an applied force while allowing the pulley system to work in different arrangements. A pulley that only works with one mounting position or one specific setup has limited use. I would like to explore interchangeable mounting parts and different pulley sizes so the system can be adapted without redesigning and printing the entire assembly. Hopefully, this design is able to finally tackle the door that constantly wakes me up throughout the night.

I can use FDM to print the wheel and support structure, then print smaller test pieces to check the fit before making the full assembly. SLA can be used for the solid pin, with the goal of giving the wheel a smooth surface to rotate around.

The goal is to create a pulley that rotates freely, keeps the rope aligned, and mounts securely.

## Video Describing Problem

The problem and how the pulley setup will work are explained in Video #1 below.

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

I was unable to retrieve the initial SLA print information, even after a friend helped me try to find it. Because of this, I could not include screenshots or confirm the orientation, support settings, layer height, print time, or resin volume used for that print. The final SLA pin settings and screenshots are included in Part 2.

## Assembly and Test of the Prototype

This image shows the assembled prototype with the white support structure. The wheel sits between the supports, with the pin passing through the holes in the structure and wheel.

<img width="4032" height="3024" alt="IMG_0529" src="https://github.com/user-attachments/assets/0b33fa75-7d8b-4705-a5d8-d61294785f2b" />

### Assembly and Use Instructions

To assemble the pulley, place the wheel between the two sides of the support structure. Line up the hole in the wheel with the holes in both supports, then slide the pin through the first support, the wheel, and the opposite support. The pin acts as the axle and holds the wheel in place while allowing it to rotate. The final assembly uses the FDM wheel and support structure with the SLA pin.

To use the pulley for the door, nail the base to the wall through its mounting holes. Run the rope over the wheel so it sits inside the groove, then attach one end to the door and the other end to a weight resting on the ground. Adjust the rope length so the weight stays on the ground until the door is almost closed. As the door reaches that point, the rope becomes taut and lifts the weight off the ground. Lifting the weight resists the door's movement and slows it before it can slam shut.

## Video #1

<video src="https://github.com/user-attachments/assets/b2caa847-ff46-47c0-9af5-c04da5f3a4a0" controls style="max-width: 100%;">
</video>

# Part 2

## Student Peer Review

<img width="3024" height="4032" alt="IMG_0479" src="https://github.com/user-attachments/assets/68cfd5d7-cd42-4c5c-a2f1-d3ffea7c014f" />

<img width="3024" height="4032" alt="IMG_0480" src="https://github.com/user-attachments/assets/642c8512-f3a7-4b62-94ab-9e383dcbaa9f" />

<img width="3024" height="4032" alt="IMG_0478" src="https://github.com/user-attachments/assets/55d5fbbd-a0ad-47aa-add3-30dd6becd1a6" />

<img width="3024" height="4032" alt="IMG_0476" src="https://github.com/user-attachments/assets/a193873c-4271-4d36-a3df-34b0be3be7e2" />

<img width="3024" height="4032" alt="IMG_0475" src="https://github.com/user-attachments/assets/e094c574-24a2-457e-8991-f756e08a192b" />

<img width="3024" height="4032" alt="IMG_0477" src="https://github.com/user-attachments/assets/5fc24007-aeb1-4ff0-b6d8-33e7278e480e" />

My classmates understood the problem and thought the pulley could be made using FDM and SLA. One comment I liked was that the pin was easy to slide in and out while still fitting the assembly. That was something I wanted from the design, but getting the parts together was only part of the problem.

The main issue was the wheel wobbling as it turned. My classmates mentioned shaking, rubbing noises, and the need for smoother spinning. I agreed with this feedback because I could get the parts to fit together, but the wheel still did not rotate the way I wanted. The wobbling could also let the wheel rub against the supports.

Another concern was how the rope would fit in the groove. The feedback mentioned rope fitment and possible slippage. I needed to leave enough space for the rope while still keeping it seated as the wheel turned. This gave me another feature to adjust along with the wheel clearance.

## Redesign

### Pulley Support CAD

I made two main changes to the pulley support. First, I reduced the vertical dimension of the triangular cuts at the top from 1.50 in to 1.00 in. This made the slopes less steep and gave the upper section a cleaner appearance. The shaft holes remained 0.62 in in diameter, with their centers 0.50 in below the top.

<img width="1617" height="962" alt="Modified upper profile sketch" src="https://github.com/user-attachments/assets/c2adf981-ba50-4ee7-adc7-31acd55eeb10" />

I then added a 3-degree draft to the two inner faces near the shaft holes, using Plane1 as the neutral plane. This tapered the faces to provide more clearance for the pulley wheel and reduce rubbing against the support structure.

<img width="1616" height="960" alt="Inner support draft settings" src="https://github.com/user-attachments/assets/aea872a5-b2ae-4f7e-928a-7534368556ab" />

This view shows the updated support with both changes applied. The revised model will allow me to check whether the added clearance reduces contact between the wheel and supports during rotation.

<img width="1612" height="958" alt="Updated pulley support model" src="https://github.com/user-attachments/assets/77cce6e2-696c-489a-86de-a249f1552a1c" />

### Pulley Wheel CAD

I wanted the wheel to resemble a nuclear radiation symbol. Some of my classmates noticed this during the peer review and thought it was cool, so I kept that appearance while adjusting the wheel’s fit.

I added a global variable named CLEARANCE and set it to 0.01 in. Both flange thicknesses are controlled by the equation `0.27 - "CLEARANCE" * 0.5`. This makes the fit parametric, allowing me to adjust both sides together when optimizing the clearance later.

<img width="1507" height="522" alt="Wheel clearance equations" src="https://github.com/user-attachments/assets/8cfb876d-c276-4d02-8c76-422d7999e7e1" />

I updated the wheel’s cross-section to give it a tighter fit between the supports, with the goal of reducing sideways movement. I also increased the groove width from 0.19 in to 0.25 in to provide more space for the rope. The groove depth remained 0.50 in.

<img width="1616" height="960" alt="Updated wheel cross section and clearance" src="https://github.com/user-attachments/assets/0fbc6e3a-6506-49fb-9814-d15107a03e4e" />

I changed each of the three openings from 100 degrees to 60 degrees. This left wider solid sections between the openings and made the wheel look more like the radiation symbol. The outer radius of the openings remained 2.30 in.

<img width="1617" height="963" alt="Updated wheel opening sketch" src="https://github.com/user-attachments/assets/3492da7b-79cc-40cb-bf7a-0534bd9e9e2f" />

I reduced the depth of this face recess from 0.20 in to 0.10 in. This left more material in the spokes while keeping the recessed area around the hub.

<img width="1617" height="957" alt="Modified wheel recess depth" src="https://github.com/user-attachments/assets/3dac5c3b-5351-4531-953e-cc5e9f4e6a7d" />

I suppressed Fillet15 to keep the sharper corners of the symbol instead of rounding the connections around the hub.

<img width="272" height="25" alt="Suppressed hub fillet" src="https://github.com/user-attachments/assets/b8ad8e28-59cb-44dd-9e8b-d3c2f65b3c48" />

### Final Assembly

<img width="1617" height="962" alt="image" src="https://github.com/user-attachments/assets/cf5ebec6-753e-40a3-8db1-8dd632d6f9d6" />

<img width="1616" height="961" alt="image" src="https://github.com/user-attachments/assets/be3ab5cc-caa9-4c69-b83b-d46cfc694e13" />

## Printing Final Design

I placed the updated support structure upright with its base flat on the build plate. I used Prusa PETG with a 0.20 mm layer height, 30% infill, and supports limited to the build plate. The organic supports extend beneath the shaft holes and overhanging sections. The estimated print time was 10 hours and 26 minutes, using 189.53 g of filament.

<img width="1917" height="1027" alt="Updated support structure slicer preview" src="https://github.com/user-attachments/assets/aed5e1e9-6a27-4f43-b365-98c6a8b1d0b9" />

I placed the updated pulley wheel flat with its shaft hole vertical on a separate build plate. I used the same material, layer height, and infill settings. Supports were generated from the build plate beneath the overhanging rim and recessed sections. The estimated print time was 6 hours and 53 minutes, using 138.83 g of filament. Neither print used a brim.

<img width="1917" height="1040" alt="Updated pulley wheel slicer preview" src="https://github.com/user-attachments/assets/7d0e641d-304e-486d-8d5f-c2fcac917c10" />

### Final SLA Pin

I printed the final pin on the Form 4 named MatureImpala using Clear V5 resin and a layer thickness of 0.05 mm. The pin and its supports fit within one-quarter of the Form 4 build plate, meeting the size requirement. I positioned the pin upright with supports at its base. PreForm estimated a print time of 2 hours and 12 minutes and a resin volume of 8.58 mL.

<img width="1907" height="1081" alt="image" src="https://github.com/user-attachments/assets/0c350e22-6049-4464-a197-9d5b18355462" />

<img width="1907" height="1133" alt="image" src="https://github.com/user-attachments/assets/1c0ba1e8-f184-4408-958b-aace8a8b65f3" />

## Final Assembly and Testing

The final prototype uses the printed PETG wheel and support structure with the Clear V5 SLA pin. It assembles using the same process described in Part 1, with the holes lined up before sliding the pin through all three components.

This image shows the completed final design with the dark support structure and redesigned wheel.

<img width="4032" height="3024" alt="IMG_0526 (1)" src="https://github.com/user-attachments/assets/a4e96575-7c14-48c3-b74d-b46f0a1ea546" />

The close-up below shows the SLA pin pushed through the aligned holes in the support structure and wheel. The pin holds the assembly together and acts as the axle for the wheel.

<img width="4032" height="3024" alt="IMG_0530" src="https://github.com/user-attachments/assets/a02557c0-27e4-4887-884d-6d7bf026d503" />

After testing the updated assembly, I found that it works better and makes less of the loud scratching noise from the original design. The tradeoff is that the wheel has a bit more friction than before, so it does not spin as freely. I would still like to adjust the clearance to reduce that friction while keeping the quieter operation.

## Part 2 Video

<video src="https://github.com/user-attachments/assets/4365d4ff-3482-43fc-82ae-3ef1db9d72d5" controls style="max-width: 100%;">
</video>

## Slide Presentation

<img width="1907" height="1067" alt="image" src="https://github.com/user-attachments/assets/d1a306d6-6c5b-4423-87d9-93d519030084" />

## Resources

- [Pulley Support CAD](Pulley_structure_v2.SLDPRT)
- [Pulley Wheel CAD](Pulley_wheel_v2.SLDPRT)
- [Pulley Pin CAD](Pulley_PIN.SLDPRT)
- [FDM Design Considerations](https://www.stratasys.com/contentassets/1a0cc7a8e7d14f29ac972189bfeade4c/dg_fdm_designconsiderationsfdmtooling_0718a.pdf)
- [Grey V5 Technical Data Sheet](https://formlabs-media.formlabs.com/datasheets/2401898-TDS-ENUS-0.pdf)
- [Laser Kerf Compensation](https://docs.lightburnsoftware.com/latest/Guides/Test-KerfOffset/)
