# A8 – Gears

## Asking Smart Questions 

The reason that asking smart questions is important is that it can determine the very foundation on which new ideas come about. The quality of the question, the angle you take, and the assumptions you challenge or introduce decide whether you end up with a quick half-attempted fix or a real solution. For design thinking, good questions prevent you from going straight to conclusions or solving the wrong problem. Instead of just focusing on surface-level observations, asking "why" over and over forces you to dig into what people actually need and care about. Starting with the right questions guides the entire design process, leading to ideas that make sense and work for real solutions.

## Problem Statement

The purpose of my design is to create a simple, 3D-printable pulley system that redirects force, specifically allowing me to close my closet door from bed. The main technical challenge is designing a mechanism with tight enough tolerances to let the wheel spin smoothly while keeping the structure sturdy and rigid. Researching a bit about pulleys and links in the resources, I figured out that the design would be based on a fixed pulley system that can attach to my shelf in the closet and will redirect the horizontal force from the door into a vertical force that is being weighted down by a jug of water. The weight of the jug needs to be heavier than the door in order for it to accelerate the door to a close.

I noticed it at night after getting completely settled into bed and realizing my closet door was wide open. I prefer keeping doors shut for room temperature and general comfort, and I couldn't fall asleep without closing it. Getting up every time ruined my sleep "momentum", so I decided to design a simple mechanical pulley system that solves the problem by automatically closing the door every time while also giving me hands-on design experience with pulleys.

My ideal users are considered general DIYers looking for low-tech, non-electronic ways to solve small household type of annoyances, as well as 3D printing makers who need a simple, open-source pulley template they can easily download, scale, and modify for their own projects. It isn't supposed to be perfect, but it should work as a great and fun starter.

My approach focused on the design was to create a 3-part pulley system that could all individually be printed and assembled together once completed. Not requiring any extra materials other than the rope that lies within the pulley itself. This was to prevent being required to have to go out of your way to make the design work over just designing it in such a way that it works as intended. This was the most difficult part of the design as I wanted to make it as independent as possible, which I struggled a lot with.

## CAD Modeling

Here is a rough generalized sketch I made of the design to elaborate on more with the CAD modeling. 

<img width="820" height="735" alt="Math Scratch Paper (31)" src="https://github.com/user-attachments/assets/23679a37-9032-40e2-b349-ac7e02d1dbfd" />


### Pulley Wheel

I first began my sketching on the front plane, planning on revolving the axis where the Right Plane and Front meet.

<img width="1643" height="982" alt="image" src="https://github.com/user-attachments/assets/2ad93bc1-6220-4c32-87df-af69e4fe33de" />

Creating the general sketch of the model, I planned to utilize the revolve feature tool to generate the pulley wheel easily. I first constrained the pulley's distance from the rotating axis; this would become the location where the pin fits and allows the pulley to rotate. It was set to 0.40 inches. The next constraint was the distance of the pulley's pin radius to the max radius; this was set to 1.7 inches as I wanted to ensure the pulley was sizable while not being overall large. I then constrained the heights, with the main interacting surface of the pulley being constrained to 0.3 inches; this was sourced from an approximate width of that value. I then constrained the 2 triangular slopes to contain a width of 0.2 inches. The top dimension was constrained so that any alteration to the bottom would result in the top being identical. The distance from the pin radius to the tooth radius was set to 1.1 inches to give a proper depth without falling too deep.

<img width="1642" height="977" alt="image" src="https://github.com/user-attachments/assets/4abd4b2d-1952-4c2a-a05c-7057cd7aa08c" />

<img width="991" height="503" alt="image" src="https://github.com/user-attachments/assets/be75ac93-fe0b-4f7a-bca2-043403132f29" />

Once the general sketch was completed, I then created a small center line around which I could revolve; it is between the intersection of the front and right planes.

<img width="1640" height="986" alt="image" src="https://github.com/user-attachments/assets/60f831f4-f406-4ae5-91c4-a2e10cde31cc" />

Once the revolve feature was applied using our sketch and the created axis I then decided to add a fillet with a radius of 0.05 inches to avoid any sharp edges found around the lip.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/ed5b56a1-2395-4f8f-8630-1a9dc0ab85b5" />

Given the finalized model shown below, one of the most noticeable factors of this model is its size and density. I decided that, to avoid any issues with structural failure, I kept the entire model solid.

<img width="1641" height="971" alt="image" src="https://github.com/user-attachments/assets/cc749ac0-f7a1-413f-af98-cbf4db592f9a" />

### Pulley Structure

I then moved on to the pulley structure that will hold the wheel and the pin. Starting with creating a sketch on the top plane.

