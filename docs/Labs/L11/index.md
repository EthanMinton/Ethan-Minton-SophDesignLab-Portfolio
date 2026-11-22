# Lab 11 – Snap Fit Design for SLA Printing

## Objective

The goal of this assignment is to design and print a useful artifact with two or more parts that snap together using the Form 4. I plan to create a ring holder with flexible arms that allow a ring to slide over the hooks and stay on the holder. I will use the snap-fit guide to choose the geometry, prepare the parts in PreForm, and test the fit after washing and curing.

## Snap-fit Research

### Cantilever Snap Fit

For this design, I selected a cantilever snap fit. The arm bends during assembly so the hook can move past the edge of the other part and snap into place. Once connected, the arm should return close to its original position instead of staying bent. This allows the hook to hold the parts together without keeping the arm under constant bending stress.

### Geometry and Stress

The root of the arm is where the highest bending stress occurs. A sharp corner in this area makes the arm more likely to crack, so I added a fillet where the arm connects to the body. Figures 8 and 9 in the guide show the hook geometry and how the root radius affects stress concentration.

The guide also recommends tapering the arm to distribute strain more evenly. Table 1, Design 2 shows an arm that gradually decreases to half of its root thickness near the tip. I researched this option but kept a constant 0.10 in wall thickness in my model. I used the arm length, slots, and root fillets to provide flexibility while keeping the sections connected to the base.

<img width="1434" height="1002" alt="23144" src="https://github.com/user-attachments/assets/75baec21-4675-4357-b7d1-ccf11cdf57c5" />

### Deflection and Undercut

The undercut is the amount that the hook overlaps the edge holding it in place. Figure 12 shows how this overlap determines the required deflection for a simple snap fit. Increasing the undercut requires the arm to bend farther, which increases strain during assembly.

For a straight arm with a constant rectangular cross section, the small-deflection relationship is:

$$
\varepsilon_{\max} = \frac{3hy}{2L^2}
$$

| Symbol | Meaning |
| --- | --- |
| $\varepsilon_{\max}$ | Maximum bending strain |
| $h$ | Arm thickness |
| $y$ | Tip deflection |
| $L$ | Arm length |

A longer arm reduces the strain for the same deflection. A thicker arm is stiffer and requires more force to bend. This equation applies to a constant rectangular cross section. It provides an estimate for my curved sections rather than accounting for their full geometry.

### Assembly and Removal

The assembly force depends on the arm stiffness, required deflection, friction, and hook entry angle. Figure 17 shows how the entry angle and friction affect the force needed to connect the parts.

I used an angled entry ramp so the mating part can push the hook aside during assembly. The openings between the arms provide access to press them inward for removal. The hook overlap provides retention, while clearance around the straight body allows the ring to slide.

### SLA Resin Properties

The amount the arm can safely bend depends on the resin used and its properties after curing. Table 2 lists strain values for specific engineering plastics, so those values cannot be directly applied to the SLA resin. Elongation at break also does not represent a safe strain for repeated assembly.

The selected resin needs enough flexibility to handle the required deflection without cracking. A longer arm, rounded root, and limited undercut can help reduce strain. The printed fit still needs to be tested after washing and curing because the material properties and finished dimensions affect how the parts connect.

## Design

### Ring Holder

I used equations in SolidWorks to estimate the deflection and link the main sketch dimensions. I used an assumed force of 0.705 lbf per section and an assumed Young’s modulus of 217,557 psi. Each section was treated as a rectangular cantilever with a width equal to one-quarter of the circumference before subtracting the cuts. This gave an estimated deflection of 0.13 in using the simplified beam equation.

<img width="1505" height="521" alt="image" src="https://github.com/user-attachments/assets/14c4d20a-cd48-4bf8-bb3f-a6344e28dc14" />

I started with a cross-sectional sketch that was 2.00 in tall, with a 1.64 in arm length and a 0.10 in wall thickness. The hook extends outward by 0.13 in and has a 45° angle to help push the arms inward when connecting the parts. The wider base holds the arms together and provides a stop for the mating part.

