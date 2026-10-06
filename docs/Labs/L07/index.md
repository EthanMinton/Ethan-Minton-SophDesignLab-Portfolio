# Lab 7: Linkage Mechanisms

## Research 

### Compliant Four-Bar Linkage for a Robotic Finger

The first mechanism I researched was a compliant four-bar linkage that was developed for a robotic finger. This mechanism was published as a patent application in 2022 by Aadeel Akhtar, Timothy Bretl, and Kyung Yun Choi, and is designed to improve the durability of robotic and prosthetic fingers. The main reason this mechanism was developed was that traditional four-bar linkages use rigid links and pin joints that can be damaged when the finger experiences an impact from the side. The compliant version uses a monolithic structure with a flexible joint section, allowing the mechanism to still move similarly to a traditional four-bar linkage while being able to flex when an unexpected force is applied.

The basic idea behind the design is that an actuator provides the input motion, which is transferred through the linkage and causes the robotic finger to bend similarly to a human hand. But instead of having every connection behave like a traditional rigid pin joint, one of the joints can flex as part of the material itself. This allows the mechanism to absorb some of the unexpected movement instead of immediately transferring the entire load into a small joint. The mechanism can therefore provide the motion of a normal four-bar linkage while also giving the finger additional flexibility.

<img width="1449" height="1055" alt="US20220183862A1-20220616-D00000" src="https://github.com/user-attachments/assets/d6e50f86-c5fc-4d1d-bb9c-b9976e59943e" />

One industry where this could be used is obviously the prosthetics industry. The mechanism was specifically designed around robotic and prosthetic fingers, where the fingers need to bend normally but also need to survive accidental impacts from the user. A second industry that could use this type of mechanism is robotics and automation. Robotic grippers and fingers could use the compliant linkage when they need to interact with objects without being as vulnerable to unexpected contact or collisions. The mechanism could be especially useful when the robot is working around people or handling objects where some sort of flexibility is beneficial.

### Center-Driven Planar Closed-Loop Mechanism

The second mechanism I researched was a group of center-driven planar closed-loop mechanisms based on an angulated four-bar linkage. This research was published in Mechanism and Machine Theory in 2023 by Matthijs J. J. Zomerdijk and Volkert van der Wijk. The researchers used an angulated four-bar linkage as the starting point and developed several different mechanisms from it, including a described multi-bar mechanism, a center-driven double-ring mechanism, and a deployable multi-arm mechanism. 

The main idea behind this mechanism is to use the motion of an angulated four-bar linkage to create controlled extension, contraction, and deployment. Depending on the configuration, the links can move between different shapes as the driving angle changes. One of the mechanisms described in the research can change between an extended and contracted shape, while another uses multiple arms that can be deployed from a compact configuration. This makes the linkage useful when a mechanism needs to change its overall shape while still being controlled by a relatively simple input motion.

<img width="550" height="364" alt="image" src="https://github.com/user-attachments/assets/e723183a-852f-4451-b301-6dcac6ad47c6" />

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


The next step was creating a new sketch on the top face of the base model and sketching 3 circles with equal diameter so that their dimensions are proportional.

<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/f3b888dc-fce4-4a6a-ad1c-f9a36a48eeb8" />

With the middle circle being centered on the center of the rectangular base, utilizing the point you see at the bottom. The other 2 secondary circles were both constrained to be 0.60 inches away from the other middle sketch. They were all then given a diameter of 0.15 inches. 

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

Similar to the link, I chose to perform the initial sketch on the top plane just for consistency.
<img width="1646" height="985" alt="image" src="https://github.com/user-attachments/assets/05a736ad-bae0-42fe-9406-a1e51fdaf3c6" />


With the initial linkage having a diameter of 0.15 inches, I followed up with a sliding pin diameter of 0.14 inches. NOTE: I will elaborate more on the determination of this value at the end of this section.

<img width="1647" height="986" alt="image" src="https://github.com/user-attachments/assets/4db518bb-a3ec-4dc8-8f00-d1d2da98e189" />

Once the simple circular sketch was completed I then extruded the Pin by 1.5 inches, this value was considerably arbitrary with it primarily being me determining the distance I wanted each side of the linkage to be from the other. 

