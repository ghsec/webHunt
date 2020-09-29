### Extract Subdomains with burp + regexp
##### One Liner command
```
([a-zA-Z0-9-_]{1,}\.){1,}domian\.com"
```

### Terminal : OneLiner
```
cat urls | grep -oP "([a-zA-Z0-9-_]{1,}\.){1,}domain\.com" | tr -d "2F" | sort -u
```