<img width="1642" height="981" alt="image" src="https://github.com/user-attachments/assets/fa907b98-c4d4-4250-96d7-598534fe1488" />

Creating a basic outline of the support structure, I contain a larger triangular shape with a length of 2.50 inches, constrained based on the total radius of the wheel with added room for a thick back surface (will be shown better once completed), and a height of 1.9 inches based on a rough approximation of the support structure to be used (a shelf within my closet). There is also a small square constrained at 0.75 inches on each of its sides, which will represent the hook that will support the structure. 


<img width="1645" height="983" alt="image" src="https://github.com/user-attachments/assets/ad2d14c7-06f6-4d05-bf51-53555c6f72a1" />

Once the sketch was completed, I then moved on to extruding the sketch by 1.50 inches, as the pulley will contain the wheel within itself at 0.7 inches. This will give us 0.4 inches on each side of the arms

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/996557d8-d0bf-4c51-b958-e78b3bab8f4a" />

Creating the holding circle, I constrained it to have a diameter of 1.20 inches. And extruded it to the opposite surface.

<img width="1646" height="981" alt="image" src="https://github.com/user-attachments/assets/db20a0df-413c-4227-b831-722926861e67" />

<img width="1916" height="981" alt="image" src="https://github.com/user-attachments/assets/0f992d67-72de-47ef-a8d8-7af96cd22741" />

The next major sketch utilized was the main cut, with the small hook being constrained to 0.40 inches. The interior triangle was constrained at 1.50 length and 1.14 height, with these values being found by taking 60% of the original lengths. The triangle was then distanced 0.25 inches away on each side. The last sketch was the pin hole, which was set to 0.79 inches for tolerance reasons because with the wheel having a radius of 0.80 inches, it means that a pin at 0.78 inches will have a looser fit with the wheel allowing for free rotation while also having a tighter fit with the structure, keeping its rigidity.

<img width="1646" height="985" alt="image" src="https://github.com/user-attachments/assets/27d9541b-e3cd-40be-8bdb-be84d5ab607b" />

It was then sketched through the entirety of the model.

<img width="1916" height="983" alt="image" src="https://github.com/user-attachments/assets/59ee24d0-1786-476f-b6e7-eaf11a604c63" />

I then moved on to creating fillets to prevent any sharp edges within the model, with a 1-inch fillet on the connection between the pin connector and the rest of the structure. The remaining structure received a fillet with a 0.10-inch radius.

<img width="1647" height="987" alt="image" src="https://github.com/user-attachments/assets/0b9d004d-dbbb-4e9b-8acf-dc32b27ebd84" />

One of the last cuts, I then created a small rectangle with dimensions of 0.25 by 0.40 inches while being centered on the side of the hook. It was then extruded up to the next section. Allowing for our structure to properly fit onto the specific shelf I have in my closet.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/0912a025-38fe-46d0-a346-88813258a862" />

The final cut was created with another rectangular sketch, at 3.00 inches by 0.72 inches. This value of 0.72 inches is derived from the thickness of the wheel at 0.70 inches with an added tolerance of 0.02 inches, allowing it to slide smoothly while being a part of the structure.

<img width="1647" height="985" alt="image" src="https://github.com/user-attachments/assets/df91a6e1-5dda-481a-b3ea-67dd04527a87" />

It was then extruded through to the pinned end.

<img width="1910" height="982" alt="image" src="https://github.com/user-attachments/assets/2bd8ce7a-0200-4dde-abd4-ef1909dab45f" />

Leaving the final result below here:

<img width="1645" height="983" alt="image" src="https://github.com/user-attachments/assets/1f5d29ca-4928-4e33-b79a-29a11a5fe8a1" />

### Pulley Pin 

I then moved on to the Pin that will be inserted into both the pulley wheel and support structure. Starting with the top plane.

<img width="1646" height="981" alt="image" src="https://github.com/user-attachments/assets/2f33f7c8-60ca-4551-8cd2-441dd4f9cdaa" />

I created a circle sketch with a diameter of 0.78 inches for the reasons of fit as mentioned prior.

<img width="1646" height="981" alt="image" src="https://github.com/user-attachments/assets/8746b311-0c67-4d2a-a6ff-db22e73379d1" />

It was then extruded 1.5 inches because of the width of the structure previously completed.

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/3bea860a-cf97-449b-a0c2-b699e16e740f" />

Below you can see the final product:
<img width="1642" height="985" alt="image" src="https://github.com/user-attachments/assets/16c66757-c780-490f-a228-9b54721ffdcd" />


## Print Settings

 I did not use a raft, as it wasn't needed. I did decide to use a skirt that would print a single layer surrounding the settings below. With only a single loop, 6mm from the object, and a height of 1 layer.

