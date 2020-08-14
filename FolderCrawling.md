# Folder Crawling

## Flag

99dde1d35d1fdd283924d84e6d9f1d820

## Description

Informations stored in hidden file on the client side.

## URL

http://192.168.x.y/.hidden/

## Steps To Reproduce

Using a recursive wget :
`wget -r -p -e robots=off http://192.168.x.y/.hidden/`
I can get all the .hidden/ files and folders

We, then read recursively all the README files and exclude the failed messages
`find .hidden/ -name 'README' -exec cat {} \; | grep -Ev "Demande|craquer|toujours|aussi"`

## Why is it dangerous ?

Hidden or not, the file is accessible for everyone.

## Possible fixes

- Don't hide files directly on your client app, in some languages you can put the sensitive files directly server-side and make a method to access it only as admin from the client.
- If you REALLY want to put sensitive files client-side, you can use a .htaccess file, be aware that requests other than POST or GET can break your .htaccess protection so limit the request methods as well.

## Resources

There is no additional resource for this issue.
