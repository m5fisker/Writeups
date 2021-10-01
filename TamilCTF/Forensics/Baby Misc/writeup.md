# TamilCTF 2021 - Baby Misc

![date](https://img.shields.io/badge/date-25.09.2021-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![OSINT category](https://img.shields.io/badge/category-osint-lightgrey.svg)
![score](https://img.shields.io/badge/score-100-blue.svg)
![solves](https://img.shields.io/badge/solves-663-brightgreen.svg)

## Description
Author: 0xRakesh

See the file structure.


## Solution

Firstly checking the file , we can confirm that it is a pdf file. Viewing the file , we see that it has a flag within it . Attempting to submit this flag, unfortunately shows us an incorrect result . Hence there is another flag present within it.

Next we check the file with Binwalk and can see that there are multiple files present within a zip archive.
![image](https://user-images.githubusercontent.com/17501137/135622034-814d34ec-e725-44bb-bec8-81c960d156ee.png)

Now that we know there is a zip archive present, I extract using binwalk and and unzip the files. Opening the archive, we can see that there are 13 text file present. The text files 1,5,9 and 13 are encoded with base64. Decoding and combing them gives us the flag.

  
## Flag
  

``` TamilCTF{R3v3rSEr_mAk3_AM1sC} ```
