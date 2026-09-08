# Lab #3: Design Something Small


## Design 
Document the design process, which includes many pictures with an overview of images at the different stages.
Detail the steps and reasons/decisions from start to finish.

Opening CREO, I initially began by selecting the datum plane to create my model. I had a plan in mind here to create a model that would be able to test the abilities of the 3D printers with curved edges and the geometry that surrounded it. I wanted to utilize the engineering shaping tools within this design to really observe the details that the printer can create at such a small scale.
<img width="2559" height="1362" alt="Screenshot 2026-09-01 132927" src="https://github.com/user-attachments/assets/c099c2e7-ef3e-4841-b784-bae4ef6de808" />
<img width="2559" height="1364" alt="Screenshot 2026-09-01 133045" src="https://github.com/user-attachments/assets/624d7038-2729-4dc2-872a-ce8de12972af" />

I sketched out the initial shape of the sketch to be a 1.5-inch by 1.5-inch square to maximize the total area that could be used and to really scale out the model; of course, this comes at the drawback of taking much more time to physically print.

<img width="2559" height="1365" alt="Screenshot 2026-09-01 133206" src="https://github.com/user-attachments/assets/b010a852-d2eb-4fdc-844d-d8e5e1a4c41f" />

To maximize the given constraints, I then extruded the shape by 0.5 inches to create the general outline.

<img width="2559" height="1360" alt="Screenshot 2026-09-01 133302" src="https://github.com/user-attachments/assets/98e54aa1-7545-4f57-b635-c489f8c86099" />

The next couples of steps involves applying the engineering shaping tools in a way to create some more complex geometries. The first step was taking the 3D model and applying a shell to it, creating a gap within the model. Once completed, I then added a large round to shape the edges of the interior portion of the box with a radius of 0.7 inches. I then added an edge chamfer to the adjacent side of the interior to the round to create this more traditional slope that transitioned into the round section. I went out of my way to ensure this geometry took place, as I wanted to test how different sloping geometries would be handled with the traditional slope, the curved slope, and the sudden clash between the 2. 


<img width="2559" height="1363" alt="Screenshot 2026-09-01 134924" src="https://github.com/user-attachments/assets/66727334-9a34-448a-8ac5-6972912dda9e" />
<img width="2559" height="1366" alt="Screenshot 2026-09-01 135124" src="https://github.com/user-attachments/assets/77f65370-5005-4624-9024-3023bff47618" />

Once I had finished utilizing the engineering tools, I then created a hole with a diameter of 0.25 inches at the beginning of the curve slope, extruding it through the box entirely to see how it handles the sloping ledge that it creates. 

<img width="2559" height="1365" alt="Screenshot 2026-09-01 140122" src="https://github.com/user-attachments/assets/bfbac843-4847-485e-a2fc-925d77a41a0c" />

Completing the model and downloading it into stl file required me to constrain the geometry into simpler polygons that could be properly interpreted by PrusaSlicer, leading to the result you find below. This is the final model used for the print.

<img width="2559" height="1364" alt="Screenshot 2026-09-01 140857 (1)" src="https://github.com/user-attachments/assets/68b21ca4-1d89-4031-8c00-da1f2e82f996" />

*To note, no overhangs were used within the model as instructed, I do find it very important to understand what overhangs are feasible without supports and which require. But for the sake of preventing any issues with the print I elected to avoid any overhangs in their entirety.*

## Research 

The 3 infill patterns below are ones that were not explicitly shown in class, I decided to find examples that provide different uses and abilities compared to other to gather a better general understanding of all patterns.

### Aligned rectilinear 

Aligned Rectilinear is an infill pattern that is made of parallel lines that are drawn across the interior of the model. The primary reason this infill pattern is used is to save time when printing; it has an average material consumption and is considerably simple for the printer to print. Often, though, this infill can create issues with the first solid top layer on whether the printer's path is aligned directly parallel to the infill pattern. As it can leave that top with no support to print onto and bridge the gap.

<img width="2048" height="1536" alt="aligned_rectilinearfinal-2048x1536" src="https://github.com/user-attachments/assets/ad84af50-4f3e-4f03-a7b4-e8b745069013" />

### Concentric 

