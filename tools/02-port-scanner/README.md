# 02 · port-scanner (week 4)

**Goal:** understand what nmap does by building a tiny version.

## Requirements
- TCP connect scan with the `socket` module
- Scan a port range: `python main.py 127.0.0.1 -p 1-1024`
- A timeout per port; use `concurrent.futures.ThreadPoolExecutor` for speed
- Print open ports, plus the banner if the service sends one

## Test against
`127.0.0.1` or your own VMs. **Never scan hosts you don't own.**

## Stretch
Compare your results with `nmap -sT` on the same target.