<img width="1663" height="176" alt="image" src="https://github.com/user-attachments/assets/586746a4-7820-4f88-a881-8c9fc328c26b" />

As seen below, the settings are considerably simple, with the layer height and first layer height being both set to 0.3 mm and 0.35 mm, respectively. The only major change I made was the perimeter, which I increased by 1 from the traditional 3; this would result in better surface strength and structure with a wall thickness of around 1.61 mm.

<img width="1660" height="285" alt="image" src="https://github.com/user-attachments/assets/bc3c382c-eb37-4505-9582-a29c655f155e" />

I chose to do 50% infill with the Gyroid pattern, which definitely means a longer print time and higher filament usage but I want the structure to be able to properly perform and work under an applied load.

<img width="1663" height="93" alt="image" src="https://github.com/user-attachments/assets/101532f4-e346-4bf9-a7c3-a6c7471d5f5d" />

I did use supports, with the listed settings below being significant, using organic style for simplicity to remove. I honestly used the support wherever it sees fit. I understood that within the print, the primary sections that would need to be supported are the overhang of the structure, the upper lip of the wheel, and the sides of the pin. All were covered everywhere. If it was needed, I would have utilized the paint tool in order to give our model the support it required.

<img width="1652" height="753" alt="image" src="https://github.com/user-attachments/assets/0c3b6965-6b2f-48e8-aa8d-7dc8bdc1e320" />

I set the seam position to random to prevent any buildup of increased surfaces.
<img width="1647" height="67" alt="image" src="https://github.com/user-attachments/assets/8b8fd925-7a23-440f-9c07-d219a9a33bdd" />

For quality assurance's sake, I set the Elephant foot compensation to 1 mm, preventing any issues with scaling. Honestly, this setting was not required for anything other than the pin, but I decided it was worth putting down.
<img width="1671" height="27" alt="image" src="https://github.com/user-attachments/assets/4d7559b0-18e8-42b0-af42-ee56607cf806" />


When organizing the plate, there were 2 key things I kept in mind when I decided to organize the structure: I needed to have all of the parts roughly spaced enough apart so that their supports do not interact with each other at all, while also remaining relatively in the center to allow for a higher accuracy of print. The reason for this build orientation for all 3 to be on their sides is because it gives them all the best strength in filament printed, with the structure part being aligned to the length it will bend over, and the pin being aligned perpendicular to its own shear plane when inserted. The Wheel was least important for strength, as it already was a very thick piece, but it made the most sense to print on its side for simplicity and structure.

<img width="1916" height="1091" alt="image" src="https://github.com/user-attachments/assets/0a06ac8b-a08d-466c-be0f-42953d43df9d" />


It is stated by Prusa that there are 127 layers of print utilized in the file. It can be observed in the right side of the main screen of Prusa after slicing.



With an estimated time of 6 hours and 44 minutes, I decided it would be best to start preheating the Printer in order to ensure no time is wasted and that our predicted time is the actual. With a build volume of 134 grams of used filament and 6.44 inches cubed of space taken up, the print is already a very hefty size.

<img width="500" height="215" alt="image" src="https://github.com/user-attachments/assets/073edcc3-1f19-4fa5-a5e4-a046e71605e3" />




## Print 

I utilized Print Machine Number 8 in the Lab.

Early Stage of Primary Print:
<img width="4032" height="3024" alt="IMG_0136" src="https://github.com/user-attachments/assets/e8acfba8-2bc0-4fad-915c-4626a151d28d" />

Video of Primary Print:
<video src="https://github.com/user-attachments/assets/e96a0b3a-cbb9-439a-920d-67779a4caeda" controls style="max-width: 100%;">
</video>

Late Stage of Primary Print:
<img width="4032" height="3024" alt="IMG_0142" src="https://github.com/user-attachments/assets/4eac4eee-2e4e-415a-bbc7-3828d74233b6" />

## Iteration 

Once the original Model had been printed, I ran into an issue with how the rope was able to sit on the model when being applied, as it kept getting pulled off of the pulley. I will elaborate more about the core issue in the lessons learned section. But I wanted to mention it here as the reason for the iteration. 

I needed to design a surface that could allow for the pulley to be placed at a more optimal angle, attaching the same structure in the closet. 

After taking some measurements, I created a sketch on the top plane. Most of these dimensions were directly sourced from the structure found within the closet, ensuring that they fit onto the model. With some of the significant points being the 1.60-inch dimension on the left side constraining the surface on which the pulley will sit on top of, the right side constraining a clip that is able to properly attach to the shelf and change the angle.