Concentric infill has a more complex geometry model, as it will take the model's direct perimeter lines and create smaller and smaller versions of that shape within itself. The best way to describe it is like a Russian Nesting Doll. Each has the same general shape, only becoming smaller and smaller within itself. The primary use for this infill is the flexibility of the models that it produces. The trade-off for this flexibility is the overall time spent printing this infill, with little difference in the material actually used.

<img width="2048" height="1536" alt="aligned_rectilinearfinal-2048x1536" src="https://github.com/user-attachments/assets/ad84af50-4f3e-4f03-a7b4-e8b745069013" />

### Hilbert curve

Hilbert Curve is a abnormaly shaped infill with its geometry primarily being comprised of labyrinth-style corridors. Defined by its unique shape and design it also provides a major use when utilizing this infill. That when you want to fill the print with some kind of epoxy, resin, or other liquid the chamber design allows for the liquid to easily flow through the design. But with this unique design comes the drawback of longer print times.

<img width="2048" height="1536" alt="hilbert_curvefinal-2048x1536" src="https://github.com/user-attachments/assets/ab5af30f-7462-4472-854f-34662f1efacc" />

### Infills affect on Mechanical Properties

The density of the infill, the infill percentage, increases the cross-sectional area of our prints, helping to directly benefit it ability to combat tensile, compressive, and flexural stress. Due to plastic generally being a softer material, infills are a way to circumvent stress that can be applied to the print. As you can expect, an increase in the percentage of infill increases the object material used and time taken, so it is important to find the right balance between all factors. To elaborate more on the balance, a good general idea for how infill percentage can become a case of diminishing returns it was found that the benefit from infill percentage being 25% to 50% gives prints a much higher strength jump comparatively to the jump of 50% to 75%. 
  
We find that the different infill patterns alter how the stress is distributed and handled. For example, the simple 2D lined infill pattern can properly distribute the stress applied parallel to its interface but would struggle to handle any applied shear stress. But 3D infill patterns such as the gyroid are great at distributing the stress evenly in all directions, preventing any single stress from localizing.



## Preprocessor and Printing 
Document the slicer information on PrusaSlicer. Some, not all, questions to answer are outlined below to guide your documentation.
Why choose the build orientation?

Grabbing the .stl file from CREO, I accessed PrusaSlicer and uploaded the file. Initially, the orientation had the model sitting on the "wall" side causing it to be outside of the print constraints. To fix this issue, I merely altered the rotation by 90 degrees to sit horizontally. 
<img width="1917" height="1131" alt="Screenshot 2026-09-03 125325" src="https://github.com/user-attachments/assets/413e0632-928b-4f2b-ad03-48906f4e3efd" />
<img width="1917" height="1135" alt="Screenshot 2026-09-03 125355" src="https://github.com/user-attachments/assets/0ae286bd-17e9-4482-b7b2-d0a4a76aba05" />
<img width="1917" height="1136" alt="Screenshot 2026-09-03 130124" src="https://github.com/user-attachments/assets/ba5d0232-63e7-4021-8dd4-2a14e6a2f017" />

Working with Nicholas Brady, I uploaded his .stl file into PrusaSlicer and was instructed by Professor Terence Fagan to orient it flat onto the surface, similar to how I performed, to prevent any major overhangs due to the cylindrical holes within his design.

<img width="1917" height="1140" alt="Screenshot 2026-09-03 131353" src="https://github.com/user-attachments/assets/57557929-c74a-4494-903c-860eb747c8a5" />
<img width="1916" height="1110" alt="Screenshot 2026-09-03 132334" src="https://github.com/user-attachments/assets/9d9c0805-f6a5-4227-8ce4-c303bccfeeb5" />
<img width="1916" height="1108" alt="Screenshot 2026-09-03 132608" src="https://github.com/user-attachments/assets/5d3e293d-5fd7-4397-bd03-d9ccf6715133" />

