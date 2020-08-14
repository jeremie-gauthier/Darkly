# Remote File Inclusion - DataURI (Document forgery)

## Flag

928D819FC19405AE09921A2B71227BD9ABA106F9D2D37AC412E9E5A750F1506D

## Description

By clicking on the NSA picture, I'm moved to this page : http://192.168.x.y/?page=media&src=nsa
By changing the src value, I get a wrong answer gif and a <object> tag wrapper containing the local ressource with the src value as URI.
Result is splitted in 2 tr, each tr containing a td.
With src = nsa :

- First td : Title (File: nsa_prism.jpg)
- Second td : `<object>` with data=http://192.168.x.y/images/nsa_prism.jpg
  With any other src :
- First td : Wrong answer gif
- Second td : `<object>` with data=src

Send a payload with the base64 option on.

## URL

http://192.168.x.y/?page=media&src=YOUR_PAYLOAD

## Steps To Reproduce

Access this URL to get the flag directly :
http://192.168.x.y/?page=media&src=data:text/html;base64,PHNjcmlwdD5hbGVydCgndGVzdCcpOzwvc2NyaXB0Pg==

## Why is it dangerous ?

You can forge a file directly in the data: wrapper and execute your code like if it was directly on the server, depending of the language, you can, for exemple :

- Show the pages source code (Especially powerful in php)
- Forge malicious AJAX requests and bypass CORS/sameorigin filters
- And lots of other cool things

## Possible fixes

- Limit user input to an alphanumerical charset, and add manualy the jpg extention (No null byte in php7)
- If the number of pictures is low enough, it's also possible to make a conditional display in raw code like for the nsa picture, using for exemple a key/value dict.
- If the number of pictures is high (or if you want to display images user uploaded as well), follow the 1st fix, then while uploading images give them an unique md5 hash as name and convert them to jpg.

## Resources

There is no additional resource for this issue.
