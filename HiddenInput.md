# Hidden Input

## Flag

1D4855F7337C0C14B6F44946872C4EB33853F40B2D54393FBE94F49F1E19BBB0

## Description

Rely on frontend form to recover the password.

## URL

http://192.168.x.y/?page=recover

## Steps To Reproduce

On page, inspect the elements and remove the following:

```xml
<input type="hidden" name="mail" value="webmaster@borntosec.com" maxlength="15">
```

## Why is it dangerous ?

It's possible to see the webmaster mail in clear, making it vulnerable for spam bots.
It's also possible to spam a given mail using your website as origin, which can cause your site reputation/trustworthiness to drop.

## Possible fixes

- Create a secure procedure with email validation to recover a user password.

## Resources

There is no additional resource for this issue.
