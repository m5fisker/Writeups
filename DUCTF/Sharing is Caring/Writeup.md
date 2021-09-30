# DUCTF 2021 - Sharing is Caring

![date](https://img.shields.io/badge/date-25.09.2021-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![OSINT category](https://img.shields.io/badge/category-osint-lightgrey.svg)
![score](https://img.shields.io/badge/score-232-blue.svg)
![solves](https://img.shields.io/badge/solves-83-brightgreen.svg)

## Description
Author: xXl33t_h@x0rXx

We have identified a username associated with one of the suspects: alex_elgato93. They seem pretty active on social media. Surely with all these posts they must have slipped up somewhere and given us a way to work out their location?

Please tell us the name of the closest street, with any spaces replaced by underscores.

Flag format: DUCTF{street_name}


## Solution

Since a username is provided in this challenge. My first goal was to find accounts related to this username. Utilizing *spiderfoot* , I created a new scan for the user.

The following accounts were displayed in the result and linked to the same person.

- https://twitter.com/alex_elgato93
- https://www.pinterest.com.au/alex_elgato93/
- https://www.twitch.tv/alex_elgato93
- https://steamcommunity.com/id/alex_elgato93

Scouring through each link , we mainly see puns that are posted by alex_elgato93 . Coming to steam , we see that the user has another username called alexandros-elgato.

Utlizing this information , I performed another scan on *spiderfoot* with user alexandros-elgato , and managed to get two results.

- https://github.com/alexandros-elgato
- https://www.reddit.com/user/alexandros-elgato

Viewing the github page, there only seems to be one repository called Hello-World and not much information further. Then looking at reddit we see that the user has made many posts. I one of the posts made contained a screenshot of his kali-vm with many tabs open. At the bottom right of the image , the user seems to have made an arp request with -a, which reveals his MAC address(BSSID) - **DE:73:2C:6C:1B:C1**. 

![image](https://i.redd.it/d8tjy7453om71.png)

Now searching for "find location using bssid" we come across wigle.net. Entering the details , we see the location of the user at "Charles McIntosh Pkwy"

![image](https://user-images.githubusercontent.com/17501137/135417072-dbe94a65-931c-4909-817d-9ec01a7c0113.png)


  
## Flag
  

``` DUCTF{charles_mcintosh_pkwy} ```