<img width="1616" height="955" alt="image" src="https://github.com/user-attachments/assets/6506e129-b38a-4394-bcbd-b448df0526b4" />

I revolved the sketch 360° around the centerline to create the hollow body. This created the upper hook and bottom base in one feature. After creating the revolved shape, I could cut the body into separate sections that would be able to bend inward.

<img width="1617" height="957" alt="image" src="https://github.com/user-attachments/assets/b13eee14-4c16-4c3c-b6ff-4b8268ae194c" />

I created a 0.15 in wide rectangle on the Front Plane that extended from the top of the hook down to the base. This sketch was used to create the first openings in the body while keeping the bottom ring connected.

<img width="1612" height="956" alt="image" src="https://github.com/user-attachments/assets/86609395-9e3b-47f8-94b7-e9454af9ccfd" />

I used an extruded cut through both directions to remove the material from the rectangular sketch. This created openings on opposite sides of the body and split the upper hook while leaving the base intact.

<img width="1616" height="955" alt="image" src="https://github.com/user-attachments/assets/873b9c58-ba59-4d3b-bef3-b69d3b597c5e" />

I created a second 0.15 in wide rectangle on the Right Plane. This sketch was perpendicular to the first one so the next cut would divide the body into four sections.

<img width="1616" height="961" alt="image" src="https://github.com/user-attachments/assets/56f2e305-997e-4567-85b2-b6e0b0f58952" />

I used another extruded cut through both directions to create the four arms. Each arm stays connected to the base but has space on both sides to move inward during assembly. These cuts allow the sections to bend like cantilever snap arms instead of keeping the wall as one continuous ring.

<img width="1621" height="953" alt="image" src="https://github.com/user-attachments/assets/8fee37d6-9fd1-42a1-8080-29e328125963" />

I added a 0.10 in fillet to the four edges where the arms connect to the base. This rounds the sharp corners at the roots to help reduce stress concentration when the arms bend, following the recommendation from the snap-fit guide.

<img width="1617" height="956" alt="image" src="https://github.com/user-attachments/assets/ab8e1965-1536-4483-8ac5-0bfce44259f3" />

The completed component has four arms with angled hooks and rounded roots. The arms bend inward as the hooks pass through the mating opening, then move back outward to hold the ring on the holder. The slots provide room for movement and access to compress the arms for removal.

<img width="1616" height="955" alt="image" src="https://github.com/user-attachments/assets/be33600e-f17d-4c7f-ab1f-dd2e85c9ef5c" />

### Test Ring

I created a test ring to check how the ring holder would work with a separate part. I started with a curved cross-sectional sketch that was 0.25 in tall, with a radial dimension of 0.40 in from the centerline. The rounded profile gives the ring a smoother shape instead of sharp outside edges.

<img width="1617" height="960" alt="image" src="https://github.com/user-attachments/assets/23123cdd-47e3-4fc4-8e8d-e8b6d4303f03" />

I revolved the sketch 360° around the centerline to create the ring. This kept the cross section consistent around the entire part and created the opening that would pass over the holder.

<img width="1617" height="956" alt="image" src="https://github.com/user-attachments/assets/40a06899-fec5-42fe-b516-97182371a872" />

The completed test ring pushes over the angled hooks by bending the holder’s four arms inward. Once the ring passes the hooks, the arms return outward and retain it on the holder. This part was used to check the fit after printing and curing.

<img width="1620" height="951" alt="image" src="https://github.com/user-attachments/assets/f05e0543-342c-42dd-a01f-a3e4f8b3eb13" />

### Assembly

I brought the ring and holder into an assembly to show how the two parts connect. The ring slides over the top of the holder and pushes against the 45° entry ramps. Once the ring passes the hooks, the arms can return outward. The shoulders underneath the hooks retain the ring, while the wider base prevents it from sliding off the bottom.

<img width="1616" height="992" alt="image" src="https://github.com/user-attachments/assets/58f3ac51-f9e6-4bad-9c5b-1dc6103051a0" />

