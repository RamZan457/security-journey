# 04 · recon (week 11)

**Goal:** automate the boring first hour of every bug bounty target.

## Requirements
- Input: a root domain **that is in scope** for a program
- Run `subfinder`, pipe to `httpx`, and save live hosts with status codes and titles
- One output folder per target: `output/<domain>/subdomains.txt`, `live.txt`
- Use `subprocess`, and handle the case where a tool isn't installed

## Stretch
Extract URLs and endpoints from the JavaScript files of live hosts.

**Always check the program's scope and rules first. Some programs ban automated scanning.**
