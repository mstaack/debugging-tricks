# debugging-tricks

## avarage memory by apache processes (like in php prefork mode)

```
user@devserver:~$ ps -ylC apache2 | awk '{x += $8;y += 1} END {print "Apache Memory Usage (MB): "x/1024; print "Average Process Size (MB): "x/((y-1)*1024)}'
Apache Memory Usage (MB): 60071.1
Average Process Size (MB): 162.794

```
## global connection stats
```
user@devserver:~$ netstat -ant | awk '{print $6}' | sort | uniq -c | sort -n
      1 Foreign
      1 Verbindungen)
      7 CLOSING
     12 FIN_WAIT1
     14 LAST_ACK
     14 SYN_RECV
     16 LISTEN
    122 FIN_WAIT2
   3055 VERBUNDEN
  12889 TIME_WAIT
  ```