I used a 0.10 in wall thickness and a 1.64 in arm length to balance flexibility and strength. The 0.13 in hook projection provides the retaining shoulder, although the actual overlap and required deflection depend on the ring’s opening. Following Figures 8 and 9 of the Snap-Fit Design Guide, I added 0.10 in root fillets to reduce stress concentration where the arms connect to the base. The arms have a constant wall thickness rather than a taper.

The main geometry adjustments were dividing the revolved wall with two perpendicular 0.15 in cuts and rounding the roots. The cuts give the arms room to move independently, while the connected base supports all four sections. I kept the walls at a consistent thickness instead of making the arms thinner throughout.

The separated view shows the ring above the holder and the direction it moves during assembly. The design is intended to be separable by pressing the arms inward until the hooks clear the ring, then lifting the ring off. This allows removal without forcing the ring backward over the retaining shoulders.

<img width="1620" height="957" alt="image" src="https://github.com/user-attachments/assets/f1a8f1de-dc74-4d4a-a95d-9ffc8364b06f" />

## Preprocessing

I kept the same basic support settings in PreForm. The touchpoint size was 0.55 mm, with the overhang, stabilization, and reinforcement densities set to 1.00. The overhang angle was 18°, and internal supports were enabled. The contact points around the snap arms and mating surfaces needed careful removal so they would not affect the fit.

<img width="472" height="827" alt="image" src="https://github.com/user-attachments/assets/9b99c931-a637-41a6-a187-f3585029388f" />

The layer selection screenshot shows 0.100 mm selected, while the build plate screenshot shows the job set to 0.050 mm. I documented 0.050 mm as the job setting. This provides smaller steps in the vertical direction for the curved ring and angled hooks. I kept the basic print profile set to Default.

<img width="742" height="322" alt="image" src="https://github.com/user-attachments/assets/9527089a-1241-4884-bbda-bb7f9df6cb94" />

I prepared the parts for the Form 4 named HumorousPetrel using Grey V5 resin. The shared build plate contains four models, including my ring holder and test ring alongside another pair of components. The parts are spaced apart to provide room for their supports and rafts.

The holder is tilted on supports to avoid placing the entire circular base flat against the platform. The ring is supported separately so both components can be cleaned up before assembly. Orientation affects the surface finish, support locations, and dimensional accuracy.

SLA resin parts are generally close to isotropic, meaning their material properties are similar in different directions. This differs from FDM parts, where the layer direction has a larger effect on strength. The holder itself is still more flexible in certain directions because of the four separate arms.

The modeled arm thickness is 0.10 in, or 2.54 mm. Using the holder’s 0.28 in inner radius and 0.10 in wall thickness gives a body radius of 0.38 in. Compared with the test ring’s nominal inner radius of 0.40 in, this gives approximately 0.02 in of radial clearance around the straight body. The hooks extend beyond the body to retain the ring, so this clearance is separate from the deflection needed to pass over the hooks.

PreForm estimated a print time of approximately 1 hour and 49 minutes and a resin volume of 20.74 mL for the entire shared job. These totals include the other components on the plate. PreForm still showed one unsupported minimum in this screenshot.

<img width="1917" height="1017" alt="Screenshot 2026-11-09 170051" src="https://github.com/user-attachments/assets/294c97e3-af05-4584-8a8a-c218e5f80df4" />

## Post-Processing

I used a scraper to remove the printed rafts from the build platform while keeping the supports attached. After washing and curing, I removed the supports using pliers and my hands. Support removal and cleanup took approximately 15 minutes. I worked carefully around the arms and ring to avoid damaging the mating surfaces.

<img width="4032" height="3024" alt="IMG_0386" src="https://github.com/user-attachments/assets/2d476988-9b9c-4d74-8965-b6a77ab2907b" />

The completed print was still attached to the build platform when it came out of the Form 4. The supports held the components in their printing orientations until they were ready for post-processing.

<img width="4032" height="3024" alt="IMG_0383" src="https://github.com/user-attachments/assets/320a50ad-dc81-4e3b-b703-ebad46646772" />

I washed the parts in 99% IPA for 10 minutes to remove uncured resin. After washing, the parts appeared to dry quickly, and I moved them into the curing chamber almost immediately. I did not record a separate drying time.

