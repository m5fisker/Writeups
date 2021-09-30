
# DUCTF 2021 - Heart of the nation

![date](https://img.shields.io/badge/date-25.09.2021-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![OSINT category](https://img.shields.io/badge/category-osint-lightgrey.svg)
![score](https://img.shields.io/badge/score-100-blue.svg)
![solves](https://img.shields.io/badge/solves-122-brightgreen.svg)

## Description
Author: xXl33t_h@x0rXx

We found some files on the website (not really), the caption was “Right at the heart of the nation, no piece of the bush inside the circle remains untouched by us".

We believe this is one of their meeting places, can you help us find the location of the photo truncated (not rounded) to three decimal places?

Flag format is DUCTF{lon,lat}

## Solution

Reading the description of the heart of the nations challenge. I initally assumed that it was to do with the "Ulluru" but viewing the image it did not look like it was anywhere near Ulluru. So the first step, I did was the reverse search the image but again similar to the other challenges. I was unable to get any results for it .

In the next step, I tired to think of other places that could be the "Heart of the nation" . This led me to the nations capital which was Canberra . Viewing images of Canberra it tended to have similar bush landscape to that of the image.

Canberra is a ciruclar esque capital , with the parliment house and other federal buildings within the ceter. Now viewing in satellite view , we first scoured through the first circle looking at a mix of street view and statellite image, but this ended up giving us no results .

Scouring through the the outerloop we foud an interesting circle in the street view , which was in the middle of the bush.


![image](https://user-images.githubusercontent.com/17501137/135414445-2a1b3a96-82b0-4a04-8194-8b8f6343abb7.png)


Viewing the image at this view , we get the spot showcased in the challenge image.

![image](https://user-images.githubusercontent.com/17501137/135414528-38210fc5-9804-4ebe-bbd6-4845b5c0358f.png)


The coordinates for this were  *"-35.30692439897341, 149.1207011429781"*.

  
## Flag
Since the flag only required the first three decimal spaces, we removed the remaining and submitted the following flag.
``` DUCTF{-35.306,149.120} ```
