## AWS API Gateway

```
[0-9a-z]+.execute-api.[0-9a-z._-]+.amazonaws.com
```

Example: https://grep.app/search?q=%5B0-9a-z%5D%2B.execute-api.%5B0-9a-z._-%5D%2B.amazonaws.com&regexp=true


## AWS API Key

```
AKIA[0-9A-Z]{16}
```

Example: https://grep.app/search?q=AKIA%5B0-9A-Z%5D%7B16%7D&regexp=true

## AWS ARN

```arn:aws:[a-z0-9-]+:[a-z]{2}-[a-z]+-[0-9]+:[0-9]+:.+```

Example: https://grep.app/search?q=arn%3Aaws%3A%5Ba-z0-9-%5D%2B%3A%5Ba-z%5D%7B2%7D-%5Ba-z%5D%2B-%5B0-9%5D%2B%3A%5B0-9%5D%2B%3A.%2B&regexp=true
