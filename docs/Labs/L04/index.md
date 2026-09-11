<h1 align="center">Lab #4: Benchmark a Parameter </h1>
<h2 align="center">Benchmark Test: Tolerance Gauge Test </h2>
  
### Prediction
I predict that my design will likely fail to be pushed through until it reaches the 0.33-inch diameter pins, the 3rd column. Based on my calculations, each increment in diameter decreases roughly by 0.01 inches. With the tolerance of each layer being roughly +-0.01 inches, it is likely for the pin with the "0.34" inch diameter to contain imperfections that contact each other and bind them together to become a singular body. Once we reach 0.33 inches, these imperfections are less likely to completely bind the 2 parts into one.

### Design

#### CAD Modeling

#### PrusaSlicer

The infill that I chose for the 3D print was 10% Honeycomb; this was chosen mainly due to time constraints and force redistribution without the cost of extra material and time. I initially wanted to attempt to use the Gyroid pattern but considered that the time I was predicted to take was roughly 1 hour and 25 minutes, with Nicholas's artifact included as well (the assignment specifies "Print time may not exceed one hour per artifact"). The pair of the 10% and honeycomb provide a adequite enough structure without costing us more materials and time.

No supports were used within either of our prints; this was a deliberate choice to avoid complications in measuring the tolerances of the pins within the holes. Any floating structures that require supports could introduce errors that throw off results. Although it is considered important to take into account these errors if you engage with tolerances with supports. But for the simplicity of the experiment, we choose to avoid them for now.

The Chosen Build orientation shown below was decided to prioritize ease of printing and the effect on the tolerances; both Nicholas's and my models were input on their sides and required a rotational adjustment of 90 degrees to ensure that the base of the primary models and the pins are flush with the baseplate of the printer. If the model remained on its side, the individual pin models would have been floating and would have almost definitely introduced failure with the tolerances, rendering the experiment completely useless.

Reminder: Picture of model on side
Reminder: PICTURE OF BUILD ORIENTATION

No Scaling was needed, as both Nicholas's and my models were scaled proportionally within CREO using inches as our scale. If we had scaled our models, it would completely ruin the test, as entirely new parameters would be introduced.


### Printing 

**G-Code**
<img width="936" height="87" alt="Screenshot 2026-09-10 132150" src="https://github.com/user-attachments/assets/87eec813-5bc9-472e-b114-3cdff0ac78d9" />

Using Printer PC-13, we began by initializing the "Preheat" option to try to reduce the amount of time that we would take on the printer, as in our previous assignments we noticed that the time accounted for adding to the estimated time was due to this preheating. After uploading the G-Code to the USB, we moved to the printer, uploaded the file, and started the print.

**Print Time Estimated: 1 Hour 25 Minutes**

Once the print began and lifted off the baseplate, I immediately began to worry about the quality of the print and the tolerances it could handle. I worried my calculated measurements were inaccurate, rendering my prediction and test useless. Within the video below, near the end, you can see me begin to zoom in on the best-case pins, trying to observe the gaps between them. I'm concerned that either the printer or the settings aren't optimized to achieve the best tolerance results.


<video controls width="100%">
    <source src="IMG_5829.mp4" type="video/mp4">
</video>

Remind: NEED TO FIX VIDEO

In the photo below, you can find a still of the pins tolerances during the print. The print was a lot messier than our previous one, which is a big reason to why I was a lot more concerned with the final results. Note you can also see the 10% Honeycomb infill within the photo.

<img width="4032" height="3024" alt="IMG_5831" src="https://github.com/user-attachments/assets/446cd02a-e2ad-44c4-b2b8-d92982b47fc2" />

Here you can see that the printer has completed the primary models of both Nicholas's and my parts. If you observe closely, you can see the text that I placed on the side of the model identifying the diameters of the pins. I have more to say about this text within the lessons learned, but it mainly pertains to its depth and legibility.

REMIND: Talk about text in lessons leanred

<img width="4032" height="3024" alt="IMG_5832" src="https://github.com/user-attachments/assets/c3b4dbc1-e3e3-47f7-98dc-c0d6252f8991" />

*Current Progress on Printer Screen*
<img width="4032" height="3024" alt="IMG_5833" src="https://github.com/user-attachments/assets/55353812-db1d-43e1-a438-20057ea469e3" />

Once the Print was completed, the platform lowered and allowed us to access the models. You can observe in the lowered position below that the models were considerably messier than prior prints and required a substantial brush-off to clean them up to look presentable.

<img width="4032" height="3024" alt="IMG_5835" src="https://github.com/user-attachments/assets/98c25801-e127-45c5-ae11-fabcfc5ff519" />

**Final Time taken to print:** 1 hour 36 minutes

To note, this is likely due to us not preheating early enough on the printer, as we were able to quickly upload the G-code to the USB and then take it to the printer before the preheating process could complete.

<img width="4032" height="3024" alt="IMG_5836" src="https://github.com/user-attachments/assets/aeca5c31-0b68-444d-a0f8-740929441dc2" />

## Lessons Learned

### Results 

