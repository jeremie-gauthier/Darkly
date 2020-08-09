# Unverified Form

## Flag

03A944B434D5BAFF05F46C4BEDE5792551A2595574BCAFC9A6E25F67C382CCAA

## Description

A form lacking of server side verification allow us to send invalid values to the database.

## URL

http://192.168.56.101/index.php?page=survey

## Steps To Reproduce

- Inspect the elements of the page.
- Choose a `<select>` and set the `value` of one of its `<option>` to a number higher than 10.
- Click on the modified `<option>`.

## Possible fixes

- Add some server side validation.

## Resources

There is no additional resource for this issue.