<img width="3024" height="4032" alt="IMG_0385" src="https://github.com/user-attachments/assets/b53f125d-d6d5-499f-b73e-c8a090931332" />

I cured the parts using a custom 10-minute cycle with preheat turned off. The display showed approximately 25°C during curing. After curing, the arms were still very flexible, and the ring slid over them relatively well. The main issue was the tips bumping into each other as the arms bent inward during insertion. I did not compare the fit before and after curing, so I could not isolate how much curing changed it.

<img width="4032" height="3024" alt="IMG_0388" src="https://github.com/user-attachments/assets/21c3a2c7-27e2-49cd-b4de-a68beacb9d64" />

The ring could slide along the holder, which was intentional because I wanted movement after assembly. The surfaces were mostly smooth, but some corners and edges were very sharp. There was also minor cracking around these sharp corners. This showed that the rounded roots did not remove every area where cracking could occur.

Compared with PLA printed through FDM, SLA resin requires washing and curing, and its material properties are generally less dependent on layer direction. Flexibility and resistance to cracking still depend on the specific resin and geometry. In this print, the arms were flexible while some sharp corners still cracked.

The smooth surfaces allowed the ring to slide as intended, but this was a fit test rather than a dimensional measurement. The interference between the tips showed that the space available during bending also matters, even when the ring can pass over the hooks.

## Validation

The printed ring and holder worked together as intended. The arms were flexible enough for the ring to slide over the hooks, and the hooks retained the ring after assembly. The ring could slide along the holder, which was intentional because I wanted it to have movement instead of being held tightly in one position.

The main issue during insertion was the tips bumping into each other as the arms bent inward. The assembly still worked without further adjustments. For another version, I would make the holder wider to provide more space between the prongs during bending and round the remaining sharp edges.

<video src="https://github.com/user-attachments/assets/9decdb64-424a-41a5-b91c-0e1283b8785f" controls style="max-width: 100%;">
</video>

The surface finish was mostly smooth, but the corners and edges around the hooks were very sharp. Minor cracking occurred around some of these corners. Rounding these areas would help improve durability and make the part more comfortable to handle.

<img width="4032" height="3024" alt="IMG_0473 (1)" src="https://github.com/user-attachments/assets/8a1498a6-942e-4190-9823-11e135d39863" />

## Lessons Learned

I learned that having flexible arms does not guarantee that the entire snap fit will move without interference. The arms could bend far enough for assembly, but the tips contacted each other during insertion. I needed to consider the space between the arms while they were bent, along with the clearance between the ring and holder.

The print also showed that sharp corners can still crack even when the rest of the part is flexible. Adding fillets at the roots created a smoother connection to the base, but the hook edges also needed attention. In another version, I would round these edges and increase the space available for the prongs to move.

I learned that SLA tolerances need to be checked after washing, curing, and support removal. The ring had the sliding movement I wanted, but I still needed to test the printed parts to find the interference between the tips. Orientation and support placement also affected where cleanup was required, especially near the mating surfaces and flexible arms.

Compared with FDM snap fits, SLA requires additional washing and curing, and the selected resin has a large effect on flexibility. This print had mostly smooth surfaces and flexible arms, but the cracking showed that a smooth finish does not mean every area will hold up during use.

The project took approximately 8 hours from start to finish, including research, modeling, print preparation, printing, post-processing, testing, and documentation. Resources included SolidWorks, PreForm, the Form 4, Grey V5 resin, 99% IPA, washing and curing equipment, and hand tools.

For a rough material cost estimate, I assumed a resin price of $100 per liter, or $0.10 per mL. Using PreForm’s estimated volume of 20.74 mL gives approximately $2.07 in resin for the entire shared build plate. This includes the other project and is not the separate cost of my two components. The estimate does not include IPA, gloves, electricity, or equipment costs.

## Resources

- *Snap-Fit Joints for Plastics – A Design Guide* (provided on Canvas) (Section B, Figures 8, 9, 12, and 17; Tables 1 and 2.)




