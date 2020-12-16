# Spidering with Gospider
[Gospider](https://github.com/jaeles-project/gospider)

### Collect Endpoints

Collect URLs and save to file: 
```
gospider -S hosts -d 16 -a -c 250 | tee gospider
```

### Extract urls

```
cat gospider | grep -oP "http(s)?://((?i)(([a-zA-Z0-9]{1}|[_a-zA-Z0-9]{1}[_a-zA-Z0-9-]{0,61}[a-zA-Z0-9]{1})[.]{1})+)?domain.com.*" | tee extract
```

### Sort unique urls

```
cat extract | sort -u | grep -oP "http(s)?://((?i)(([a-zA-Z0-9]{1}|[_a-zA-Z0-9]{1}[_a-zA-Z0-9-]{0,61}[a-zA-Z0-9]{1})[.]{1})+)?domain.com.*" | tee urls
```

