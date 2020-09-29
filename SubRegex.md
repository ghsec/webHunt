### Extract Subdomains with burp + regexp
##### One Liner command
```
cat urls | grep -oP "([a-zA-Z0-9-_]{1,}\.){1,}domian.com" | tr -d "2F" | sort -u
```