<img width="1917" height="1012" alt="image" src="https://github.com/user-attachments/assets/b13b8a95-47b9-4a90-912e-73fee48b71e2" />

Finalized Part: 
<img width="1643" height="935" alt="image" src="https://github.com/user-attachments/assets/5ace4a6a-7860-4c75-a4a4-2763ff6689f9" />

The diameter of the sliding pin was determined to be 0.14 inches.  This was from the personal information that I had gathered from Lab 4, as although the 0.01 reduction had not allowed for a pin to be pushed through, I was able to observe that, despite the fact, the printer was able to print them independently without merging the walls completely. This led to the conclusion that if they are printed separately, the pin could be inserted with a tight enough fit that will prevent sliding out while also allowing for the links to slide together. Initially, I considered printing with a reduction of 0.02 tolerance but felt that the biggest issue I could run into is that the pins are too thick and will slide out too easily.

I decided that the best case would be to do the 0.01 inch reduction and iterate if necessary.

### Interference Pin 

For the interference pin, I decided to create a copy of the model of the sliding pin and modify the diameter of the sketch. For the pincher, I wanted to avoid any movement and decided that finding a middle between a sliding fit and a non-clearance fit would be an interference fit. I decided that to do this, I must increase the diameter by 0.005 inches, or 5 thou, to 0.145
<img width="1648" height="982" alt="image" src="https://github.com/user-attachments/assets/92a5bba2-2613-40ad-9c82-ed37508369d4" />

The greatest alternative here was considered doing a 0 tolerance and dimensioning it at 0.15 inches. The reason I decided against doing a 0 tolerance was that the likelihood of the print expanding after releasing the filament is very high, meaning that in the case of doing a press fit between the materials, they would likely yield and break before they are able to connect completely. The 0.145 inches felt like a safer option; they had a higher likelihood of working without the requirement for iteration. I will preface that if iteration is required, this part will be the likely culprit due to the more major unknowns.


### Pincher 

Similar to the rest of the sketches I decided to utilize the top plane to create the initial sketch of the pincher.
<img width="1637" height="982" alt="image" src="https://github.com/user-attachments/assets/e16ebc9b-a059-470e-82bc-c9f24a11df40" />

I then created a simple sketch and dimensioned it for the basic shape. To elaborate more, the dimensions here don't hold any real weight other than to get the rough shape I am going for. I wanted to ensure it was the same width and length as the links at 0.25 inches and 1.5 inches, respectively. The height of the triangle and the length of the non-triangle space were chosen to get a sharper shape without having its teeth be too long.

<img width="1645" height="985" alt="image" src="https://github.com/user-attachments/assets/27972bf0-2f49-421d-a55a-5b81c20edd9d" />

Once the sketch was completed, I then extruded the model by 0.7 inches. This value of thickness was determined by the total length of the pins at 1.5 inches, minus 2 sets of links on each side that sum to 0.8 inches. This leaves us with 0.7 inches of clearance that the pincher can occupy without overlap.

Note that once the model is completely assembled, this decision becomes clearer.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/6bbf1b07-e796-4434-8eb5-55143edcded6" />

Similar to the lengths, to avoid any sharp corners, I filleted the free corners at a radius of 0.20 inches.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/2841e177-64b8-4313-a7f8-842fd1ef5a18" />

I then created a sketch on the top surface of the model and produced a circle with a diameter of 0.15 inches, similar to that of the links. I then centered the circle at the end of the model so that it can easily attach to the interference pins.

<img width="1646" height="981" alt="image" src="https://github.com/user-attachments/assets/4e216fe4-8a4a-480c-aa88-b4da535e1a8b" />

This circle was extruded through the entire part, similar to the links.

<img width="1646" height="982" alt="image" src="https://github.com/user-attachments/assets/ef53949b-464c-4cb3-9c95-8a418e8319fa" />

 ### Assembly 
 
In order to ensure and visualize the model, I decided to assemble it with the final product seen below. This was a lot of help in visualizing how all of the parts come together once they have been printed. As you can see, the extruded value of the pincher fits perfectly between the 2 links on the side. A link to the Assembly file and all of the CAD models are found below. I do want to preface that the model of the assembly contains a lot of the different parts. 

