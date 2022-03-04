# AWS
Search AWS urls,keys in response body
### Regex

AMAZON_URL: ```https?://[^\"\\'> ]```

AMAZON_URL_1: ```[a-z0-9.-]+\.s3-[a-z0-9-]\\.amazonaws\.com```

AMAZON_URL_2: ```[a-z0-9.-]+\.s3-website[.-](eu|ap|us|ca|sa|cn)```

AMAZON_URL_3: ```s3\\.amazonaws\.com/[a-z0-9._-]```

AMAZON_URL_4: ```s3-[a-z0-9-]+\.amazonaws\\.com/[a-z0-9._-]```

URLS: ```https?://[^\"\\'> ]```

AMAZON_KEY: ```([^A-Z0-9]|^)(AKIA|A3T|AGPA|AIDA|AROA|AIPA|ANPA|ANVA|ASIA)[A-Z0-9]{12,}```

UPLOAD_FIELDS: ```<input[^>]\stype=[\"']?file[\"']?```


### Scan for s3 bucket takeover vuln

#### what you need 
* golang
* subfinder or other subdomain collector tool: ```https://github.com/projectdiscovery/subfinder```
* gospider: ```https://github.com/jaeles-project/gospider```
* httpx: ```https://github.com/projectdiscovery/httpx```
* Oneliner terminal command

```
subfinder -d hackerone.com -silent | httpx -silent | gospider -d 5 --sitemap --robots -w -r --subs | grep "\[aws-s3" | sed 's/\[aws-s3\] - //g' | httpx -silent -mr "NoSuchBucket" | tee s3-bucket-takeover.txt
```
