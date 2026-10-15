# A8 – Gears

## CAD Modeling

### Pulley Wheel

I first began my sketching onto the front plane, planning on revolving the axis where the Right Plane and Front meet.
<img width="1643" height="982" alt="image" src="https://github.com/user-attachments/assets/2ad93bc1-6220-4c32-87df-af69e4fe33de" />

Creating the general sketch of the model, I planned to utilize the revolve feature tool to generate the pulley wheel easily. I first constrained the pulley's distance from the rotating axis; this would become the location where the pin fits and allows the pulley to rotate. It was set to 0.40 inches. The next constraint was the distance of the pulley's pin radius to the max radius; this was set to 1.7 inches as I wanted to ensure the pulley was sizable while not being overall large. I then constrained the heights, with the main interacting surface of the pulley being constrained to 0.3 inches; this was sourced from an approximate width of that value. I then constrained the 2 triangular slopes to contain a width of 0.2 inches. The top dimension was constrained so that any alteration to the bottom would result in the top being identical. The distance from the pin radius to the tooth radius was set to 1.1 inches to give a proper depth without falling too deep.

<img width="1642" height="977" alt="image" src="https://github.com/user-attachments/assets/4abd4b2d-1952-4c2a-a05c-7057cd7aa08c" />

<img width="991" height="503" alt="image" src="https://github.com/user-attachments/assets/be75ac93-fe0b-4f7a-bca2-043403132f29" />

Once the general sketch was completed I then created a small center line of which I could revolve around, it is between the intersection of the front and right plane.

<img width="1640" height="986" alt="image" src="https://github.com/user-attachments/assets/60f831f4-f406-4ae5-91c4-a2e10cde31cc" />

Once the revolve feature was applied using our sketch and the created axis I then decided to add a fillet with a radius of 0.05 inches to avoid any sharp edges found around the lip.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/ed5b56a1-2395-4f8f-8630-1a9dc0ab85b5" />

Given the finalized model shown below, one of the most noticeable factors of this model is its size and density. I decided that, to avoid any issues with structural failure, I kept the entire model solid.
<img width="1641" height="971" alt="image" src="https://github.com/user-attachments/assets/cc749ac0-f7a1-413f-af98-cbf4db592f9a" />

### Pulley Strucure

I then moved onto the pulley structure that will hold the wheel and the pin. Starting with creating a sketch onto the top plane.

<img width="1642" height="981" alt="image" src="https://github.com/user-attachments/assets/fa907b98-c4d4-4250-96d7-598534fe1488" />

Creating a basic outline of the support structure, I contain a larger triangular shape with a length of 2.50 inches, constrained based on the total radius of the wheel with added room for a thick back surface (will be shown better once completed), and a height of 1.9 inches based on a rough approximation of the support structure to be used (a shelf within my closet). There is also a small square constrained at 0.75 inches on each of its sides, which will represent the hook that will support the structure. 


<img width="1645" height="983" alt="image" src="https://github.com/user-attachments/assets/ad2d14c7-06f6-4d05-bf51-53555c6f72a1" />

Once the sketch was completed I then moved onto extruding the sketch by 1.50 inches as the pulley will contain the wheel within itself at 0.7 inches. This will give us 0.4 inches on each side of the arms

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/996557d8-d0bf-4c51-b958-e78b3bab8f4a" />

Creating the holding circle I constrained it to have a diameter of 1.20 inches. and extruded it the opposite surface.

<img width="1646" height="981" alt="image" src="https://github.com/user-attachments/assets/db20a0df-413c-4227-b831-722926861e67" />

<img width="1916" height="981" alt="image" src="https://github.com/user-attachments/assets/0f992d67-72de-47ef-a8d8-7af96cd22741" />

The next major sketch utilized was the main cut with the small hook being constrained to 0.40 inches. The interior traiangle being constrained at 1.50 lenght and 1.14 height with these values being found by taking 60% of the original lengths. The triangle was then distanced 0.25 inches away on each side. The last sketch was the pin holewhich was set to 0.79 inches for tolerance reason (EXPLAIN MORE)

<img width="1646" height="985" alt="image" src="https://github.com/user-attachments/assets/27d9541b-e3cd-40be-8bdb-be84d5ab607b" />


It was then sketched through the entirity of the model.

<img width="1916" height="983" alt="image" src="https://github.com/user-attachments/assets/59ee24d0-1786-476f-b6e7-eaf11a604c63" />

