# Day 04 — Practice Drill

## Task
Find every .conf file under /etc, find every file larger than 1MB in /var, then report total disk usage of /home and remaining free space on the root filesystem. 

## Commands Run (in order)

```shell
$ pwd
/home/devrushd

$ sudo find /etc -name "*.conf"

$ find /var -type f -size +1M

$ sudo du -sh /home
5.4G    /home

$ df -h /
Filesystem      Size  Used Avail Use% Mounted on
/dev/sdd       1007G  9.4G  947G   1% /