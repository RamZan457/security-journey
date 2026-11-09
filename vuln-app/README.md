# vuln-app (weeks 5–6)

A deliberately vulnerable app, built with the stack you already know (MERN or Next.js).
Building the bugs yourself teaches you where real developers make mistakes, and that's exactly what AppSec engineers look for.

## Build these 5 bugs
1. **NoSQL injection** in the login (`{"$ne": null}`)
2. **IDOR**: `/api/orders/:id` returns any user's order
3. **Stored XSS**: comments rendered with `dangerouslySetInnerHTML`
4. **CSRF**: a state-changing POST with no token and `SameSite=None` cookies
5. **Command injection**: a "ping a host" feature using `child_process.exec`

## Then
- Exploit each one with Burp (week 6)
- Fix each one in a separate commit
- Write `WRITEUP.md`: the attack, the root cause and the fix for each bug

⚠️ **Run it on localhost only. Never deploy this app publicly.**