I then moved onto creating fillets to prevent any sharp edges within the model with a 1 inch fillet on the connection between the pin connector and the rest of the structure. Witht the remaining strucutere recieving a fillet at 0.10 inches radius.

<img width="1647" height="987" alt="image" src="https://github.com/user-attachments/assets/0b9d004d-dbbb-4e9b-8acf-dc32b27ebd84" />

One of the last cuts I then created a small rectangle dimension at 0.25 by 0.40 inches while being centered on the side of the hook. It was then extrude up to the next section.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/0912a025-38fe-46d0-a346-88813258a862" />

The final cut was the created with another rectangular sketch, at 3.00 inches by 0.72 inches (explain 0.72 where from)
<img width="1647" height="985" alt="image" src="https://github.com/user-attachments/assets/df91a6e1-5dda-481a-b3ea-67dd04527a87" />

It was then extrude through until the pinned end.

<img width="1910" height="982" alt="image" src="https://github.com/user-attachments/assets/2bd8ce7a-0200-4dde-abd4-ef1909dab45f" />

Leaving the final result below
<img width="1645" height="983" alt="image" src="https://github.com/user-attachments/assets/1f5d29ca-4928-4e33-b79a-29a11a5fe8a1" />

### Pulley Pin 

I then moved on to the Pin that will be inserted into both the pulley wheel and support structure. Starting with the top plane

<img width="1646" height="981" alt="image" src="https://github.com/user-attachments/assets/2f33f7c8-60ca-4551-8cd2-441dd4f9cdaa" />

I create a circle sketch with a diameter of 0.78 inches

<img width="1646" height="981" alt="image" src="https://github.com/user-attachments/assets/8746b311-0c67-4d2a-a6ff-db22e73379d1" />

extruded 1.5 inches because width of strucute

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/3bea860a-cf97-449b-a0c2-b699e16e740f" />

Final product
<img width="1642" height="985" alt="image" src="https://github.com/user-attachments/assets/16c66757-c780-490f-a228-9b54721ffdcd" />

### Assembly
<img width="1647" height="967" alt="image" src="https://github.com/user-attachments/assets/c637a1d5-45a2-456f-a7eb-3651606179a5" />


## Print Settings
What number machine did you use?

NEED TO PUT
Did you use a raft? If so, what were the settings?

I did not use a raft as it wasn't need I did decide to use a skirt that would print a single layer surrounding the settings are below. With only a single loop, 6mm from object, and a height of 1 layer.

<img width="1663" height="176" alt="image" src="https://github.com/user-attachments/assets/586746a4-7820-4f88-a881-8c9fc328c26b" />





What was the wall thickness?
What is the layer thickness?

As seen below the settings are considerably simple with the layer height and first layer heigh tbeing both found at 0.3mm and 0.35 mm respectively. The only major change I made was the perimetiter where I increased it by 1 from the traditional 3, this would result in better surface strength and structure.

<img width="1660" height="285" alt="image" src="https://github.com/user-attachments/assets/bc3c382c-eb37-4505-9582-a29c655f155e" />

What infill did you use and why?
I chose to do 50% infill with the Gyroid pattern, which definitely means a longer print time and higher filament usage but I want the structure to be able to properly preform and work under a applied load.
<img width="1663" height="93" alt="image" src="https://github.com/user-attachments/assets/101532f4-e346-4bf9-a7c3-a6c7471d5f5d" />


Did you use supports? Why or why not? If you did, explain the technical process you used to support the print.

<img width="1652" height="753" alt="image" src="https://github.com/user-attachments/assets/0c3b6965-6b2f-48e8-aa8d-7dc8bdc1e320" />

I did use supports with the listed settings below being significant, using organic style for simplificity to remove. I honestly used the supoport everwhere it sees fite I understood that within the print the primary sections that would need to be supported is the overhang of the structure, the upper lip of the wheel, and the sides of the pin. All were covered by everywhere. If it was needed I would have utilized the paint tool in order to give our model supports it required.


Set seam postion to random 
<img width="1647" height="67" alt="image" src="https://github.com/user-attachments/assets/8b8fd925-7a23-440f-9c07-d219a9a33bdd" />

Elephant foot compensation 1 mm
<img width="1671" height="27" alt="image" src="https://github.com/user-attachments/assets/4d7559b0-18e8-42b0-af42-ee56607cf806" />


Outline reasons for the layout.
Outline reasons for build orientation.


How many layers are used in the print?

What is the build volume of your print?


Note the slice information on Prusa Slicer


## Post Print 
Comment on the surface finish of the supports
What did you use to remove the supports?
## Analyze


## Decide


## Communicate

