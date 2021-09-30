# DUCTF 2021 - The Internet is Written in Ink

![date](https://img.shields.io/badge/date-25.09.2021-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![OSINT category](https://img.shields.io/badge/category-osint-lightgrey.svg)
![score](https://img.shields.io/badge/score-100-blue.svg)
![solves](https://img.shields.io/badge/solves-189-brightgreen.svg)

## Description
Author: Crem

One of the interns, Ducky, accidentally posted DUCTF data publicly, he said he was successful in scrubbing it from what he called "CTF clock" and mentioned the number four hundred and four ¯\(ツ)/¯.

Ducky wouldn't screw up twice would he?

## Solution

This was a pretty straightforward challenge. The hint given was the *"CTF Clock"* which refers to CTFTime.com and *"four hundred and four"* as error 404 page. 

Now scrubbing through the CTFTime link for the event in Wayback machine . We find that there was a [capture](https://web.archive.org/web/*/http://ctftime.org/event/1312) taken on March 14 which contains the flag .


## Flag
  
``` DUCTF{a5abef5222adc680a453607384bcb4d2} ```
