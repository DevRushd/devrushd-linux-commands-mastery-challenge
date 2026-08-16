# Day 05 — Commands: Paths, Links & Tree Structures 

---

## 1. `tree` - *Display Directory Structure as a Tree*

**Syntax:** `tree [path]`

**What it does:** Prints the full folder and file structure of a directory in a visual and branching tree form.

**Problem it solves:** `ls` only shows one level of the directory struture at a time; and understanding a project's whole layout by running `ls` repeatedly is slow and hard to picture.

**Real-world scenario:** Being introduced to an unfamiliar Terraform project, you might run `tree terraform/` to see the entire module structure at a glance, instead of `cd`-ing into every folder one by one.

**Example:**
```shell
tree .
tree /etc/nginx
```

---

## 2. `tree -L` - *Limit Tree Depth*

**Syntax:** `tree -L [number] [path]`

**What it does:** Displays the directory tree, but only down to a specified number of levels deep.

**Problem it solves:** A full `tree` on a large project can print hundreds of lines and become unreadable; limiting the depth keeps the output manageable.

**Real-world scenario:** Getting a quick overview of `/etc` without every nested config file flooding your screen, you might run `tree -L 2 /etc` to see just the top two levels.

**Example:**
```shell
tree -L 2 /etc
tree -L 1 terraform/
```

---

## 3. `ln` (hard link) - *Create a Hard Link*

**Syntax:** `ln source_file link_name`

**What it does:** Creates a second name for the same file data on disk with both names pointing to the exact same content, and editing one edits the other.

**Problem it solves:** You need two file paths that always stay perfectly in sync, without duplicating the actual data or maintaining two separate copies, thereby limiting storage space utilization.

**Real-world scenario:** Keeping a script accessible from two different paths without duplicating it, you might run `ln script.sh /usr/local/bin/script.sh` so both locations always reflect the exact same file.

**Example:**
```shell
ln notes.txt notes-link.txt
ln deploy.sh /usr/local/bin/deploy
```

---

## 4. `ln -s` (symbolic link) - *Create a Symbolic (Soft) Link*

**Syntax:** `ln -s target link_name`

**What it does:** Creates a shortcut file/folder that points to another file/folder by path, rather than sharing the same underlying data.

**Problem it solves:** You need a shortcut to a file or folder, possibly across different filesystems or directories, without duplicating anything.

**Real-world scenario:** Managing multiple versions of an app, you might run `ln -s /opt/myapp/v2 /opt/myapp/current` so `current` always points to whichever version is active, and switching versions is just repointing one link.

**Example:**
```shell
ln -s /etc/nginx/sites-available/app.conf /etc/nginx/sites-enabled/app.conf
ln -s /opt/myapp/v2 current
```

## 5. `readlink` - *Show What a Symbolic Link Points To*

**Syntax:** `readlink link_name`

**What it does:** Prints the target path that a symbolic link points to.

**Problem it solves:** A symlink's destination isn't always obvious just by looking at it in a file listing; `readlink` confirms exactly where it leads.

**Real-world scenario:** Investigating a config that isn't loading as expected, you might run `readlink /etc/nginx/sites-enabled/app.conf` to confirm it's actually pointing to the correct file in `sites-available`.

**Example:**
```shell
readlink current
readlink /etc/nginx/sites-enabled/app.conf
```

## 6. `realpath` - *Resolve the Full Absolute Path*

**Syntax:** `realpath path`

**What it does:** Prints the full, absolute path of a file, resolving any symbolic links and relative references (like `.` or `..`) along the way.

**Problem it solves:** You're working with a relative path or a series of linked symlinks and need to know the exact, real location of the file on disk.

**Real-world scenario:** Debugging a script that behaves differently depending on where it's run from, you might use `realpath script.sh` to confirm its true absolute location, regardless of your current directory.

**Example:**
```shell
realpath script.sh
realpath ../config/app.yml
```

## 7. `basename` - *Extract the Filename from a Path*

**Syntax:** `basename path`

**What it does:** Strips away the directory portion of a path and returns just the filename at the end.

**Problem it solves:** In a script, you often have a full path but only need the filename itself, without manually trimming the string.

**Real-world scenario:** Writing a backup script, you might use `basename /var/log/app.log` to extract just `app.log` from the full path, so you can rename or reference it cleanly elsewhere in the script.

**Example:**
```shell
basename /var/log/app.log
basename /home/ec2-user/deploy.sh
```

---

## 8. `dirname` - *Extract the Directory from a Path*

**Syntax:** `dirname path`

**What it does:** Strips away the filename from a path and returns just the directory portion.

**Problem it solves:** In a script, you often need to know the folder a file lives in, without manually parsing the path string yourself.

**Real-world scenario:** Writing a deployment script that needs to `cd` into a file's parent folder before running something, you might use `dirname /opt/myapp/deploy.sh` to get `/opt/myapp` automatically.

**Example:**
```shell
dirname /opt/myapp/deploy.sh
dirname /var/log/app.log
```

---

## 9. `pushd` / `popd` - *Navigate with a Directory Stack*

**Syntax:** `pushd path` / `popd`

**What it does:** `pushd` saves your current directory onto a stack and moves you to the path you stated; `popd` checks the stack for your previous directory and takes you back to where you were before.

**Problem it solves:** Jumping between more than two directories repeatedly with plain `cd` means retyping paths or losing track of where you came from; the stack remembers multiple locations for you.

**Real-world scenario:** Working across several Terraform module folders at once, you might `pushd modules/vpc` to jump in and work, then `popd` to instantly return to exactly where you started, without retyping the original path.

**Example:**
```shell
pushd terraform/modules/vpc
popd
```

## 10. `ls -lt` - *List Files Sorted by Modification Time*

**Syntax:** `ls -lt [path]`

**What it does:** Lists files in long format, sorted from most recently modified to oldest.

**Problem it solves:** In a folder with many files, you need to quickly find what changed most recently without checking timestamps one by one.

**Real-world scenario:** Investigating a server issue, you might run `ls -lt /var/log` to instantly see which log file was written to most recently, pointing you toward the one most likely related to the problem.

**Example:**
```shell
ls -lt /var/log
ls -lt terraform/
```