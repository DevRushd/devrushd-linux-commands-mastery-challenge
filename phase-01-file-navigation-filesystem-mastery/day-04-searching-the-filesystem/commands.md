# Day 04 — Commands: Searching the Filesystem

---

## 1. `find -name` - *Search Files by Name*

**Syntax:** `find [path] -name "pattern"` (path - '.' for current directory, '/' for the whole filesystem)

**What it does:** Searches through a directory tree and finds files or folders matching a specific name or pattern.

**Problem it solves:** You could barely remember the full name of a file or exactly where it is in the filesystem but you could still do a rough guess.

**Real-world scenario:** Checking a server's configuration, you might run `find /etc -name "*.conf"` to locate every config file under `/etc`, without knowing the exact folder each one lives in.

**Example:**
```shell
find /home -name "notes.txt"
find /etc -name "*.conf"
```

---

## 2. `find -type` - *Search by File Type*

**Syntax:** `find [path] -type [f|d|l]`

**What it does:** Filters your search results by type — `f` for regular files, `d` for directories, and `l` for symbolic links.

**Problem it solves:** You want to find files specifically or folders specifically without getting results that match both type at the same time.

**Real-world scenario:** Cleaning up a project, you might run `find . -type d -name "node_modules"` to locate every `node_modules` folder specifically, without matching any files that happen to share the name.

**Example:**
```shell
find . -type f -name "*.log"
find /var/www -type d
```

---

## 3. `find -size` - *Search by File Size*

**Syntax:** `find [path] -size [+/-]N[unit]`

**What it does:** Finds files larger or smaller than the size you specify, using units like `k` (KB), `M` (MB), or `G` (GB).

**Problem it solves:** You need to track down files eating up disk space, but don't know their names or exact locations.

**Real-world scenario:** A server's disk is filling up, so you might run `find /var -size +1M` to list every file in `/var` larger than 1MB, and narrow down what's actually taking up the space.

**Example:**
```shell
find /var -size +1M
find /home -size -100k
```

---

## 4. `find -mtime` - *Search by Last Modified Time*

**Syntax:** `find [path] -mtime [+/-]N`

**What it does:** Finds files based on how many days ago they were last modified — `+N` for more than N days, `-N` for less than N days.

**Problem it solves:** You need to identify files that haven't been touched in a while, or recently changed files that needs to be checked or investigated.

**Real-world scenario:** Cleaning up your old build artifacts, you might run `find /tmp -mtime +30` to find every file in `/tmp` untouched for more than 30 days, and safely mark them for deletion.

**Example:**
```shell
find /tmp -mtime +30
find /var/log -mtime -1
```

## 5. `find -perm` - *Search by Permissions*

**Syntax:** `find [path] -perm [mode]`

**What it does:** Finds files that match a specific permission setting.

**Problem it solves:** You need to spot files with incorrect or risky permissions across a large filesystem, rather than checking each one manually with `ls -l`.

**Real-world scenario:** Running a security check, you might run `find / -perm 777` to search the entire system for files that are readable, writable and executable by everyone.

**Example:**
```shell
find / -perm -u+w # Search for files that are writable by users 
find /home -perm 777
```

---

## 6. `locate` - *Fast File Search Using an Index*

**Syntax:** `locate filename`

**What it does:** Searches the database (a prebuilt index) of the filesystem for files matching a name, returning results almost instantly.

**Problem it solves:** `find` searches live and can be slow on a large filesystem; `locate` is much faster because it searches a database instead.

**Real-world scenario:** Trying to quickly find where a config file lives system-wide, you might run `locate nginx.conf` and get an instant result, instead of waiting on a live `find` search across the whole disk.

**Example:**
```shell
locate nginx.conf
locate .bashrc
```

## 7. `updatedb` - *Refresh the locate Database*

**Syntax:** `sudo updatedb`

**What it does:** Rebuilds the index that `locate` searches, so it reflects the current state of the filesystem.

**Problem it solves:** `locate` can return outdated or missing results if a file was created or deleted after the index was last built.

**Real-world scenario:** After installing a new package, you might run `sudo updatedb` first, so a follow-up `locate` command actually finds the new files instead of missing them because the index is stale.

**Example:**
```shell
sudo updatedb
locate newfile.conf
```

---

## 8. `du` - *Check Disk Usage of Files and Folders*

**Syntax:** `du [path]`

**What it does:** Tells you how much disk space files and directories are using.

**Problem it solves:** You need to know what's consuming space on your disk, folder by folder, not just the overall free space left.

**Real-world scenario:** Investigating a server running low on space, you might run `du /var/log` to see the disk usage of every file inside that directory and narrow down the source.

**Example:**
```shell
du /var/log
du /home/ec2-user
```

---

## 9. `du -sh` - *Summarized, Human-Readable Disk Usage*

**Syntax:** `du -sh [path]`

**What it does:** Shows the total disk usage of a folder as a single summarized, human-readable size, instead of listing every file inside it.

**Problem it solves:** Plain `du` can print a long, hard-to-read list; `-sh` gives you one clean total instead.

**Real-world scenario:** Checking how much space a project folder is taking up, you might run `du -sh /home/ec2-user/myapp` to get one clear number like `2.3G`, instead of a breakdown of every file inside it.

**Example:**
```shell
du -sh /home/ec2-user/myapp
du -sh /var/log
```

## 10. `df -h` - *Check Free Disk Space, Human-Readable*

**Syntax:** `df -h`

**What it does:** Shows how much space is used and available across all mounted filesystems, in human-readable sizes like GB and MB.

**Problem it solves:** You need a quick overview of overall disk space, not just usage inside one specific folder.

**Real-world scenario:** A server starts throwing "disk full" errors, so you might run `df -h` first to confirm which mounted volume is actually out of space, before digging into individual folders with `du`.

**Example:**
```shell
df -h
df -h /var
```