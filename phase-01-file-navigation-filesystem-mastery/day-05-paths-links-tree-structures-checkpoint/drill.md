# Day 05 — Practice Drill

## Task
CHECKPOINT. Create a symbolic link to a config file, resolve its real path, print a two-level tree of /etc, and explain to a peer, in your own words, the difference between a hard link and a symbolic link.  

### Differences Between Hard Link & Soft Link
- *Hard link* creates a link file that points directly to the content of the target link file i.e they both share the same underlying file content; while *Soft link* creates a link file or folder that points to the target link file folder and not its content directly.
- *Hard link* can only be used to link files, not directories; while *Soft link* can be used to link both files and directories.  

## Commands Run (in order)

```shell
$ pwd
/home/devrushd

$ ln -s /var/log/fontconfig.log config.log

$ ls -l
total 4
lrwxrwxrwx 1 devrushd devrushd   23 Aug 16 13:24 config.log -> /var/log/fontconfig.log
drwxr-xr-x 3 devrushd devrushd 4096 Aug 13 04:17 practice-bak

$ realpath config.log
/var/log/fontconfig.log

$ tree -L 2 /etc


