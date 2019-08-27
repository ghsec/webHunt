### Open Redirect|SSRF

Possible Open Redirect | SSRF detection Regexp

```
(=|%3d)(http(s)?:\/\/\w+|aHR0)
```
### Detect Open Redirect in response

```
.*?; *?URL *?= *?(.*)|window\.location(\s=\s|\.href|\.replace)?(\(|\s=\s)?(https\:\/\/www\.)?google\.com(\))|Location:\shttps:\/\/www\.google\.com
```
#### Payloads:
https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Open%20Redirect/Intruder
