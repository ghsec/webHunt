# Recon

Change domain.com with your domain

### crt.sh
```curl -s https://crt.sh/?q=%25.domain.com\&output=json | jq '.[].name_value' | sort -u | sed 's/"//g' | sed '/^*/d'```
