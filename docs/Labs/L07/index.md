# Lab 7: Linkage Mechanisms

## Research 

### Compliant Four-Bar Linkage for a Robotic Finger

The first mechanism I researched was a compliant four-bar linkage that was developed for a robotic finger. This mechanism was published as a patent application in 2022 and was designed to improve the durability of robotic and prosthetic fingers. The main reason this mechanism was developed was because traditional four-bar linkages use rigid links and pin joints that can be damaged when the finger experiences an impact from the side. The compliant version uses a monolithic structure with a flexible joint section, allowing the mechanism to still move similarly to a traditional four-bar linkage while being able to flex when an unexpected force is applied.

The basic idea is that an actuator provides the input motion, which is transferred through the linkage and causes the robotic finger to bend. Instead of having every connection behave like a traditional rigid pin joint, one of the joints can flex as part of the material itself. This allows the mechanism to absorb some of the unexpected movement instead of immediately transferring the entire load into a small joint. The mechanism can therefore provide the motion of a normal four-bar linkage while also giving the finger some additional flexibility.

Need to insert image/sketch of the compliant four-bar linkage here.

One industry where this could be used is the prosthetics industry. The mechanism was specifically designed around robotic and prosthetic fingers, where the fingers need to bend normally but also need to survive accidental impacts. A second industry that could use this type of mechanism is robotics and automation. Robotic grippers and fingers could use the compliant linkage when they need to interact with objects without being as vulnerable to unexpected contact or collisions. The mechanism could be especially useful when the robot is working around people or handling objects where some flexibility is beneficial.

### Center-Driven Planar Closed-Loop Mechanism

The second mechanism I researched was a group of center-driven planar closed-loop mechanisms based on an angulated four-bar linkage. This research was published in Mechanism and Machine Theory in 2023. The researchers used an angulated four-bar linkage as the starting point and developed several different mechanisms from it, including a multi-bar mechanism, a center-driven double-ring mechanism, and a deployable multi-arm mechanism.

The main idea behind this mechanism is to use the motion of an angulated four-bar linkage to create controlled extension, contraction, and deployment. Depending on the configuration, the links can move between different shapes as the driving angle changes. One of the mechanisms described in the research can change between an extended and contracted shape, while another uses multiple arms that can be deployed from a compact configuration. This makes the linkage useful when a mechanism needs to change its overall shape while still being controlled by a relatively simple input motion.

need to insert image/sketch of the center-driven linkage here.

One industry where this could be useful is the robotics industry, since the research specifically identifies potential applications of these mechanisms in robotics. A deployable linkage could allow a robot to have a compact configuration when it is not being used and then expand when additional reach or workspace is needed. Another possible industry is aerospace, where mechanisms that can fold into a smaller configuration and then deploy can be useful because available space and weight are major design considerations. The same basic idea could also be useful for deployable mechanical structures where the mechanism needs to change between a compact and expanded configuration.

## CAD Design 

### Purpose 

The design that I wanted to go for was a linkage mechanism that can transfer an applied force to one end through the linkages to a "pincher" at the end. This is primarily to test how I am able to design around different types of fits, utilizing the tolerances the Printers are capable of to design the linkage mechanism. Going into the design section, I took a lot of notice of my previous labs, such as Lab 4 with the Cylinder_tolerance test finding that reducing my measurements by roughly 0.01 inches or 10 thou would provide a fit that would be able to slide while also not falling out of the links. The pincher itself is to be able to showcase the product of the effort and design that was put into the linking mechanism. One of the greatest difficulties that I am going to have to work around is the design of the different pins themselves; with a pin being too loose, it'll require me to ensure that they don't slip out with just the basic application of force. But with a too-tight tolerance, it doesn't allow for our models to slide. 

### Link 


For the Link I decided to utilize sketching onto the top plane; this is not a significant decision as in Pruse models can be oriented around.
<img width="1647" height="983" alt="image" src="https://github.com/user-attachments/assets/bf8da211-6e2e-4146-a8ba-44a03f2520f6" />

