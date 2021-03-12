---
title: Scraping Data with Python
layout: post
author: Barco van Rhijn
category: Python
---
So I reached a point where I needed to get data from a 3rd party portal to send on to customers. 

I've got access to the backend but there's no API so making the data useful in a customer context requires some hacking. 

I ended up going with the Python Requests library and used Xpath

```
# create sesson
session_requests = requests.session()
# extract CSRF token using xpath and lxml
login_url = "https://example.com/login.php"
result = session_requests.get(login_url)
tree = html.fromstring(result.text)
authenticity_token = list(
set(tree.xpath("//input[@name='loginSubmit']/@value")))[0]

# login & send payload
result = session_requests.post(
login_url,
data=payload,
headers=dict(referer=login_url)
)
```
## Lessons learned
Load all the assets
- Interestingly it's important that you load all the assets (css and js) from the page to keep the scraper looking like a normal web client. Call it stealthy if you like.

- Useful for legacy integration.
Scraping if not used maliciously can actually save lots of integration time. When dealing with legacy systems managed by 3rd parties it's an indispensable technique. 

- Consider the resource you're scraping
Always consider if the 3rd party is ok with you doing this. In my case I have permission to use the information.

- Remember the CSRF token
CSRF tokens are a security measure to protect against bots. We're writing a scraping bot. But thankfully simpler forms are easy to submit - just include the CSRF token in the request after you identify and scrape it.

-Chasing a moving target
Sites that change structure frequently are harder to scrape consistently. There will always be times when scraping breaks and needs re-adjustment.

## Next Challenge
Scraping JS table data.
