# Day 03 — Practice Drill

## Task
Pick any log file on the system. View it fully with cat, page through it with less, show the first and 
last 15 lines, count its lines, identify its file type, and inspect its full metadata with stat.  

## Commands Run (in order)

```shell
$ pwd
/home/devrushd

$ cd /var/log

$ ls

$ cat syslog
# Displays a whole lot of text

$ less syslog # Up & Down Arrow Key / Spacebar Key - to move up and down line by line (Pg Up/Pg Down - works for page by page), 'q' - to quit the reading mode and get back to the terminal.  
# Gets into a reading mode and you decide yourself when you want to go the next page. To exit, press 'q'

$ head -n 15 syslog
# Shows fist 15 lines of the file

$ tail -n 15 syslog
# Shows last 15 lines of the file

$ wc -l syslog
1320 syslog # 1,320 lines

$ file syslog
syslog: ASCII text, with very long lines (327)

$ stat syslog
    File: syslog
    Size: 181129          Blocks: 368        IO Block: 4096   regular file
Device: 8,48    Inode: 11896       Links: 1
Access: (0640/-rw-r-----)  Uid: (  102/  syslog)   Gid: (    4/     adm)
Access: 2026-08-15 22:40:18.073278525 +0100
Modify: 2026-08-15 22:40:13.597278665 +0100
Change: 2026-08-15 22:40:13.597278665 +0100
 Birth: 2026-08-11 10:22:19.021924053 +0100
```