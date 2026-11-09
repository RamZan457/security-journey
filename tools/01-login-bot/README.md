# 01 · login-bot (week 2)

**Goal:** log into a web app with Python, the way a browser does.

## Requirements
- Use `requests.Session()` so cookies persist between requests
- GET the login page and parse the CSRF token from the HTML (`re` or BeautifulSoup)
- POST the username, password and CSRF token
- Detect success or failure (redirect, status code, or text on the page)
- CLI: `python main.py --url <login-url> --user <u> --password <p>`

## Test against
Your own local app (any of your MERN or Laravel projects), or a PortSwigger lab.

## Stretch
Read passwords from a wordlist and stop on success. You'll use this to solve PortSwigger's brute-force labs.
