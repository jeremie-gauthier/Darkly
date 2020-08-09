http://192.168.56.3/index.php?page=redirect&site=EVIL_URL

https://www.vaadata.com/blog/fr/comprendre-les-vulnerabilites-web-en-5-min-episode-10-redirections-et-renvois-non-valides/

# Open Redirect

## Flag

B9E775A0291FED784A2D9680FCFAD7EDD6B8CDF87648DA647AAF4BBA288BCAB3

## Description

The PHP code obtains a URL from the query string and then redirects the user to that URL.

## URL

http://192.168.x.y/index.php?page=redirect&site=EVIL_URL

## Steps To Reproduce

- Type the URL in your address bar.

## Possible fixes

- Remove those redirections.
- Verify the `referrer` during the redirection.
- Disable redirections outside the website domain.
- Use a whitelist of destinations.
- Sign the redirection with a hash and control its validity.

## Resources

There is no additional resource for this issue.
