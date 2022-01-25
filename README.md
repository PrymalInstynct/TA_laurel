# TA_laurel
Technology Add-on for parsing Laurel Auditd Logs

Example Search Command
```
index=linux_events sourcetype=laurel_json ("SYSCALL.UID"=taco OR "SYSCALL.AUID"=taco OR "SYSCALL.UID"=root OR "SYSCALL.AUID"=root) NOT "PARENT_INFO.ARGV_STR"="*ansible*" ("PARENT_INFO.ARGV_STR"="*sudo*" OR "PARENT_INFO.ARGV_STR"="/usr/bin/bash*") "EXECVE.ARGV_STR"="*" 
| table _time,host,SYSCALL.UID,SYSCALL.AUID,PARENT_INFO.ARGV_STR,EXECVE.ARGV_STR
```