<img width="1646" height="938" alt="image" src="https://github.com/user-attachments/assets/4cf1d6a9-35ac-4d3c-8d12-f766a2979685" />

| Component | Function | Obtaining |
| :--- | :--- | :--- |
| **Link** | The Basic Link acts as the main body for keeping the entire structure together and performing the transfer of force when applied. | 3D Printed - Count of 8 |
| **Sliding Pin** | The pin found within the main body between the different links that allows them to slide around each other when force is applied. | 3D Printed - Count of 6 |
| **Interference Pin** | The pin found at the very end of the body, connected to the end links and the pinchers; these interference pins are not supposed to move so that the pincher doesn't deflect when grabbing something. | 3D Printed - Count of 2 |
| **Pincher** | These are the pinchers; they are the end caps that are the utility of the structure. They are meant to be able to grab things once a force is applied to the opposite end as they are clamped down. | 3D Printed - Count of 2 |

## Print Settings

Utilizing the STEP files as previously mentioned in other labs, I was able to upload all of the models into a single plate to be printed. But before slicing, I had to modify a few key settings.

Due to the sheer scale and size of the print. As well as the use of a press fit, I decided that the best way to set the infill is at 10% honeycomb so that any deflection needed can be used to properly ensure our model can be assembled correctly.

<img width="1637" height="262" alt="image" src="https://github.com/user-attachments/assets/953fbad8-c446-4107-a9d0-b4b552257b41" />

For similar reasons, I reduced the perimeter to 2 (which is typically set at 3) so that the model is able to properly flex. 

<img width="1616" height="182" alt="image" src="https://github.com/user-attachments/assets/c06fdaa3-c456-4aad-88f7-0b02a0ee97e6" />

We were asked to use the Elephant foot compensation setting, which I set to 1 mm. This should allow for any flattening on the model's bottom to be compensated for, preventing any major issues with the tolerancing I had already set. 

<img width="1605" height="32" alt="image" src="https://github.com/user-attachments/assets/accb6a15-4118-4b09-87d0-4c597c90645a" />

I also added a brim to the model to help minimize any nozzle issues.

<img width="1632" height="140" alt="image" src="https://github.com/user-attachments/assets/034b0aef-d32c-45e0-a23a-db4e12d22e2c" />

Another big and new setting I utilized was setting the Seam Alignment to random to help prevent any stacking from the printer running over and raising within the same position. This should leave a more scattered and bumpy surface finish but should allow for better tolerancing and minimizing issues.

<img width="1617" height="35" alt="image" src="https://github.com/user-attachments/assets/a50554d8-a499-4718-9c11-d4b538db192b" />

Outside of the Specific Settings that I had altered, I chose to utilize Prusa PETG as my filament and utilizing a 0.4 Nozzle Prusa Core One printer. I also had activated the supports everywhere, but it seems that it wasn't needed after slicing. The last major decision that I made was scaling all of the parts up by 150%; I found that the models were extremely tiny and would have likely resulted in parts being too flimsy or struggling to stay together. Thankfully, the Scale feature is universal and scales all dimensions.


<img width="1917" height="1138" alt="image" src="https://github.com/user-attachments/assets/e4612719-b9a0-4b41-a724-d0d7b4a49ad2" />


Once the print was sliced, it was estimated to take 2 hours and 59 minutes using 2.06 in^3 of filament or 42.97 grams. 

<img width="1917" height="1027" alt="image" src="https://github.com/user-attachments/assets/ff553226-7c32-4834-8ee6-b4958f196250" />

G-code Utilized:
<img width="927" height="67" alt="image" src="https://github.com/user-attachments/assets/43163d0c-79b9-47da-9f5f-f39f996f23ad" />

## Print 

I had utilized the PC-16 printer within the Duke Lab, which was supplied with a Gold PETG filament. I attempted to preheat the printer with PETG, as I know how long it takes to preheat. Once I uploaded the model, it began to print all of the bases. 

