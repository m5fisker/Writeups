# TamilCTF 2021 - Dark Night

![date](https://img.shields.io/badge/date-28.09.2021-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![Forensics category](https://img.shields.io/badge/category-forensics-lightgrey.svg)
![score](https://img.shields.io/badge/score-50-blue.svg)
![solves](https://img.shields.io/badge/solves-118-brightgreen.svg)

## Description
Author: 0xcyberpj

Batman hunts in dark

[file]()

## Solution

Firstly, checking the file using *"file"* command we can confirm that it is a pdf file. Now viewing the pdf file we see faded text that is filled for the first few pages. 

Utilizing this information . I first try to find the flag using *strings* but this does not seem to provide any valuable result.

So next I moved to using pdftotext tool, which gave me a text dump . Analyzing the text dump , I found the following ASCII characters.

```84 97 109 105 108 67 84 70 123 49 95 108 48 118 51 95 98 98 52 52 116 116 95 109 97 110 125 ```

Using an online ASCII decoder , we are able to get the flag
  
## Flag
  

``` TamilCTF{1_l0v3_bb44tt_man} ```
