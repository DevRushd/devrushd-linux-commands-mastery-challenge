# Day 02 — Practice Drill

## Task
Create a nested folder structure `practice/2026/april` in one command, create three empty files inside it, copy the folder to a backup location, rename one file, then safely delete only the empty directories left behind. 

## Commands Run (in order)

```shell
$ pwd
/home/devrushd

$ mkdir -p practice/2026/april

$ ls
practice
$ cd practice/2026/april/

$ touch file1 file2 file3

$ cd -
/home/devrushd/practice-drills

$ cp -r practice/ practice-bak/

$ ls
practice practice-bak

$ cd practice-bak/2026/april/

$ pwd 
/home/devrushd/practice-drills/practice-bak/2026/april

$ ls
file1 file2 file3

$ mv file1 first-file

$ ls
file2 file3 first-file

$ cd -
/home/devrushd/practice-drills

$ cd practice/2026/april/

$ pwd 
/home/devrushd/practice-drills/practice/2026/april

$ rm file1 file2 file3

$ ls

$ cd ../../..

$ pwd
/home/devrushd/practice-drills

$ ls 
practice practice-bak

$ rmdir -p practice/2026/april/

$ ls
practice-bak
```