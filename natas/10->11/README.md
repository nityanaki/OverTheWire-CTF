## [Natas Level 10->11](http://natas10.natas.labs.overthewire.org)
#### Natas10 password: nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu

The code is different from the previous level in that the characters '/[;|&]/' are no longer allowed in order to avoid command injection.

However, grep allows searching for items from more than one input file. We can modify
````console
: ~$ grep -i <word> dictionary.txt
````
to be
````console
: ~$ grep -i <word> <file> dictionary.txt
````

Search for characters that may be in the file ../../../../etc/natas_webpass/natas11. For example, try the input "a ../../../../etc/natas_webpass/natas11" to get the command
````console
~$ grep -i a ../../../../etc/natas_webpass/natas11 dictionary.txt
```` 
which doesn't yield results. Try replacing "a" with "o" and the output includes the flag. The password for natas11 is U82q5TCMMQ9xuFoI3dYX61s7OZD9JKoK.
