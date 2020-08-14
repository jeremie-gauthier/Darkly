# Cookie Forgery

## Flag

df2eb4ba34ed059a1e3e89ff4dfc13445f104a1a52295214def1c4fb1693a5c3

## Description

The website store a cookie that determines whether the user is admin or not.

The cookie is encoded with `md5` and, once decoded, its value is `false`.

## URL

http://192.168.x.y/

Everywhere on the website.

## Steps To Reproduce

- Hash the string `true` with the `md5` method.
- Replace the value of the cookie named `I_am_admin` by the new hash.
- Reload the page.

## Why is it dangerous ?

Since `false` is very easy to crack by bruteforce or dictionary, any user can easily guess how the cookie works and grant themselves admin access.

## Possible fixes

- This cookie could have used the `'http-only'` and `'secure'` flags.
- A better option could have been to create a session on the server side.

## Resources

- [Hash Decoder](https://crackstation.net/)
- [MD5 Hash Generator](https://www.md5hashgenerator.com/)
- `true` in `md5` is `b326b5062b2f0e69046810717534cb09`
