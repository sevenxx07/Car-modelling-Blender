# modeling Subaru BRZ tS 2020
![obrazek](https://github.com/user-attachments/assets/3da14697-6aae-49ab-958a-5bca135e94c5)

## Reference materials 
* blueprint (just screenshot) - https://www.the-blueprints.com/vectordrawings/show/20732/subaru_brz_ts/
* commercial fotos - https://www.japan-cars.cz
* side, front, back fotos - https://www.autoweb.cz

## Workflow 
* 3D modelling tool: Blender 2.8
* Used modifiers: Mirror (clipping), Subdivision Surfaces#
* Material Properties#
* UV editing - UV maps
* Shading
* Used tools: Knife, Extrude, Loop Cut, Insert Faces
* Time: around 85 hours

I started with adding background images. I took blueprint and pasted it in the front, side, up and back dimensions and translated it to right positions. <br />
![obrazek](https://github.com/user-attachments/assets/c6062f35-ad47-4acb-914c-58f6a8442c00)

I started with generating plane and creating car hood. I know that I should do firstly simple construction of the car, but after spending lots of time 
I refused to start all over again. So I did all detail with modeling the car. I think it is also different, because I chose car with many curves and 
modeling with details from the beginning looked easier.


### First part of model:
I added modifiers already in first part. Then I continued with sides of the car. I used also Main crease when I needed more sharp edge (set to 1.0). <br />
![obrazek](https://github.com/user-attachments/assets/6f1a6b4d-6618-4688-af8f-2ff5eb7a4670)
![obrazek](https://github.com/user-attachments/assets/325f28f1-9bc1-4abe-9e02-27f83786df79)
After modeling back of the car, I started to model the roof and connecting all parts. Burt the whole car is modeled as one “plane”.<br />
![obrazek](https://github.com/user-attachments/assets/746f6238-6132-4be1-8926-926e4ad67092)
Then I added details - lights, handle and so one. It was done by inserting face and then extruding it in right way. 
In last step, I made wheels of the car as different geometry and using the same modifiers. I ended with doing back of the car. <br />
![obrazek](https://github.com/user-attachments/assets/da3cd0d5-aba9-4d84-8d83-0d1a9d2e8aeb)

### Second part of the model:
I started creating materials that I needed for my car. I made a base material for the car with the dominant value of specular. 
Then black plastic where I used more of roughness. The rubber as material something in between with roughness and little bit of specular. 
I also needed more of metal material. So I used 1.0 metallic with 0.5 specular and little bit of roughness. 
On of the last materials were materials for lights. I did different for front and back lights. Back lights are shines red and front little bit of yellow. The shine was made by emission color and strength.
In these materials I used Principled BSDF. On the other hand by creating a glass I used Glass BSDF with low roughness. <br />
![obrazek](https://github.com/user-attachments/assets/2988799f-0f7f-41a6-b6bf-a7bc564f9c2b)
![obrazek](https://github.com/user-attachments/assets/52b039df-4917-4173-adf9-864d26c74490)
![obrazek](https://github.com/user-attachments/assets/9748580e-6b5f-4d8f-8b23-cc21f48ea633)

Then I assign these materials to faces of the model. When two faces next to each other have different material, it was needed to set the adjacent edge as sharp and set mean crease to 1.0. <br />
![obrazek](https://github.com/user-attachments/assets/a6880e6d-d5bb-4293-9d21-a63b38b62354)
I did Smart UV with Island Margin 0.0001. I also tried to Unwrap it but there were some inaccuracies.<br />
![obrazek](https://github.com/user-attachments/assets/c97bc39f-34d1-40e5-a3da-6044d5d050d0)
I created diffuse map for the base color. In every material was added Image texture with new image diffuse_bake and set Color space to sRGB. I set metallic to 0 and then bake new texture as diffuse and set sampling as on the picture. <br />
![obrazek](https://github.com/user-attachments/assets/049a59ac-7968-4f8a-a6b9-318d6423a096)
I also created roughness map. In every material was added Image texture with new image roughness and set Color space to Non-color. I bake the new texture as Roughness. <br />
![obrazek](https://github.com/user-attachments/assets/aa61143b-529d-42a4-a730-eac2133e5348)
Very similarly was the specular map created. But the specular value of parameters was provided to roughness and also baked as Roughness.
Last was the metallic map created. The metallic value was provided to emission and baked as Emit.

To connect all created textures I used new material with Image Textures connected to relevant parameter.
![obrazek](https://github.com/user-attachments/assets/64090432-2e20-44fd-9d50-20d4feac4bd0)






