<h1 align="center">Lab #4: Benchmark a Parameter </h1>
<h2 align="center">Benchmark Test: Tolerance Gauge Test </h2>
  
### Prediction
I predict that my design will likely fail to be pushed through until it reaches the 0.33-inch diameter pins, the 3rd column. Based on my calculations, each increment in diameter decreases roughly by 0.01 inches. With the tolerance of each layer being roughly +-0.01 inches, it is likely for the pin with the "0.34" inch diameter to contain imperfections that contact each other and bind them together to become a singular body. Once we reach 0.33 inches, these imperfections are less likely to completely bind the 2 parts into one.

### Design

#### CAD Modeling

#### PrusaSlicer

The infill that I chose for the 3D print was 10% Honeycomb; this was chosen mainly due to time constraints and force redistribution without the cost of extra material and time. I initially wanted to attempt to use the Gyroid pattern but considered that the time I was predicted to take was roughly 1 hour and 25 minutes, with Nicholas's artifact included as well (the assignment specifies "Print time may not exceed one hour per artifact"). The pair of the 10% and honeycomb provide a adequite enough structure without having to cost us more materials and time.

No supports were used within either of our prints; this was a deliberate choice to avoid complications in measuring the tolerances of the pins within the holes. Any floating structures that require supports could introduce errors that throw off results. Although it is considered important to take into account these errors if you engage with tolerances with supports. But for the simplicity of the experiment, we choose to avoid them for now.

The Chosen Build orientation shown below was decided to prioritize ease of printing and the effect on the tolerances; both Nicholas's and my models were input on their sides and required a rotational adjustment of 90 degrees to ensure that the base of the primary models and the pins are flush with the baseplate of the printer. If the model remained on its side, the individual pin models would have been floating and would have almost definitely introduced failure with the tolerances, rendering the experiment completely useless.

Reminder: Picture of model on side
Remind: PICTURE OF BUILD ORIENTATION

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

To note this is likely due to us not preheating early enough on the printer, as we were able to quickly upload the G-code to the USB and then take it to the printer before the preheating process could complete.

<img width="4032" height="3024" alt="IMG_5836" src="https://github.com/user-attachments/assets/aeca5c31-0b68-444d-a0f8-740929441dc2" />



## Objective


Remind: mention Elephant foot setting: 2 mm 

## Resources
Design Rules for 3D Printing PDF: [Download Link](https://github.com/user-attachments/files/32124984/PL_3DP_Design_Rules_EN.1.pdf)

Printables Tolerance Test Example: [Link to Page](https://www.printables.com/model/31843-tolerance-test/files)
## Decide


## Communicate