**First Image Showcasing Early Print:**
<img width="4032" height="3024" alt="IMG_0002" src="https://github.com/user-attachments/assets/ce171d29-6320-45bf-b9eb-b6e27d468036" />


**Video Showcasing Print Process and Infill**
<video src="https://github.com/user-attachments/assets/43a1f168-de7b-43dc-bd72-5bb6dffe866b" controls style="max-width: 100%;">
</video>

**Last Image Showing Finished Print:**
<img width="4032" height="3024" alt="IMG_0004" src="https://github.com/user-attachments/assets/71697dcd-63bc-407b-b632-c4ae52823b27" />

**Final Print Screen** 
<img width="4032" height="3024" alt="IMG_0006" src="https://github.com/user-attachments/assets/a9d25d59-9023-4778-be30-34f991fa634d" />

True Time taken by Print: 3 Hours 8 Minutes

## Lessons Learned 

This project took roughly 11 hours of dedicated time to complete. The research took roughly 2 hours and 30 minutes to find all of the sources, write down the needed information, and cite them properly. The CAD took the most time with all 4 of the parts, and then the assembly took a total of 4 hours. Ensuring that all of the dimensions would line up before the assembly is considerably tedious, but it doesn't ruin time spent on documenting because you made a critical mistake early on and have to fix it. Slicing in total likely took around 30 minutes, with changing critical settings asked for from us and properly orienting the models so they could be properly printed. Once I had started the printing, it took around 3 hours flat, but I had utilized this time to complete my documentation and add all finalized details. Post-processing and final documentation roughly took an hour. This was a total of 11 hours, which is roughly what I had expected; in my head, it was around 12 hours.

I wouldn't say I had any critical failures or struggles that were detrimental to the process, as I had thankfully been able to utilize previous labs for information I needed about the behavior of my fits. The biggest issue and mistake that I had made was the scaling of my dimensions when modeling; I had completely failed to properly visualize how small the scales I was adding to my models were. Thankfully, this issue was easily resolved within Prusa, as it contains a universal scale feature that is able to scale all of the parts up by 150%. Meaning that the effort I had put into the different dimensions wouldn't have been for nothing due to a simple error.

Although my tolerances had worked out for the print, I do want to note the extreme difficulty of inserting the interference pins into the pinchers of the model. Most of the assembly time was spent inserting these 2 pins, showing that a fit can function as intended while still being considerably difficult to assemble. I chose the tighter fit to prevent the pinchers from moving independently when grabbing something, but it also made assembly much more tedious than I expected. If I were to print this again, I would consider reducing the final printed pin diameter and testing how much fit I can allow without making assembly extremely difficult. To estimate the change would be between 0.145 nd 0.140 inches. I would likely do a binary style test to isolate what the best fit would be with minimized pin sizes that easily allow for insertion while also preventing any sliding, hopefully around 0.1425 inches.

### Final Assembly and Test

**Final Assembly**
<img width="4032" height="3024" alt="IMG_0008" src="https://github.com/user-attachments/assets/6b10a821-49b9-4768-b93b-f16a8a85e274" />

**Video Test**
<video src="https://github.com/user-attachments/assets/4048def8-123d-40c2-a2be-b9b5ee9d4fd0" controls style="max-width: 100%;">
</video>


## Resources 

[https://www.sciencedirect.com/science/article/pii/S0094114X22003767?utm](https://www.sciencedirect.com/science/article/pii/S0094114X22003767?utm)

[https://www.mdpi.com/2076-0825/11/5/131?utm](https://www.mdpi.com/2076-0825/11/5/131?utm)

[https://patents.google.com/patent/US20220183862A1/en](https://patents.google.com/patent/US20220183862A1/en)

[Link_LAB7.SLDPRT](Link_LAB7.SLDPRT)

[Pin_LAB7.SLDPRT](Pin_LAB7.SLDPRT)

[Pin_tight_LAB7.SLDPRT](Pin_tight_LAB7.SLDPRT)

[Pincher_LAB7.SLDPRT](Pincher_LAB7.SLDPRT)

[Lab7_Assembly.SLDASM](Lab7_Assembly.SLDASM)