<img width="1916" height="1010" alt="image" src="https://github.com/user-attachments/assets/e27f804b-a243-48bf-a8cb-532b28d5058a" />

The next set was extruding the model by 0.365 inches; this would allow for the pulley structure to be placed on top of the iteration without requiring some sort of mechanism.

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/fe938b31-ed31-482e-801e-b8c21e023ea6" />

I then filleted many of the edges to a radius of 0.10 inches in order to prevent a sharp model and allow for stress concentrations to be reduced.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/34f67e52-6da3-4978-b6aa-430bb4e82daa" />

Utilizing the same settings for Prusa and printing the body flat on its face to maximize its bending strength. I was able to receive the model and use it for the demonstration.

<video src="https://github.com/user-attachments/assets/916dd5f4-8c9a-4ffa-922d-4cd1c76c8653" controls style="max-width: 100%;">
</video>


## Post Print 

The surface finish from the supports was considerably low quality, with much of their surface being very bumpy and stringy compared to the model, but once it was finished, they had left the model in much better shape. I don't expect the supports to be completely perfect surface finish and as long as they do their job in supporting the required structures, I won't complain. Removing these supports was relatively easy as well only taking roughly about 3-5 minutes using mainly my hands and a set of sharp pliers. The pliers were mainly used to trim supports that were either difficult to get to or stuck to the actual structures. I found that the pin required the most attention as it was the one model with stricter tolerances and fits.

<img width="1169" height="1012" alt="IMG_0254" src="https://github.com/user-attachments/assets/948ec387-78f4-4d6a-8852-e501e036caf0" />

Here is a video of the Pulley actually functioning properly with the closet door:
<video src="https://github.com/user-attachments/assets/398c9f0e-f937-4d68-8a75-ecfeb6132eed" controls style="max-width: 100%;">
</video>

Photo of the Assembled Pulley without the Iteration:
<img width="4032" height="3024" alt="IMG_0253" src="https://github.com/user-attachments/assets/e9ee033b-9323-4cf0-b9dc-f4ed48a7b6a0" />


## Lessons Learned 

The biggest takeaway from this project was definitely that I should have planned better for iteration and done real testing much earlier in the design process. When I finally installed the completed assembly onto my closet shelf, I realized that pulling the string from my bed created an off-axis angle that pulled the rope right off the wheel. If I had built a quick physical mock-up or tested the pull angle before committing to the CAD model, I would have designed the pulley setup completely differently from the start. I would have integrated an angled mounting bracket and deepened the wheel's center groove upfront, rather than figuring out a fix after printing the final model. It was incredibly frustrating: after a nearly 7-hour print, the model had a very prevalent issue that had to be remedied by another printed part. If I were to start the project again, I would have assembled a simple mock-up to check how the pulley would behave when in action with the door.

Another major lesson came from my printing strategy. The total print time for all three components combined came out to 6 hours and 44 minutes. Putting every single part onto one plate meant I had to wait nearly seven hours just to test basic clearances and functional setup. Looking back, I definitely should have broken the job up into smaller individual prints. Printing just the wheel or pin first would have let me verify tolerances and physical fits in a much shorter time; if something were to go wrong, I could have saved filament with design iterations and kept myself from locking up a printer for almost seven hours only to discover a layout issue. Thankfully, things have worked out with the design itself, but if something were to go wrong in the latter part of the print or in post-processing, that would have been nearly 7 hours wasted.

I do want to preface that coming back from Fall break gave me a lot more time and flexibility to complete this project, so I wanted to do something big that I could iterate upon and improve at a later date, but in doing this there was a much higher sunk cost I had to contribute to with the design, ideas, and print. It took roughly 15 hours and 30 minutes to complete all that was asked, with roughly 6 hours dedicated to modeling all of the different parts and ensuring tolerances checked out, and with the 6 hours and 44 minutes of printing time, I attempted to utilize much of that time for researching, reading the articles, and documenting. Even after printing was finished, I still had to iterate the design and set up the pulley system. This took up most of the remaining time mentioned.

### Resources

[https://en.wikipedia.org/wiki/Pulley](https://en.wikipedia.org/wiki/Pulley)

[https://www.toptal.com/designers/product-design/design-thinking-great-questions](https://www.toptal.com/designers/product-design/design-thinking-great-questions)

[Pully_Base_V1.SLDPRT](Pully_Base_V1.SLDPRT)

[Pully_pin_V1.SLDPRT](Pully_pin_V1.SLDPRT)

[Pully_structure_V1.SLDPRT](Pully_structure_V1.SLDPRT)

[Pully_wheel_V1.SLDPRT](Pully_wheel_V1.SLDPRT)
