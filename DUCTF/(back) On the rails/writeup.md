
# DUCTF 2021 - (back) On the rails

![date](https://img.shields.io/badge/date-25.09.2021-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![OSINT category](https://img.shields.io/badge/category-osint-lightgrey.svg)
![score](https://img.shields.io/badge/score-100-blue.svg)
![solves](https://img.shields.io/badge/solves-170-brightgreen.svg)

## Description
Author: xXl33t_h@x0rXx

We intercepted further communications between the two. This text was sent shortly before we lost track of one of the suspects, with an image attached. Can you work out what they're talking about?

Okay, please promise not to judge me, but I might have ended up catching the wrong train again. Though I think I'm still in Australia this time (at least it isn't like that time in Norway LOL). I managed to snap a picture before we went past this station… you have any ideas where I might be?

Please tell us the name of the station, with any spaces replaced by underscores.

Flag format: DUCTF{station_name}


## Solution

The image is highly pixelated and has motion blur, which makes it really hard to see. 

First, I tried to revese image search the image . But I was unable to find any results. For the next stage, I identified aspects of the image that might help us in a search. These were "graffiti", "bush", "abandoned" and "train station". Also the fact that this was an Australia CTF , I assumed that the train station had to be in Australia.

Now with these keywords , I searched in google for "graffiti bush abandoned train station australia"

The second link in the google image search led to a youtube video, which pretty much matched the image location. Looking through the description there is a [wiki link](https://en.wikipedia.org/wiki/General_Motors_railway_station) provided. Double confirming with the images in the wikipedia page , we know that the train station is the General Motors station
## Flag
  
Adding the train station we now have the flag 
``` DUCTF{general_motors_station} ```
