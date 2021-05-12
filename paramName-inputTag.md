## collect hidden parameters

OneLiner: Collect hidden parameters from requests with parallel and grep

command greps parameters name in input tag

Exampele: ```<input name="something" >``` command extracts ```something``` parameter name


### Terminal:

``` 
cat urls | parallel -j 200 curl -s {} | grep "<input" | grep -oP 'name="[a-zA-Z0-9-_]{1,}' |  cut -d'"' -f2 | sort -u | tee params
```