After removing the 3D print from the baseplate, I found that my results lined up nearly exactly to what I predicted. Which, in the moment, genuinely surprised me based on how inconsistent and messy the print finished. After a small application of force to the "0.32" and "0.31" inch diameter pins, they were easily able to push through the cut holes in the primary part. When I applied force to the "0.33" bottom row, one was able to be pushed through without much difficulty but I found that the top one had a lot more resistance. I could tell that it was loose, as I could easily wiggle it, yet I decided to leave it within the primary as I didn't want to break any pieces. Despite any application of force, the "0.35" and "0.34" inch diameter pins were not able to be extracted and did not have any wiggle room. All of these results were generally expected, with some great insights into the tolerances the Core One machines have.

In the picture below, you can observe the pins that were able to be extracted and the pins that were not able to be extracted. Note you can also observe the gap between the not-extracted "0.33" inch pin and the walls of the primary part. 

<img width="4032" height="2258" alt="IMG_5838" src="https://github.com/user-attachments/assets/efff5f81-faaa-4fdf-bfe4-a89dcbb41c06" />

Looking back at the Design Rules Chart (linked at the bottom within "Resources"), it stated that the minimum tolerence that Fused Deposition Modeling generally has a lower limit tolerance of 0.3 mm, which translates to about 0.011811 inches. I chose to use 0.01 increments for the pin diameters as an estimated value to show the results. Based on the chart, I assumed that it would work around "0.33" because each layer of the 3D print carried the +-0.011811 inches tolerance, which, in the setup I performed, meant that, in a worse case senarior the walls of the primary part and the walls of the pin could have a maximum inconsistency of 0.023622 inches. Well within the "0.35" and "0.34" range and even dipping below the "0.33" pin diameter, with the worst-case diameter required being 0.326378 inches. The fact that only one of the "0.33" inch pins could be safely extracted shows exactly how these tolerance ranges work, with inconsistencies more likely to happen the closer you approach the base value. It provides great value to have the double pin design here because it gave me the chance to observe that tolerance inconsistencies are inconsistent themselves.

<img width="1243" height="77" alt="image" src="https://github.com/user-attachments/assets/78c9d18b-7605-4afb-abf1-c89411c0f66b" />

### Future Changes

As I mentioned prior, one of the things that I noticed was the quality of the print. Specifically, its effect on the imprinted text on the side of the primary model. The extrusion of the text was not nearly deep enough for the text to be easily legible at a glance. Taking a second to observe it, you can figure out what it all means, but an important factor when you create products such as these is that it needs to be easy for the observer to understand its use and what information it conveys. The attached photo below was edited with enhanced contrast, as the camera was not able to clearly capture the lettering. An easy solution here would be to just extrude the text deeper into the model so that the printer doesn't just lightly print the letters out. In this specific case it is unlikely this would be possible, though, as extruding the text deeper could interfere with the primary and pins tolerance interactions. It would be recommended to expand the width of the model more to prevent any issues such as this.

<img width="4032" height="1551" alt="IMG_5842" src="https://github.com/user-attachments/assets/031fee74-8608-49b7-b8d4-7aa687746cf9" />

Another lesson learned is how to take my CAD files and upload them into PrusaSlicer without the concern of geometric compression, the automatic mesh it creates that simplifies geometry. This is a very considerable issue here, as to measure tolernce accurately requires high precision within your geometry, and geometric meshes that make assumptions could ruin any real results from your test. A classmate was able to educate me on how I could work around these geometric meshes and obtain more accurate models within PrusaSlicer using a STEP file. If we instead save our CAD file in CREO as a STEP file rather than an STL file, it doesn't create the mesh that simplifies your geometry when it comes to printing. In the image below you can find the result of using a step file within Prusa.

Remind: Use a STEP file in Prusa and get an image

Similar to last week's lab, we ran into another issue with the time taken to print; due to the increased scale of our model, it was projected to take "1 Hour 25 Minutes." We attempted to preheat the printer to reduce any extra time but still faced some increase in time taken due to heating. A major concern that I have is a print failing later on in its print, requiring me to stay way later into the evening just to make sure that the print is completed and collected; with a strict lab time, this increases the stress. The change that I would make here is printing at a more optimal time. Thankfully, I now have access to the 3D lab with my Student ID, so I can make 3D prints at an earlier time in the day and ensure that if any issue arises, I can fix it without being too late.

The last lesson would likely be to optimize the material usage and modeling of my CAD. If we look at the final print, one key issue that I struggled with was the time taken to print and the material usage. Of course, I was printing with a pair so it took longer; that fact, on my part, took a majority of the time that was expected. If I could go back to the start of this lab, I would almost definitely optimize the modelling process. If you look at the final print below, one of the biggest issues with the model itself is the dead space that is left over on the left and right edges. When I was designing the model I was conversing with the class TA, Nicholas Teixeira, as I was concerned about how the tolerances could end up, and he mentioned the idea of reducing the height and width of the model itself to allow for any possible reprints to move along quicker. The original test did work out, but it provided a lot of insight to the fact that looks and optimization are extremely important when designing to maximize your ability to test. If I were to design another test I would decrease the width and overall height of the model to focus more on the test without taking nearly an hour to print alone.

Total Time Taken: 6 Hours 30 Minutes

Remind: mention Elephant foot setting: 2 mm 

## Resources
Design Rules for 3D Printing PDF: [Download Link](https://github.com/user-attachments/files/32124984/PL_3DP_Design_Rules_EN.1.pdf)

Printables Tolerance Test Example: [Link to Page](https://www.printables.com/model/31843-tolerance-test/files)