Creating a simple rectangular sketch with dimensions of 1.50 inches by 0.25 inches; this is the general shape of the link. To note, commenting on this later, this is more like the proportion distributed, as all dimensions will be scaled up in PrusaSlicer to achieve a better size.
<img width="1632" height="983" alt="image" src="https://github.com/user-attachments/assets/bf0dcb90-12c3-4bd3-a691-45dc44ed8f60" />


Once the base sketch was completed, I extruded it by 0.2 inches.
<img width="1917" height="987" alt="image" src="https://github.com/user-attachments/assets/6e788bbb-df4d-438a-ba45-68335e278dcd" />


The next step was creating a new sketch on the top face of the base model and sketching 3 circles with equal radii so that their dimensions are proportional.

<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/f3b888dc-fce4-4a6a-ad1c-f9a36a48eeb8" />

With the middle circle being centered on the center of the rectangular base, utilizing the point you see at the bottom. The other 2 secondary circles were both constrained to be 0.60 inches away from the other middle sketch.

<img width="1643" height="937" alt="image" src="https://github.com/user-attachments/assets/a43eac0b-cf27-48d4-a499-a794b15f05d3" />

Once the sketch was completed, the circles were extruded completely through the base model.
<img width="1917" height="1016" alt="image" src="https://github.com/user-attachments/assets/78ffdb99-d1ed-4878-bd43-68194eda123c" />

To avoid having such a rigid rectangular model, I added a fillet to the 4 corners at a radius of 0.20 inches. 
<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/f3efcc97-c68c-4af0-b801-df27836d65c7" />

Finalized Part:
<img width="1646" height="937" alt="image" src="https://github.com/user-attachments/assets/771a55b5-abb3-423b-9a83-d54745b27a7c" />

Starting with the link, I wanted to ensure that the design would function through most key situations when force is applied. The 2 primary design decisions I was thinking of making were the number of pin holes that would be included. Traditionally, a 2-hole model was considered, with each being found on the end of the model. This would reduce time cost, material cost, and complexity. But I also considered a 3-hole model, taking inspiration from the link design from our TA Nicholas de Souza Teixeira, which would elaborate on the design by preventing any awkward flexure or movement from the links and pins when force is applied. But this is at the cost of time, material, and simplicity.  

Honestly, I have the time, material, and ability to perform the 3-holed link. As seen above, this was the chosen design to reduce failure and incorrect sliding from the links.

### Sliding Pin

Starting with the pin I decided to again sketch onto the top plane 
<img width="1646" height="985" alt="image" src="https://github.com/user-attachments/assets/05a736ad-bae0-42fe-9406-a1e51fdaf3c6" />

I then sketched a circle with a radius of 0.14 inches, based on my result for lab 4 (talk more about)

<img width="1647" height="986" alt="image" src="https://github.com/user-attachments/assets/4db518bb-a3ec-4dc8-8f00-d1d2da98e189" />

I then extruded it by 1.5 inches 

<img width="1917" height="1012" alt="image" src="https://github.com/user-attachments/assets/b13b8a95-47b9-4a90-912e-73fee48b71e2" />

Final product here 
<img width="1643" height="935" alt="image" src="https://github.com/user-attachments/assets/5ace4a6a-7860-4c75-a4a4-2763ff6689f9" />

### Interference Pin 

For the pincher, I wanted to avoid any movement, so I made a copy and increased the radius by 5 thou (0.005 inches). 
<img width="1648" height="982" alt="image" src="https://github.com/user-attachments/assets/92a5bba2-2613-40ad-9c82-ed37508369d4" />


### Pincher 
Sketch on top plane
<img width="1637" height="982" alt="image" src="https://github.com/user-attachments/assets/e16ebc9b-a059-470e-82bc-c9f24a11df40" />

I then created a simple sketch and dimensioned it for the basic shape. remind explain more
<img width="1645" height="985" alt="image" src="https://github.com/user-attachments/assets/27972bf0-2f49-421d-a55a-5b81c20edd9d" />

I then extruded it 0.7 inches (talk about how 2 links and 1.5 - 0.8 = 0.7)

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/6bbf1b07-e796-4434-8eb5-55143edcded6" />

