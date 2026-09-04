# A3 – [Topic]


## Design 
Document the design process, which includes many pictures with an overview of images at the different stages.
Detail the steps and reasons/decisions from start to finish.

Openning CREO I initially began by slecting the datum plane to create my model. I had a plan in mind here to create a model that would be able to test the abilities of the 3D printers with curved edges and the geometetry that surrounded it. I wanted to utilize the engineering shaping tools within this design to really observe the details that the printer can create at such a small scale.
<img width="2559" height="1362" alt="Screenshot 2026-09-01 132927" src="https://github.com/user-attachments/assets/c099c2e7-ef3e-4841-b784-bae4ef6de808" />
<img width="2559" height="1364" alt="Screenshot 2026-09-01 133045" src="https://github.com/user-attachments/assets/624d7038-2729-4dc2-872a-ce8de12972af" />

I sketched out the initial shape of the sketch to be a 1.5 inch by 1.5 inch square to maximize the total area that could be used and to really scale out the model, of course this comes at a drawback with taking much more time to physically print.

<img width="2559" height="1365" alt="Screenshot 2026-09-01 133206" src="https://github.com/user-attachments/assets/b010a852-d2eb-4fdc-844d-d8e5e1a4c41f" />

To maximize the the given constraints I then extruded the shape by 0.5 inch to create the general outline.

<img width="2559" height="1360" alt="Screenshot 2026-09-01 133302" src="https://github.com/user-attachments/assets/98e54aa1-7545-4f57-b635-c489f8c86099" />

The next couples of steps involves applying the engienering shaping tools in a way to create some more complex geometries. The first step was taking the 3D model and applying a shell to it creating a gap within the model. Once completed I then added a large round shaping the edges of the interior portion of the box with a radius of 0.7 inch. I then added an edge chamfer to the adjacent side of the interior to the round to create this more traditional slope that transitioned into the round section. I went out of my way to ensure this geometry took place as I wanted to test how different sloping geometries would be handed with the traditional slope, the curved slope, and the sudden clash between the 2. 


<img width="2559" height="1363" alt="Screenshot 2026-09-01 134924" src="https://github.com/user-attachments/assets/66727334-9a34-448a-8ac5-6972912dda9e" />
<img width="2559" height="1366" alt="Screenshot 2026-09-01 135124" src="https://github.com/user-attachments/assets/77f65370-5005-4624-9024-3023bff47618" />

Once I had finished utilizing the engineering tools I then created a hole with a diameter of 0.25 inch within the beginning of the curve slope extruding it through the box entirely to see how it handles the sloping ledge that it creates. 

<img width="2559" height="1365" alt="Screenshot 2026-09-01 140122" src="https://github.com/user-attachments/assets/bfbac843-4847-485e-a2fc-925d77a41a0c" />

Completing the model and downloading it into stl. file required me to constraint the geometry into simpler polygons that could be properly interpreted by Prusaslicer leading to the result you find below, this is the final model used for the print.

<img width="2559" height="1364" alt="Screenshot 2026-09-01 140857 (1)" src="https://github.com/user-attachments/assets/68b21ca4-1d89-4031-8c00-da1f2e82f996" />


## Research 
Research three infills not shown in class to describe the geometry and why each infill is used.
Directly answer: how does infill percentage affect mechanical properties, and how do different infill patterns affect mechanical properties?

### Aligned rectilinear 

Aligned Rectilinear is a infill pattern that is made of parallel lines that are drawn across the interior of the model. The primary reason of which this infill pattern is used is to save time when printing, it has an average material consumption, and is considerably simple for the printer to print. Often though this infill can create issues with the first solid top layer on whether the printers path is alligned directly parallel to the infill pattern. As it can leave that top with no support to print onto and bridge the gap.

<img width="2048" height="1536" alt="aligned_rectilinearfinal-2048x1536" src="https://github.com/user-attachments/assets/ad84af50-4f3e-4f03-a7b4-e8b745069013" />

### Concentric 

Concentric infill has a more complex geometry model as it will take the model's direct perimeter lines and create smaller and smaller versions of that shape within itself. The best way to describe it is like a Russian Nesting Doll. Each having the same general shape only becoming smaller and smaller within itself. The primary use for this infill is the flexiblility of the models that it produces. The trade-off for this flexibility is the overall time spent printing this infill with little difference among the material actually used.

<img width="2048" height="1536" alt="aligned_rectilinearfinal-2048x1536" src="https://github.com/user-attachments/assets/ad84af50-4f3e-4f03-a7b4-e8b745069013" />

### Hilbert curve

Hilbert Curve is a abnormaly shaped infill with its geometry primarily being comprised of labrenth style corridorrs. Defined by its unique shape and design it also provides a major use when utilizing this infill. That when you want to fill the print with some kind of epoxy, resin, or other liquid the chamber design allows for the liquid to easily flow through the design. But with this unique design comes the drawback of longer print times.

<img width="2048" height="1536" alt="hilbert_curvefinal-2048x1536" src="https://github.com/user-attachments/assets/ab5af30f-7462-4472-854f-34662f1efacc" />

