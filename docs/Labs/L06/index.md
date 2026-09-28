# A6 – Design Fits for an artifact

## Objective

Create a snap fit that can snap fit around a selected object in class. I decided to select the Motor seen below, creating a snap fit design around the end of the shaft so it is able to properly transfer torque to a different system. This was considerably difficult, as PLA plastic is known for having very little yield strength when handling bending. Applying the proper pressure to the shaft without plastic deformation can be considerably difficult. The primary goal is to design the snap fit with the capability to attach itself to the shaft using pressure applied without that same pressure deforming our snap fit.

<img width="4032" height="3024" alt="IMG_5997" src="https://github.com/user-attachments/assets/3ae817a5-9d9e-4868-9ab5-7a3a246823e2" />

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

To begin constraining, I first began to utilize the previously recorded geometric constraints of the motors defining the deflection triangle height by the distance from the Shaft diameter divided by 2, for the radius. Resulting in a value of 0.2350 inches away from our axis. 

<img width="1918" height="885" alt="image" src="https://github.com/user-attachments/assets/be140229-fb02-4de5-9c9f-019ddbb0e12c" />

The next constraint performed was the gap between the deflection triangle and the lip stopper found above it. This gap is defined by the measured height of the bulb, which was measured at 0.2965 inches. 

<img width="1915" height="883" alt="image" src="https://github.com/user-attachments/assets/76d63262-72f6-42cf-bd8e-19101c106bab" />

The last of these sets is the distance from the flat surface of the gap between the 2 previously mentioned geometries; this used the measured bulb diameter divided by 2 to obtain the radius. This results in a value of 0.3128 inches, defining how far the snap-fit and the motor should snap together. 

<img width="1917" height="881" alt="image" src="https://github.com/user-attachments/assets/302cdb79-3ef7-4bda-8433-e178b6e3e1ba" />

I want to note that these values are without any tolerances initially; this is primarily because a core concept for this snap fit is that it needs to be tight enough to properly grasp the shaft and transfer applied torque. If any iterations are applied to improve the design they will be mentioned and applied to the model to ensure success. I just wanted to note that this is supposed to be extremely tight to apply pressure properly.

The step of the model is to define our geometric assumptions to calculate the length of the model. Starting with the thickness or the width of the beam, I initially chose to define the thickness as 0.15 inches. And assigned it to both dimensions, as you see in the screenshot below. I want to preface that assigning this dimension was extremely frustrating, as I attempted to make them both equal to each other, but every troubleshooting step altered something else. I spent roughly 25 minutes on this until I just decided to constrain both with the thickness value; it equates to the same parametric models when altered or regenerated. This value was selected to not require an overly thick model that would be too bulky when in use. 

<img width="1916" height="840" alt="image" src="https://github.com/user-attachments/assets/82d93b5f-eeb0-498a-aef3-c50541d2f4b7" />

The Base of the model is not a constraint that is defined by the predetermined geometry, with it being roughly the circumference of the cylinder divided by 4, the reason for the division will be elaborated on later. But the way we find the radius of the model is just by adding the bulb's diameter and the thickness of the model. When multiplied by Pi divided by 2, we find out the base is 1.22 inches.

To calculate the length we were required to make a couple of more assumptions such as the Modulus of Elasticity which I assumed to be roughly around 200,000 PSI this is based on the previous assignment where I found that the 340,000 PSI was a measure that over estimated its Modulus. It repeatively gave a length way over what was actually able to be bend without plastic defomration I selected a reduced value to prevent this issue. If more information is gather out of any test prints it will be noted for future projects. Deflection was defined by the difference between the Bulbs and shafts diameters divided by 2, due to using a revolve feature this is best way to find this value which equated to 0.08 inches. The final variable to assume for the length is the force applied, similar to the previous project, I assumed the force to be 1.5 lbf, a very small value that could be realistically applied by a human finger.

The equation below was used previously to calculate the length of a snap-fit with it being written out as "= ( ( "BASE" * "ELONG" * "THICK" ^ 3 * "DEFL" ) / ( 4 * "FORCE" ) ) ^ ( 1 / 3 )". This equation takes all the previously mentioned values and equates to a length of 2.2 inches.

Remind: Talk about length of height of model, photo in first sketch, with added offset

## Decide


## Communicate
Lesson learned

mention troubleshooting thickness dimension 
