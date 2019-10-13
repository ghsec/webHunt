# Subdomains to Burp Suite
Export subdmains from file to Burp suite by https://twitter.com/Deepak_maxx

```cat <file-name> | parallel -j 200 curl -L -o /dev/null {} -x 127.0.0.1:8080 -k -s```
