# Recon with BurpSuite "სიყვარულით საქართველოდან"

### Download and run
* Download [Burp Suite](https://portswigger.net/burp/communitydownload)
* Run in terminal
```
java -jar burpsuite_community_v1.7.36.jar
```

### Set scope
* Scope --> Use advansed scope control --> Add --> host or IP range == target

![Scope](https://github.com/ghsec/webHunt/blob/master/Img/Screenshot%20from%202019-05-10%2002-25-10.png)

### Spidering 
* Select all host in sitemap and Spider. 
* Do it again and again if new hosts are noticed.

### Recon for new Subdomains
* Collect new subdimains which is not detected by spider. in request | response body.
```
(http[s]?:\/\/)?((-)?[\w+\.]){1,20}domain\.com
```
Note: click + button and check regex && Auto-scroll to match when text changes

![ReconSubdomain](https://github.com/ghsec/webHunt/blob/master/Img/Screenshot%20from%202019-05-10%2002-40-35.png)
