# XEE Injection
### Errors Regexp
```
simplexml_load_string|parser error :|An error occured!
```
### Detect Payload
```
<!DOCTYPE foo [<!ENTITY xxe "XEE VULN IS HERE"> ]>
```
```XEE VULN IS HERE``` reflects in respose
