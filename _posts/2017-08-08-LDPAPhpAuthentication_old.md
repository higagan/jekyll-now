---
layout: post
title:  LDAP Auth in Php
published: true
category: php
---
```php
<script>
function goBack() {
    window.history.back();
}
</script>
<?php

if(isset($_POST['username'])){
$ldap_host = "ldap.forumsys.com";
$base_dn = "dc=example,dc=com";
$filter = "(ou=mathematicians)";
$username = $_POST['username'];
$ldap_user  = "uid=".$username.",dc=example,dc=com";

$ldap_pass = "password";
$ldap_port = 389 ; 
$connect = ldap_connect( $ldap_host, $ldap_port)
         or exit(">>Could not connect to LDAP server<<");
ldap_set_option($connect, LDAP_OPT_PROTOCOL_VERSION, 3);
ldap_set_option($connect, LDAP_OPT_REFERRALS, 0);
$bind = ldap_bind($connect, $ldap_user, $ldap_pass)
      or exit(">>Could not bind to $ldap_host<<");
$read = ldap_search($connect, $base_dn, $filter)
      or exit(">>Unable to search ldap server<<");
$info = ldap_get_entries($connect, $read);

if (in_array($ldap_user, $info[0]['uniquemember']))

echo "<h1>Login successful</h1><br><button onclick='goBack()'>Go Back</button>";
else
echo "<h1>Login not successful</h1><br><button onclick='goBack()'>Go Back</button>";


ldap_close($connect);

}
else{
?>
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
<body>

    <div class="container">
      <form class="form-signin" form action="#" method="POST">
        <h2 class="form-signin-heading">Please sign in</h2>
        <label for="inputEmail" class="sr-only">Email address</label>
    
        <label for="username">Uid: </label>
        <input id="username" type="text" name="username" /> 
        <button class="btn btn-primary" value='submit' type="submit">Sign in</button>
    </form>
    


    </div>
<?php } ?> 


```
