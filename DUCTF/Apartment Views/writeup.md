
# DUCTF 2021 - Apartment Views

![date](https://img.shields.io/badge/date-25.09.2021-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![OSINT category](https://img.shields.io/badge/category-osint-lightgrey.svg)
![score](https://img.shields.io/badge/score-100-blue.svg)
![solves](https://img.shields.io/badge/solves-301-brightgreen.svg)

## Description
Author: xXl33t_h@x0rXx

We received intel that the accomplice we have been following is meeting with the ringleader of RaaS operation, they shared this photo online a few years back - believed to be the view from their apartment building (hideout).

Between you and me, our sources say the ringleader was testing the ransomware they were going to sell and instead infected their own laptop.

We think we may be able to setup a sting to apprehend the ringleader and retrieve the decryption key when they meet the accomplice at a dead drop in a nearby alleyway. Can you work out what the name of the street is?

Flag format: DUCTF{street_name}

## Solution

The first part of the image that I noticed was the ANZ building in the back . Since I live in Melbounre , I knew this building existed in the Melbourne CBD. So after searching for *"ANZ Building Melbounre CBD"*. I was able to find the address and go to the next stage of reversing the location.

There was a small hurdle though, it was diffcult to identify the direction of flat side of the ANZ building using the streetview. So I searched for images first to identify the direction that the logos where facing which turned out to be the North and South from Little Collins St.

After gaining this information , I tried to find the next building that was with glass and concrete. Using streetview and moving up Queen St. I discovered the building at the intersection between Queens St and Little Bourke St. Now that we have our reference points . We can assume that the picture was taken from the next two streets from Little Bourke St.


Checking Londsdale St we can see that it has the correct view angle but is one street in front.

![image](https://user-images.githubusercontent.com/17501137/135404572-32ca27ab-a12d-44dd-9379-f0cc25e9e741.png)


Moving to the next street, at Little Londsdale St we can find the yellow building from the frame and street pathway below. The picture appears to have been taken from ELM Tower. 

![image](https://user-images.githubusercontent.com/17501137/135405274-1f04cfa0-d127-476e-9264-76ea24fe307a.png)



  
## Flag
  
I attempted both Little Londsdale St and Hardware St. The flag was Little Londsdale St.
``` DUCTF{Little_Londsdale_St} ```
