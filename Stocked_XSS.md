# Stocked XSS

## Flag

0FBB54BBF7D099713CA4BE297E1BC7DA0173D8B3C21C1811B916A3A86652724E

## Description

A clear and concise description of what the issue is about.

## URL

http://192.168.x.y/?page=feedback

## Steps To Reproduce

Leave a new feedback, using the form on the page.

Put the following:

```
Name:     anything

Message:  \<strong\>You've been hacked\</strong\>
```

Then valid the form with the `Sign Guestbook` button

## Possible fixes

- Escape the user input.
- Limit the charset to alpha characters only.

## Resources

There is no additional resource for this issue.
