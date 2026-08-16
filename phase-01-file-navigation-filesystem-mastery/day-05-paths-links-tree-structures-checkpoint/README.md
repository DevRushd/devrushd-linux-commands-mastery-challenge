# Day 05: Paths, Links & Tree Structures

## Phase 1 - File Navigation & File System Mastery | Day 5 of 30

### Commands covered today
See [commands.md](./commands.md) for all 10 commands, their syntax and my own explanation of what each one does and when I would reach for it.

### What I practiced
I did a thorough hands-on practice with path and directory structure commands today. `tree` and `tree -L` gave me a way to actually see a folder's layout at once instead of stressing myself with repeated `ls` and `cd` commands. I created both a hard link with `ln` and a symbolic link with `ln -s`, then used `readlink` and `realpath` to confirm exactly what each one pointed to and resolve the real path behind it. `basename` and `dirname` also came in handy for pulling just the filename or just the folder out of a full path. I also tried using `pushd` and `popd` to bounce between two directories without retyping their paths, and used `ls -lt` to sort files by when they were last changed.

The part that took the longest was understanding the actual difference between a hard link and a symbolic link well enough to explain it without just repeating the definition.

See [drill.md](./drill.md) for the full task and the exact commands I ran.


### What surprised me
I assumed a hard link and a symlink worked the same way, but just with different names. They actually don't. A hard link points to the same data/content on your disk, so deleting the original doesn't break it. A symlink or soft link is just a pointer to a path, so deleting the original breaks it instantly. I only actually understood this after I tested both, and not from reading about it only.

### Evidence
Kindly find the screenshot or terminal transcript of the drill in [evidence/](./evidence).

### Related
Previous day: [day-04-searching-the-filesystem](../day-04-searching-the-filesystem/)

Next day: [day-06-reading-and-setting-permissions](../../phase-02-permissions-ownership-security/day-06-reading-and-setting-permissions/)