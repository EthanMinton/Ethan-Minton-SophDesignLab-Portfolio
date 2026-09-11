# Lab #4: Benchmark a Parameter

## Benchmark Test: Tolerance Gauge Test

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

Print Time Estimated: 1 Hour 25 Minutes

Once the print began and lifted off the baseplate, I immediately began to worry about the quality of the print and the tolerances it could handle. I was worried that my calculated measurements were either inaccurate, rendering my prediction and test as a whole useless. Within the video below, near the end, you can see me begin to zoom in on the best-case pins, trying to observe the gaps between them. In the moment, I was concerned that either the printer or the settings weren't optimized to achieve best tolerance results.


<video controls width="100%">
  <source src="videos/IMG_5829%20(1).mov" type="video/quicktime">
</video>











## Objective


Elephant foot setting: 2 mm 

No supports
No need for scale, modeled correctly

## Analyze


## Decide


## Communicate

