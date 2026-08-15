# Day 03 — Commands: Reading & Inspecting Files

---

## 1. `cat` - *Concatenate and Display File Content*

**Syntax:** `cat [options/flags] filename`

**What it does:** Reads a file you specify and displays its entire content straight back to you on the terminal from the beginning to the end.

**Problem it solves:** You need a quick look at a short file's content without opening a text editor.

**Real-world scenario:** After a deployment script finishes, you might run `cat deploy-output.log` to quickly check what happened, without launching an editor for a file you're not going to modify.

**Example:**
```shell
cat notes.txt
cat /etc/hostname
```

---

## 2. `less` - *View File Content Page by Page*

**Syntax:** `less filename`

**What it does:** Opens a file and loads it for you to view one page at a time, letting you scroll up and down without loading the whole thing on your screen at once.

**Problem it solves:** `cat` dumps a huge file all at once and floods your terminal; `less` lets you read it at your own pace instead.

**Real-world scenario:** Investigating a server issue, you might run `less /var/log/syslog` to scroll through a large log file page by page, searching for the relevant entry, instead of everything loaded on your terminal making it clumsy and complex to find pain points.

**Example:**
```shell
less /var/log/syslog
less requirements.txt
```

---

## 3. `head` - *View the Beginning of a File*

**Syntax:** `head [options] filename`

**What it does:** Prints the first 10 lines of a file by default.

**Problem it solves:** You just need to confirm what a file looks like at the top; say you want to take a quick look at its structure, headers, or first few lines without you opening the whole file.

**Real-world scenario:** Checking a freshly generated CSV export, you might run `head data.csv` to confirm the column headers look correct before processing the full file.

**Example:**
```shell
head access.log 
head /etc/passwd
```

---

## 4. `head -n` - *View a Specific Number of Lines from the Start*

**Syntax:** `head -n [number] filename`

**What it does:** Prints the stated number of lines from the beginning of a file, instead of the default 10.

**Problem it solves:** Sometimes 10 lines is too few or too many to actually see what you need.

**Real-world scenario:** Reviewing a config file, you might run `head -n 20 nginx.conf` to see just the first 20 lines where the main server block usually sits.

**Example:**
```shell
head -n 5 error.log
head -n 50 app.log
```

## 5. `tail` - *View the End of a File*

**Syntax:** `tail filename`

**What it does:** Prints the last 10 lines of a file by default.

**Problem it solves:** The most recent entries in a log or file are usually at the bottom, and scrolling through the whole file to find them will waste your time.

**Real-world scenario:** After a deployment, you might run `tail deploy.log` to see the last few lines and confirm whether it finished successfully or failed.

**Example:**
```shell
tail app.log
tail /var/log/auth.log
```

---

## 6. `tail -f` - *Follow a File Live as It Grows*

**Syntax:** `tail -f filename`

**What it does:** Keeps the file open and prints new lines to the terminal in real time as they're written.

**Problem it solves:** You need to watch a file update live, instead of repeatedly running `tail` at subsequent times to check for new entries.

**Real-world scenario:** While a deployment is running, you might run `tail -f deploy.log` to watch the process unfold live and catch an error the moment it happens.

**Example:**
```shell
tail -f /var/log/nginx/access.log
tail -f app.log
```

## 7. `wc` - *Word, Line, and Byte Count*

**Syntax:** `wc filename`

**What it does:** Counts the lines, words, and bytes in a file, and prints all three by default.

**Problem it solves:** You need a quick size or content check on a file without opening it.

**Real-world scenario:** Before processing a data export, you might run `wc data.csv` to get a sense of how large the file is, getting to see the number of lines, words, and bytes before deciding how to handle it.

**Example:**
```shell
wc report.txt
wc access.log
```

---

## 8. `wc -l` - *Count Lines Only*

**Syntax:** `wc -l filename`

**What it does:** Counts and prints only the number of lines in a file.

**Problem it solves:** Most of the time you only care about the line count, not the word or byte count that `wc` gives you by default.

**Real-world scenario:** Checking a log file after an incident, you might run `wc -l error.log` to quickly see how many error entries piled up.

**Example:**
```shell
wc -l users.csv
wc -l /var/log/syslog
```

---

## 9. `file` - *Identify File Type*

**Syntax:** `file filename`

**What it does:** Inspects the stated/specified file and tells you what kind of file it actually is, regardless of its extension.

**Problem it solves:** A file's extension can be skeptical or missing entirely, and you need to know its real format before trying to open or process it.

**Real-world scenario:** You download a file with no extension from a server, you might run `file backup` to confirm whether it's actually a `.tar.gz` archive, a plain text file, or something else, before deciding how to handle it.

**Example:**
```shell
file backup
file script.sh
```

## 10. `stat` - *View the Detailed Metadata of a File*

**Syntax:** `stat filename`

**What it does:** Shows detailed metadata about a file; its size, permissions, owner, and the exact timestamps for when it was last accessed, modified, and changed.

**Problem it solves:** `ls -l` gives you a summary, but sometimes you need the full detail, especially exact timestamps, which `ls -l` doesn't show precisely.

**Real-world scenario:** Investigating whether a config file was recently changed without authorization, you might run `stat nginx.conf` to check its exact last-modified timestamp.

**Example:**
```shell
stat app.log
stat /etc/passwd
```