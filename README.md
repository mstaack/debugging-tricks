# debugging-tricks

## processes with memory

ps aux --sort -rss

## connection stats
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
