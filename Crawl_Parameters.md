# Crawl parameters with getallurls

- Download gau | link: https://github.com/lc/gau
- Compile
```go build gau.go```

- Move ```gau``` to /usr/bin
```sudo mv gau /usr/bin```

### Usage:
```gau -subs domain.com | grep -oP "(\?|\&)\w+" | tr -d "?|&" | sort -u | tee params```

### GREP 
greping parameters in response body

```grep -oP "<input.*?>" | grep -oP "name=[\"|'].+" | cut -d "\"" -f2```

### crawl and Scan

* Add this function in .bashrc file

```
# Parameter scanner with Jaeles
checkparam(){
for i in $(cat $1); do
        curl -sk "$i" | grep -oP "<input.*?>" | grep -oP "name=[\"|'].+" | cut -d "\"" -f2 | tee params.txt
        jaeles scan -v -s ~/path_To_Jaeles_Signature/xss.yaml -u "$i"
        rm params.txt
done
}

```

* collect urls with your favorite tool. "Burp, gospider, hakrawler"
* check urls which includer "<input> tag" with ffuf

```
ffuf -u FUZZ -w urls.txt -mc all -mr "<input.*?>" | awk '{print $1}' | tee crawled.txt
```

* Scan collected urls, command for terminal

```
checkparam crawled.txt
```
