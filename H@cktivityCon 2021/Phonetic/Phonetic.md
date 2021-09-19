# H@cktivityCon 2021 - Phonetic

![date](https://img.shields.io/badge/date-19.09.2021-brightgreen.svg)  
![solved in time of CTF](https://img.shields.io/badge/solved-in%20time%20of%20CTF-brightgreen.svg)  
![malware category](https://img.shields.io/badge/category-malware-lightgrey.svg)
![score](https://img.shields.io/badge/score-362-blue.svg)
![solves](https://img.shields.io/badge/solves-112-brightgreen.svg)

## Description
Author: @JohnHammond#6971

It's easy to find the flag... just sound it out!

## Solution

Firstly, identifying the file type , using the file command
```
phonetic: PHP script, ASCII text, with very long lines
```
Viewing the code we see obsucated version of the code. I firstly, cleaned it up and tried to make sense of the code

Some interesting parts within the code 
```
// Function to perform certain actions and retuns a string value
 function firstFunction($input1, $input2 = '')
 { 
 	$firstValue = $input1;
 	$secondValue = '';
 	for ($i = 0; $i < strlen($firstValue);)
 		{ 
 			for ($j = 0; $j < strlen($input2) && $i < strlen($firstValue); $j++, $i++) 
 			{ 
 					$secondValue .= $firstValue[$i] ^ $input2[$j]; 
 			} 
 		} 
 		return $secondValue; 
 }
```

```
//Looping with a concatenation and adding it to emptyString1
foreach([24,4,26,31,29,2,37,20,31,6,1,20,31] as $k){
   $emptyString1 .= $jqueryValue[$k];    //base64_decode
}

//Looping with a concatenation and adding it to emptyString2
foreach([26,16,14,14,31,33] as $k){
   $emptyString2 .= $jqueryValue[$k];   //strrev
}

//Running strrev on a string of characters
$k = $emptyString2('n'.''.''.'o'.''.''.'i'.''.'t'.''.'c'.''.'n'.''.'u'.'f'.''.''.''.''.'_'.''.''.''.'e'.''.'t'.''.'a'.''.'e'.''.''.''.''.'r'.''.''.''.''.'c'); //create_function

//Modified to display result instead of creating a function
$deobsucatedResult = $emptyString1( firstFunction($emptyString1($bigBlob), "tVEwfwrN302"));
```


## Flag