### Infills affect on Mechanical Properties

The density of the infill, the infill percentage, increates the cross sectional area of our prints helping to directly benefit it ability to combat tensile, compressive, and flexural stress. Due to plastic generally being a softer material infills are a way to circumvent stress that can be applied to the print. As you can expect an increase in the percentage of infill increases the object material used and time taken so it is important to find the right balance between all factors. To elaborate more on the balance a good general idea for how infill percentage can become a case of diminishing returns it was found that the benefit from infill percentage being 25% to 50% gives prints a much higher strength jump comparitviely to the jump of 50% to 75%. 
  
We find that the different infill patterns alter how the stress is distributed and handed. For example the simple 2D lined infill pattern are able to properly distribute the stress applied parallel to its interface but would struggle to handle any applied shear stress. But 3D infill patterns such as the gyroid are great with distributing the stress evenly in all directions, preventing any single stress from localizing.



## Preprocessor and Printing 
Document the slicer information on PrusaSlicer. Some, not all, questions to answer are outlined below to guide your documentation.
Why choose the build orientation?

Grabbing the .stl file from CREO I access PrusaSlicer and uploaded the file. Initially the orientation had the model sitting on the "wall" side causing it to be outside of the print constraints to fix this issue I merely altered the rotation by 90 degrees to sit horizontally. 
<img width="1917" height="1131" alt="Screenshot 2026-09-03 125325" src="https://github.com/user-attachments/assets/413e0632-928b-4f2b-ad03-48906f4e3efd" />
<img width="1917" height="1135" alt="Screenshot 2026-09-03 125355" src="https://github.com/user-attachments/assets/0ae286bd-17e9-4482-b7b2-d0a4a76aba05" />
<img width="1917" height="1136" alt="Screenshot 2026-09-03 130124" src="https://github.com/user-attachments/assets/ba5d0232-63e7-4021-8dd4-2a14e6a2f017" />

Working with Nicholas Brady I uploaded his .stl file into PrusaSlicer and was instructed by Professor Terence Fagan to orient it flat onto the surface similar to how I preformed to prevent any major overhangs due to the cyldindrical holes within his design.

<img width="1917" height="1140" alt="Screenshot 2026-09-03 131353" src="https://github.com/user-attachments/assets/57557929-c74a-4494-903c-860eb747c8a5" />
<img width="1916" height="1110" alt="Screenshot 2026-09-03 132334" src="https://github.com/user-attachments/assets/9d9c0805-f6a5-4227-8ce4-c303bccfeeb5" />
<img width="1916" height="1108" alt="Screenshot 2026-09-03 132608" src="https://github.com/user-attachments/assets/5d3e293d-5fd7-4397-bd03-d9ccf6715133" />

Thankfully to Nicholas and mine properly scaling our models within the given constraints we had no issues this time that involved scaling our models physically at all. We decided to use the "Honeycomb" infill patern with a 10% infill percentage to maintain a good structureal integretey without compensating so much time to print a infill such as Gyroid or another infill with a much higher percentage. We decided to stick with the 3 perimeter as our models were incredibly small means any huge external force is unlikelt to be applied to the point of fracture. Learning from our mistakes of the first lab we didn't struggle to much with any major mistakes through the setup process, the only major issue we faced was the time our print took, both mine and Nichlas's models took full advantage of the space we could work within which means more time spent. It was estimated by Prusa that the print would take around 1 Hour and 9 minutes.

<img width="1917" height="1110" alt="Screenshot 2026-09-03 132927" src="https://github.com/user-attachments/assets/4fb1ae28-fb7e-451b-910d-c8f2f70e593f" />
<img width="1917" height="1086" alt="Screenshot 2026-09-03 140027" src="https://github.com/user-attachments/assets/16903529-f657-4a54-bb31-862db96f609f" />
<img width="1917" height="1115" alt="Screenshot 2026-09-03 140050" src="https://github.com/user-attachments/assets/fee6de2e-3fdf-4f49-a990-65a0690bdfbf" />




## Print 
3D print your design using one of the FDM printers from the UNCC print farm.
Upload a video showing the 3D operation of your component to your GitHub portfolio.
Confirm the printed part meets all stipulations (size, height, no overhangs, PLA/PETG, print time).

## Lessons Learned 
Detailed lessons learned throughout the process, the more detail the better. Which includes detailing any mistakes throughout the process and how you fixed them.
Actual time it took from start to finish, and resources.
What would happen if you scaled this decision up? If your infill percentage or wall thickness choice were applied to a structural or safety-critical part instead of a small desk object, what would the consequences of getting it wrong be?
What mistake did you catch, and what mistake might you not have caught? Detail an error you found and fixed. Then, more importantly: what's one flaw in your design or process that could have gone to print undetected, and what would need to change (in your process, not just this part) to catch it next time?
How does this connect to a real product decision? Identify a consumer or industrial product where infill strategy, wall thickness, or material choice affects user safety (it doesn't have to be 3D printed). Briefly explain the parallel.

Resources (5%)
List all resources used.

## Analyze


## Decide


## Communicate