Thankfully, Nicholas and I properly scaled our models within the given constraints; we had no issues this time that involved scaling our models physically at all. We decided to use the "Honeycomb" infill pattern with a 10% infill percentage to maintain good structural integrity without spending so much time printing an infill such as Gyroid or another infill with a much higher percentage. We decided to stick with the 3 perimeter, as our models were incredibly small means any huge external force is unlikely to be applied to the point of fracture. Learning from our mistakes in the first lab, we didn't struggle too much with any major mistakes through the setup process; the only major issue we faced was the time our print took. Both mine and Nicholas's models took full advantage of the space we could work within, which means more time spent. It was estimated by Prusaslicer that the print would take around 1 Hour and 9 minutes.

<img width="1917" height="1110" alt="Screenshot 2026-09-03 132927" src="https://github.com/user-attachments/assets/4fb1ae28-fb7e-451b-910d-c8f2f70e593f" />
<img width="1917" height="1086" alt="Screenshot 2026-09-03 140027" src="https://github.com/user-attachments/assets/16903529-f657-4a54-bb31-862db96f609f" />
<img width="1917" height="1115" alt="Screenshot 2026-09-03 140050" src="https://github.com/user-attachments/assets/fee6de2e-3fdf-4f49-a990-65a0690bdfbf" />

To elaborate more on the chosen wall thickness, we believed that the small simplistic nature of the designs they did not require a heavier perimeter above the value of 3. As 3 layers of perimeter would give each wall roughly 1.2 mm of surface thickness to the print, enough to not crumble or break when interacted with but not too much to where it becomes too heavy or takes too much time which we already were in short supply of.

*Screenshot of G-code Upload*
<img width="935" height="585" alt="Screenshot 2026-09-03 132836" src="https://github.com/user-attachments/assets/a1fea5b9-c4bd-41c7-86d3-ff007d976973" />


## Print 

The 3D printing process was considerably smoother than our first attempt at printing, as we kept a keen eye out for issues with the filament getting caught, as it had previously. To note, this had actually happened to another group during our printing time. The primary issue that had arisen was the time we were going to take to have the print complete.

As previously mentioned, the print was estimated to take approximately 1 hour and 9 minutes, although this estimate is typically off, as the estimation doesn't take into account the time that it requires to temperature-prep the printer. For documentation, I recorded the length of the print with my personal device as a double measure to check whether or not the time taken to heat the 3D printer was included in our total time. The moment we uploaded the G-code to the machine, I started the personal timer.

<img width="4032" height="3024" alt="IMG_5776 (1)" src="https://github.com/user-attachments/assets/e7c22a58-0654-431d-bd3e-3f4029cf6d41" />

This photo shows the earlier stage of the print as it begins to lift off the base and uses the infill pattern of honeycombs at 10%. To both Nicholas's and my surprise, the size of our prints was smaller than we expected, and the infill was larger than we expected.

<img width="4032" height="3024" alt="IMG_5784" src="https://github.com/user-attachments/assets/a869bdb7-36e2-4782-93db-7621aa12609e" />


Here is the video recorded towards the latter end of the print. Noting the speed at which the printer was moving.
<video src="https://github.com/user-attachments/assets/0ceceebf-1528-44a6-a6eb-c96dce0764e4" controls style="max-width: 100%;">
</video>

After the print had concluded, roughly 1 hour 23 minutes had passed, with the temperature preparation accounting for the extra time added to the estimated 1 hour 9 minutes. Both the printer's timer and the personal timer match in recorded time passed, confirming that the clock starts the moment you press the print button.
<img width="4032" height="3024" alt="IMG_5792" src="https://github.com/user-attachments/assets/d38a746b-4bc5-4b39-ba49-2a14b05d58bf" />
<img width="1169" height="929" alt="IMG_5791" src="https://github.com/user-attachments/assets/aff6986c-3f49-4572-80f4-ec8e9bd2d77f" />

As shown in the print within the settings, the print was completed using PETG; the time taken was 1 hour 23 minutes, and the final measured dimensions can be found below: roughly 1.4965 inches by 1.4960 inches, with a height of 0.4950 inches. Fitting within all given constraints in the assignment.

<img width="4032" height="3024" alt="IMG_5800" src="https://github.com/user-attachments/assets/58040510-afd0-4244-a47a-848f91e5e2e6" />
<img width="4032" height="3024" alt="IMG_5801" src="https://github.com/user-attachments/assets/ab27e91e-95f0-4461-adb5-ed51c4c19aac" />
<img width="4032" height="3024" alt="IMG_5802" src="https://github.com/user-attachments/assets/b08f19f8-eabc-4254-ab2a-4876be8266f1" />


