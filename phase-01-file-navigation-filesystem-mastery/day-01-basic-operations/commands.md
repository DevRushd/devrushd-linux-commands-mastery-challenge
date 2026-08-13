# Day 02 — Commands: Creating, Copying, Moving, Deleting.

---

## 1. `mkdir` - *Make Directory*
**Syntax:** `mkdir [options] directory_name`
**What it does:** It creates a new, empty folder for you. 
**When to use it:** When building your app or project folder structure to keep your files organized.
**Real-world scenario:** Starting a new personal project, you might open your terminl, `cd` into your desired directory,  and run `mkdir devrushd-app-project` to create a single folder to keep everything related to that project in one place.
**Example:**
```bash
mkdir devrushd
mkdir -v devrushd | ('-v' for verbose, prints confirmation message when each folder is created)
```

## 2. `mkdir -p` - *Make Directory with '-p' flag/option as Parents*
**Syntax:** `mkdir -p /parent-directory/child-directory`
**What it does:** It automatically creates a lot of nested folders with a single command, you can create as many parent folders and a child folder as you want even if anyone of them have not being created before
**When to use it:** When setting up a multi-layer structure for your project at once.
**Real-world scenario:** Organizing your practice files for a challenge like this, you might want to run `mkdir -p linux-challenge/day-02` to create the parent folder(linux-challenge) and the day's subfolder/child folder(day-02) together, even though neither of them existed yet.
**Example:**
```bash
mkdir -p devrushd/gridsynk/frontend
```

## 3. `touch` - *Creates New File*
**Syntax:** `touch [options] file-name`
**What it does:** It simply creates a new empty file for you, and if the file already exists, it updates the timestamp to the time it was last modified(as at when you ran `touch` command on the filename again) without changing its content. 
**When to use it:** When creating empty config & placeholder files, and updating a file's timestamp.
**Real-world scenario:** While writing a new script, you might want to run `touch script.sh` to create an empty file first, before opening it in an editor(nano/vim/vscode) to actually write the code.
**Example:**
```bash
touch traffic-app.log
touch -t app.config | ('-t' sets a specific timestamp instead of using the current time)
```

## 4. `cp` - *Copy Files*
**Syntax:** `cp [options] source destination`
**What it does:** It creates the duplicate of your file(s) for you in another location that you specify. 
**Real-world scenario:** Before editing your **.bashrc** file, you might want to run `cp .bashrc .bashrc.bak` so that you can have a working copy to restore from if your changes break your terminal setup.
**Example:**
```bash
cp env.example env | (duplicates the file in the same folder)
cp /config/app.log /logs/app/gridsynk-app.log (copies the file into another folder with another name)
```

## 5. `cp -r` - *Copy Files with '-r' flag/option for recursive*
**Syntax:** `cp -r source-directory destination-directory`
**What it does:** It lets you copy your entire folder with the subfolders and files in it, into your desired location or directory. 
**When to use it:** When copying project folders, backing up directories, and creating a new project folder by copying an existing template folder structure.
**Real-world scenario:** Backing up a folder of notes before a big edit, you might want to run `cp -r notes/ notes-backup/` to duplicate the entire folder, not just a file inside it.
**Example:**
```bash
cp -r nodejs-app-template wafiy-app-project
```

## 6. `mv` - *Move File(s)/Directory*
**Syntax:** `mv [options] source destination`
**What it does:** It moves file or folder from one location to another, and also renames a file in the same location. 
**When to use it:** When renaming files or moving them to another directory.
**Real-world scenario:** After finishing a draft, you might want to run `mv notes-draft.txt notes-final.txt` to rename the file once it's done, without creating a duplicte.
**Example:**
```bash
mv script.py /templates
```

## 7. `rm` - *Remove/Delete files*
**Syntax:** `rm [options] file_name`
**What it does:** It permanently deletes your file without keeping a copy in any recycle bin.
**When to use it:** When deleting certain files you are sure you will not be needing anymore.
**Real-world scenario:** After confirming a download completed correctly, you might want to run `rm setup.sh.part` to delete the leftover partial file your browser or terminal created during the download.
**Example:**
```bash
rm crdownload.txt
```

## 8. `rm -r` - *Remove/Delete files with '-r' for recursive*
**Syntax:** `rm -r directory_name`
**What it does:** It deletes an entire folder and everything inside it, including subfolders and files. 
**When to use it:** When deleting a directory you no longer need in your project.
**Real-world scenario:** After finishing a temporary test folder you no longer need, you might want to run `rm -r test-folder/` to remove the folder along with every file inside it.
**Example:**
```bash
rm -r old-config
```

## 9. `rm -rf` - *Remove/Delete files with '-r' for recursive and '-f' for forcefully*
**Syntax:** `rm -rf directory_name`
**What it does:** It deletes a folder with everything inside it forcefully, even when it is write-protected, without any confirmation prompt. 
**When to use it:** Only when you are very **certain** of the exact path, folder and files in it, and you very sure you won't be needing them anymore.
**Real-world scenario:** Clearing out an old project you're starting over, you might want to run `rm -rf old-project/` to remove the entire folder and its contents in one go, without being asked to confirm each file.
**Example:**
```bash
mkdir devrushd
mkdir -v devrushd
```

## 10. `rmdir` - *Removes a Directory*
**Syntax:** `rmdir [options] directory_name`
**What it does:** It deletes an empty directory only. 
**When to use it:** When cleaning up empty leftover folders.
**Real-world scenario:** After moving all files out of a folder with `mv`, you might want to run `rmdir temp-folder` to remove the empty directory entirely.
**Example:**
```bash
rmdir staging-directory
```
