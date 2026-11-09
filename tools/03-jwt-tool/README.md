# 03 · jwt-tool (week 7)

**Goal:** understand JWT attacks deeply. You use JWTs in Next.js; now break them.

## Requirements
- `decode`: split on `.`, base64url-decode the header and payload, pretty-print the JSON
- `none`: rebuild the token with `"alg":"none"` and an empty signature
- `crack`: try each secret from a wordlist with HMAC-SHA256 until the signature matches
- `forge`: sign a modified payload with a known secret

## Test against
PortSwigger JWT labs, and tokens from your own apps.