## Lessons Learned 

### Mistake Caught
One of the biggest struggles that 3D printers face is the allocation of time and resources. Through research of the infill strengths and weaknesses, they each carry the process of selecting settings is much more complex and nuanced than previously thought. I had believed that although these choices are allowed to be made by yourself, they are often more arbitrary in their differences. But each different variant of infill has its own strengths, weaknesses, and differences, such as gyroid giving 3D prints a much higher strength compared to other infill patterns due to its geometry being able to distribute stress more evenly than most. Yet it is also a much more expensive infill, both in the time it takes and the material it costs. For small prints such as this lab, it wouldn't have much of an impact, but if you scale up the size of the print or the infill percentage. Our print barely was below the 1 and half hour limit with a 10% infill percentage. The object's relatively small size gives a lot of flexibility to reduce our percentage without much worry. 

But in the case of printing something that is more load-bearing, such as a real-world H support beam used within the expansion of the Charlotte's football stadium, the infill percentage or in this specific case the material used could be the defining setting that ensures stability within a structure. An incorrect material used can lead to structural integrity that would fail under a considered normal load. In school events lives could be lost due a mistake as such. It is every important to note every decision made and the consequences it can lead to. Initially, we considered using a higher infill percentage to observe the strength of our prints, but after slicing our models, we found that the estimated time was above the set limit. Thankfully, I had caught the mistake before taking the code to the printer, which would have had consequences that would require us to reset the 3D print and resliced our models. This eventually led to us deciding to select the honeycomb pattern at 10% infill to try and balance out the time it takes with material strength.

### Mistake Possibly Not Caught

A lot of possible mistakes that could have been made are likely to be within the settings, due to being most unfamiliar with navigation and what each setting does. Specifically, the setting for the perimeter is the most uncertain setting that was modified. Initially, we struggled to find a setting that would account for the print's thickness; we googled for guidance and were pointed to the perimeter setting. Information about it was generally vague. Describing the setting, we decided to keep the setting close to numerical values, as we believed that the value of 3, the value we selected, meant that 3 filled layers of the 0.4mm nozzle would encapsulate the print on every surface. We chose this wall thickness primarily because the model would not require a very thick wall, and if we decided on increasing the wall thickness through the perimeter the time added and material used brough no direct benefit, with little real force being applied to it; we decided not to go lower than 3 to provide some structure while also allowing for space within the model to utilize the infill pattern.  I plan to ask Professor Terence Fagan at the start of Lab #4 to ensure that no mistakes are made in the future, if that is the case. Due to the small scale of the prints, the perimeter or wall thickness has no issue, as the print was considered a success with no structural issues.

### Goal Achieved
Regardless of lessons learned from mistakes, the goal for my model was to learn as much information about the details that the 3D prints could handle at such a scale. Such as how it can handle cylindrical curves, I now observe that to break down the curved section, the print creates overlapping layers on top of each other, getting closer and closer together to create the curved section. The sloped geometry showed similar results, with uniform overlapping layers as it climbed up the print. When the slope met the curved section, it used a wrapping technique that extended from the slope and met at the edge of the curved section. One struggle that the printer seemed to face was creating the hole within the bottom of the curved section, as it seemed to misprint the lines surrounding it, making it more like a drain with a gradient leading to the hole rather than just a cut cylinder from the body. Overall, there was a lot of interesting information to gather from such a small and simple print. It is important to note all of this down to carry on to the next project when designing.

<img width="4032" height="3024" alt="IMG_5805" src="https://github.com/user-attachments/assets/f94d0576-3422-4565-900e-14ef659e8348" />

*Dedicated Time taken, including print time, documentation, and modeling: 5 Hours 30 Minutes*

Resources (5%)

Different Infill Patterns: https://help.prusa3d.com/article/infill-patterns_177130

Infills affect on Mechanical Properties: https://www.mdpi.com/2504-477X/8/4/115

3D Model: [geometry_print_test.prt](geometry_print_test.prt)