For some artistic flare I added 0.2 radius fillits to the corners

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/2841e177-64b8-4313-a7f8-842fd1ef5a18" />

I then created a hole with dimensions below

<img width="1646" height="981" alt="image" src="https://github.com/user-attachments/assets/4e216fe4-8a4a-480c-aa88-b4da535e1a8b" />

Then extrude it through the entire part.

<img width="1646" height="982" alt="image" src="https://github.com/user-attachments/assets/ef53949b-464c-4cb3-9c95-8a418e8319fa" />

 ### Assembly 
 
In order to ensure and visuilizze the model I decided to assemble it togther with the final product seen below.

<img width="1646" height="938" alt="image" src="https://github.com/user-attachments/assets/4cf1d6a9-35ac-4d3c-8d12-f766a2979685" />

| Component | Function | Obtaining |
| :--- | :--- | :--- |
| **Link** | The Basic Link acts as the main body for keeping the entire structure together and performing the transfer of force when applied. | 3D Printed - Count of 8 |
| **Sliding Pin** | The pin found within the main body between the different links that allows them to slide around each other when force is applied. | 3D Printed - Count of 6 |
| **Interference Pin** | The pin found at the very end of the body, connected to the end links and the pinchers; these interference pins are not supposed to move so that the pincher doesn't deflect when grabbing something. | 3D Printed - Count of 2 |
| **Pincher** | These are the pinchers; they are the end caps that are the utility of the structure. They are meant to be able to grab things once a force is applied to the opposite end as they are clamped down. | 3D Printed - Count of 2 |
## Print Settings

Using press fit I leave the infill at 10% honeycomb so that the model can be pressed when needed.

<img width="1637" height="262" alt="image" src="https://github.com/user-attachments/assets/953fbad8-c446-4107-a9d0-b4b552257b41" />

For similar reasons, I reduced the perimeter to 2 so that the model is able to properly flex.
<img width="1616" height="182" alt="image" src="https://github.com/user-attachments/assets/c06fdaa3-c456-4aad-88f7-0b02a0ee97e6" />


Elephant foot compensation of 1 mm, I want to fit but also have clean models.
<img width="1605" height="32" alt="image" src="https://github.com/user-attachments/assets/accb6a15-4118-4b09-87d0-4c597c90645a" />

I also added a brim to the model 
<img width="1632" height="140" alt="image" src="https://github.com/user-attachments/assets/034b0aef-d32c-45e0-a23a-db4e12d22e2c" />

I also changed the seam alignment to random

<img width="1617" height="35" alt="image" src="https://github.com/user-attachments/assets/a50554d8-a499-4718-9c11-d4b538db192b" />

Some of the other settings I change is that I am using PETG, I scaled the model by 150%, and I am using a 0.4 Nozzle Prusa Core One printer. Although Supports were not needed I activated it just in case.


<img width="1917" height="1138" alt="image" src="https://github.com/user-attachments/assets/e4612719-b9a0-4b41-a724-d0d7b4a49ad2" />


Once sliced it was estimated to take 2 hours and 59 minutes.

<img width="1917" height="1027" alt="image" src="https://github.com/user-attachments/assets/ff553226-7c32-4834-8ee6-b4958f196250" />

G-code
<img width="927" height="67" alt="image" src="https://github.com/user-attachments/assets/43163d0c-79b9-47da-9f5f-f39f996f23ad" />

## Print 

Printer Number 16

## Analyze


## Decide

## Resources 

Akhtar, A., Bretl, T., and Choi, K. Y. “Compliant Four-Bar Linkage Mechanism for a Robotic Finger.” U.S. Patent Application US20220183862A1, published June 16, 2022.

Yang, T., Li, P., Shen, Y., and Liu, Y. “Center-driven planar closed-loop mechanisms based on an angulated four-bar linkage.” Mechanism and Machine Theory, Vol. 180, 2023, Article 105130.

Zomerdijk, M. J. J., and van der Wijk, V. “Structural Design and Experiments of a Dynamically Balanced Inverted Four-Bar Linkage as Manipulator Arm for High Acceleration Applications.” Actuators, 2022, 11(5), 131.

## Communicate

