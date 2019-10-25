# Recon

Change domain.com with your domain

### crt.sh
```curl -s https://crt.sh/?q=%25.domain.com\&output=json | jq '.[].name_value' | sort -u | sed 's/"//g' | sed '/^*/d'```

### certspotter
```curl -s https://certspotter.com/api/v0/certs\?domain\=domain.com | jq '.[].dns_names[]' | sed 's/\"//g' | sed 's/\*\.//g' | sort -u | grep domain.com```

### Virustotal
```https://www.virustotal.com/gui/domain/domain.com/relations```

### SecurityTrails
```https://securitytrails.com/list/apex_domain/domain.com```

### Github
```https://github.com/search?q="domain.com"```

### Censys
```443.https.tls.certificate.parsed.names: domain.com```

### bgp
```https://bgp.he.net/```
