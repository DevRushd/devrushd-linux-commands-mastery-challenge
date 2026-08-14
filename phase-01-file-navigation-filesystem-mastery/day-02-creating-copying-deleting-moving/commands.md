# Day 02 — Commands: Creating, Copying, Moving, Deleting

---

## 1. `mkdir` - *Make Directory*

**Syntax:** `mkdir [options/flags] directory-name`

**What it does:** Creates a new and empty folder for you.

**Problem it solves:** When you are in the terminal, you can't create folders through a file explorer, and that brings you to using this command to create your project folders.

**Real-world scenario:** Starting a new personal project, you might want to run `mkdir project-folder` in order to create a single folder that will keep everything related to your project in one place.

**Example:**
```shell
mkdir traffic-app
mkdir -v traffic-app | ('-v' flag means 'verbose', which enables the printing of a confirmation message for each folder created.)
```

---

## 2. `mkdir -p` - *Make Directory with flag '-p' for Parent*

**Syntax:** `mkdir -p parent_dir/sub_dir1/sub_dir2`

**What it does:** Creates nested folders automatically in a single command.

**Problem it solves:** You do not need to bother whether a parent directory or sub-directory exists or not, this command automatically creates any missing directory in the desired path.

**Real-world scenario:** Organizing your practice files for this challenge, you might want to run `mkdir -p linux-challenge/day-02` to create the parent folder and the subfolder together and at the same time, even though neither of them existed yet.

**Example:**
```shell
mkdir -p traffic-app/config/log 
```

---

## 3. `touch` - *Create Files*

**Syntax:** `touch [options/flag] filename`

**What it does:** Creates new and empty files, and if the file already exists, it modifies its timestamp to the current time or any time you want without changing its content.

**Problem it solves:** Before writing a program or script, you need to create the file the program will reside in, this command lets you do that.

**Real-world scenario:** Setting up a new script, you might want to run `touch backup.sh` to create the empty file first, before opening it in an editor to actually write the code.

**Example:**
```shell
touch config.txt
touch file1 file2 file3 | ---> Creates multiple files at a go.
touch -t 202608140147 roles.yaml | --> '-t' flag means 'set timestamp', which sets the timestamp of 'roles.yaml' file to 14/08/2026 1:47AM.
```

---

## 4. `cp` - *Copy Files*

**Syntax:** `cp [options/flags] source destination`

**What it does:** Creates the duplicate of a file in the same or another specified location.

**Problem it solves:** You get duplicate files in your desired location without losing the original file in its initial location.

**Real-world scenario:** Before editing your `.bashrc` file, you might want to run `cp .bashrc .bashrc.bak` so that you can have a working copy to restore from if your changes break your terminal setup.

**Example:**
```shell
cp config.txt config.bak
cp /test/app.config /prod/ 
```

---

## 5. `cp -r` - *Copy Directories with '-r' for Recursive*

**Syntax:** `cp -r source destination`

**What it does:** Duplicates a folder with all files and directories inside it entirely.

**Problem it solves:** For duplicating project folders, backing up directories or copying a template folder.

**Real-world scenario:** Backing up a folder of notes before a big edit, you might want to run `cp -r notes/ notes-backup/` to duplicate the entire folder, not just a file inside it.

**Example:**
```shell
cp -r /dev/app-base/ /prod/
```

---

## 6. `mv` - *Move Files/Folders*

**Syntax:** `mv [options] source destination`

**What it does:** Moves files/folders from one location to another, and also renames files and folders.

**Problem it solves:** With this command, you get to reorganize or rename your fies and folders easily.

**Real-world scenario:** After finishing a draft, you might want to run `mv notes-draft.txt notes-final.txt` to rename the file once it's ready, without creating a duplicate copy.

**Example:**
```shell
mv oldfile.txt newfile.txt
mv /dev/app-code /test/dev/
```

---

## 7. `rm` - *Remove files*

**Syntax:** `rm [options/flags] filename`

**What it does:** Deletes files permanently.

**Problem it solves:** Helpful in deleting files you no longer need.

**Real-world scenario:** After confirming an unfinished or disrupted download, you might want to run `rm crdownload.file` to delete the leftover partial file your browser created during the download.

**Example:**
```shell
rm hub.txt
```

---

## 8. `rm -r` - *Removes Directories with '-r' as Recursive*

**Syntax:** `rm -r directories`

**What it does:** Deletes an entire directory with files and subfolders in it instantly.

**Problem it solves:** You need this command to delete directories as `rm` alone won't delete directory.

**Real-world scenario:** After finishing a temporary test folder you no longer need, you might want to run `rm -r test-folder/` to remove the folder along with every file inside it.

**Example:**
```shell
rm -r temporary-build old-build
```

---

## 9. `rm -rf` - *Deletes Directories recursively with '-f' for Force*

**Syntax:** `rm -rf directory`

**What it does:** Delates the specified path or directory, with all the files and subfolders in it forcefully without any confirmation prompt. 

**Problem it solves:** It comes handy when you want to clean up your system of old projects or automated scripts that makes your code pause and wait for confirmation on every processing it does.

**Real-world scenario:** Clearing out an old project you're starting over, you might want to run `rm -rf old-project/` to remove the entire folder and its contents in one go, without being asked to confirm each file.

**Example:**
```shell
rm -rf next_modules
```

---

## 10. `rmdir` - *Remove Directory*

**Syntax:** `rmdir directory`

**What it does:** Deletes only an empty directory or directories.

**Problem it solves:** Makes it safe to delete just empty folders when you are not sure whether they have contents or not.

**Real-world scenario:** After manually deleting the files inside a folder, you might want to run `rmdir empty-folder/` to remove the folder itself, and have it refuse to run if you missed a file and it isn't actually empty yet.

**Example:**
```shell
rmdir blank-folder
```