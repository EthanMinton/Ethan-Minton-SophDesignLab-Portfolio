# Final Project – [Topic]

## Objectives


## Problem to Solve


## Part 1

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

## Part 2
