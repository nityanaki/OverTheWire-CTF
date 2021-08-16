## [Natas Level 8 -> 9](http://natas8.natas.labs.overthewire.org)

#### Natas8 password: DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe

Problem: Using the source code, find an input secret.

Notice in the source code:
        <?

        $encodedSecret = "3d3d516343746d4d6d6c315669563362";

        function encodeSecret($secret) {
            return bin2hex(strrev(base64_encode($secret)));
        }

        if(array_key_exists("submit", $_POST)) {
            if(encodeSecret($_POST['secret']) == $encodedSecret) {
            print "Access granted. The password for natas9 is <censored>";
            } else {
            print "Wrong secret";
            }
        }
        ?>
        
Convert 
