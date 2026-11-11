# OverTheWire Bandit

- Telling linux it's file use so read it. e.g. file name is `-`, `cat ./- OR  cat < -`

- Find a file:
    - `find . -type f -size 1033c ! -executable`  current directory, type, size in bytes, not exec
    - `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null` root directory, type, user, group, size, Hide permission-denied errors

- `grep` searches for specific text inside files.
    - `grep "millionth" data.txt` OR `cat data.txt | grep millionth`

- Sort lines alphabetically and find unique:
    - `sort filename | uniq -u`
    - `|` Passes output from one command to another

- Extract human-readable strings and find the one preceded by several = characters
    - `strings data.txt | grep "==="`  Extracts human-readable text from binary data pass to next and find strings

- Base64-decoded format to encode:
    - `echo -n "hello" | base64`
    - `base64 data.txt`

- Base64-encoded format to decode:
    - `base64 -d data.txt`
    - `cat data.txt | base64 --decode`