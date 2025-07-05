# Linux-Cloud-Learning-Journey

## About

This repository documents my daily learning progress as I build my skills for Cloud Administration and Computing roles.

---

## Day 1 - June 23, 2025

- Started my Linux journey:  
  - Installed VirtualBox and Ubuntu VM  
  - Adjusted BIOS and Windows settings to enable virtualization  
- Learned terminal shortcuts:  
  - Clear command line, open/close terminal
- Practiced basic Linux commands:  
  - `date`, `echo`, `cal`, `history`  
  - Explored adding options and inputs to these commands
- Learned how to check the path of commands using `$PATH` and understood its purpose
- Learned core Linux concepts:  
  - Terminal, Shell, Commands, and how they interact together
- Explored command options:  
  - `-A`, `-B`, combined short options, long options using `--`
- Learned about the Linux Manual (`man` command):  
  - How to access, navigate, and interpret manuals
  - Understood key notations:  
    - `[]` = optional  
    - `<>` = required  
    - `|` = choose between options

---

# Upcoming Topics
 -Standard Input ,Outputs and Errors
 -Redirection basics and advanced
 -sort, grep, cut commands

## Day 2 - June 24, 2025

  Day 2 - June 24, 2025
   - Learned about Linux input/output system:
       -    Standard Input (stdin) – user input from keyboard
       -   Standard Output (stdout) – regular command output
       -  Standard Error (stderr) – error messages
       - Understood how these are displayed and handled in the terminal

   - Practiced file redirection:
     -   > to overwrite output into a file
     -  >> to append output to an existing file
     -  < to use a file as input
     -   Created multiple files and redirected output using these operators
   - Learned and practiced:
     - cat — creating, viewing, and combining file contents
     -   cut — extracting fields using delimiters (-d, -f options)
    - sort — sorting file content alphabetically or numerically
    -      Started using piping (|) to chain multiple commands together
   - Practiced with AI-assisted problem sets on redirection and piping:
        - Asked ChatGPT to generate command-line problems
        - Solved scenarios involving multiple redirections and file manipulations
    - Started exploring command-line filtering:
      - Learned basics of grep (more practice planned for Day 3)
- Upcoming Topics
   - Deep dive into grep, awk, and sed
   - Chaining commands with advanced piping
   - Creating bash scripts for automation
   - Practicing real-world mini tasks using Linux CLI

## ✅ Day 3 – June 25, 2025
  Day 3 – June 25, 2025
### ✅ Day 3 – June 25, 2025

- 📄 **New Commands**
  - `tee` – split output to both file and screen
  - `xargs` – convert input into arguments

- 📁 **Advanced `ls` Options**
  - `-l` – long list
  - `-a` – show hidden files
  - `-F` – classify entries (e.g., `/`, `*`, etc.)
  - `-h` – human-readable sizes

- 📂 **Directory Navigation**
  - `pwd`, `cd`, `cd ..`, `cd ~`, `cd /desktop`

- 💡 **Aliases**
  - Created `.bash_aliases`
  - Added custom shortcuts like:
    ```bash
    alias docs='cd ~/Documents'
    alias desk='cd ~/Desktop'

## ✅ Day 4 – June 26, 2025
  Day 4 – June 26, 2025
### ✅ Day 4 – June 26, 2025

---

# 📂 Topics Covered

# 📄 File Extensions in Linux

- Linux doesn't depend on file extensions like `.txt`, `.jpg`, or `.mp4`.
- It reads the **file header (content)** to determine the file type.
- You can rename a `.txt` to `.mp4` and Linux will still treat it as a text file if the content matches.

---

# 📄 Creating Files & Folders

| Command | Description |
|--------|-------------|
| `touch file.txt` | Create a single file |
| `touch file1 file2 file3` | Create multiple files |
| `mkdir foldername` | Create one folder |
| `mkdir a b c` | Create multiple folders |
| `mkdir -p a/b/c` | Create nested folders recursively |

---

# 🧹 Deleting Files & Folders

| Command | Action |
|--------|--------|
| `rm file.txt` | Delete a file |
| `rm -r folder/` | Delete folder and all contents |
| `rmdir folder/` | Delete only empty folder |

> ⚠️ Warning: `rm -r` is powerful — use it carefully.

---

# 🌟 Wildcards

| Wildcard | Meaning | Example |
|---------|---------|---------|
| `*` | Matches any characters | `ls *.txt` → all `.txt` files |
| `?` | Matches one character | `ls f?.txt` → `f1.txt`, `fa.txt` |
| `[]` | Matches a range or list | `ls file[1-3].txt` → `file1.txt`, `file2.txt`, `file3.txt` |

---

# 🔧 Brace Expansion

| Command | Result |
|---------|--------|
| `touch file{1,2,3}.txt` | file1.txt file2.txt file3.txt |
| `mkdir week{1..3}` | week1 week2 week3 |
| `mkdir project{A,B}/day{1,2}` | projectA/day1 projectA/day2 projectB/day1 projectB/day2 |
## ✅ Day 5 – June 28, 2025
  Day 5 – June 28, 2025
### ✅ Day 5 – June 28, 2025

## 📄 Copying Files & Folders (cp command)

- cp source.txt destination.txt → Copies a file
- cp file1 file2 dir/ → Copies files into directory
- cp -r folder1/ folder2/ → Copies entire folder recursively
- cp -i → Interactive mode (asks before overwriting)
- cp -u → Copies only if source is newer than destination

✅ Used for transferring files/folders anywhere we want.

---

## 📁 Moving / Renaming Files & Folders (mv command)

- mv file1.txt dir/ → Moves file to directory
- mv oldname.txt newname.txt → Renames a file
- mv file1.txt file2.txt folder/ → Moves both into folder/

⚠️ Automatically overwrites unless used with -i (interactive)

---

## ✍️ Editing Files with nano

- nano filename.txt → Opens file in nano text editor
- Inside nano:
  - Ctrl + O → Save (Write Out)
  - Ctrl + X → Exit
  - Ctrl + K → Cut line
  - Ctrl + U → Paste line
  - Ctrl + W → Find
  - Ctrl + \ → Find and Replace

---

## 🔍 Spell Checker in nano

- aspell needs to be installed
- Edit nano config file:
  ```bash
  nano /etc/nanorc
  # 📅 Day 6 – Locate, Sudo, and Basic Find Command

---

## 📍 locate / plocate

- `locate filename` → Finds path using a prebuilt database
- `sudo updatedb` → Updates the plocate database
- `plocate` is the modern replacement for `mlocate` (used in newer Ubuntu)
- Database location: `/var/lib/plocate/plocate.db`

### 🔍 Database Info (approximation)
- `ls -lh /var/lib/plocate/plocate.db` → Shows database size
- `strings /var/lib/plocate/plocate.db | grep '^/' | wc -l` → Path entries in DB
- `strings /var/lib/plocate/plocate.db | grep '^/' | awk '{ sum += length } END { print sum }'` → Approx bytes in filenames

---

## 🔐 sudo

- `sudo` runs commands with elevated (root) privileges
- Needed for updating DB, installing software, editing system files

---

## 🔎 find

- `find /path -name "file.txt"` → Case-sensitive match
- `find /path -iname "file.txt"` → Case-insensitive
- `find /path -type f` → Find files only
- `find /path -type d` → Find directories only
- `find /path -maxdepth 2` → Limits how deep to search
- `find /path -mindepth 2` → Skips top-level results

---

✅ Summary:
- Learned to use `locate` with `plocate`
- Explored how to check and understand the database
- Practiced using `find` with filters and depth control
- Understood how `sudo` is needed for system-level changes

## ✅ Day 6 – June 29, 2025
  Day 6 – June 29, 2025
### ✅ Day 6 – June 29, 2025
– Locate, Sudo, and Basic Find Command

---

# 📍 locate / plocate

- `locate filename` → Finds path using a prebuilt database
- `sudo updatedb` → Updates the plocate database
- `plocate` is the modern replacement for `mlocate` (used in newer Ubuntu)
- Database location: `/var/lib/plocate/plocate.db`

# 🔍 Database Info (approximation)
- `ls -lh /var/lib/plocate/plocate.db` → Shows database size
- `strings /var/lib/plocate/plocate.db | grep '^/' | wc -l` → Path entries in DB
- `strings /var/lib/plocate/plocate.db | grep '^/' | awk '{ sum += length } END { print sum }'` → Approx bytes in filenames

---

# 🔐 sudo

- `sudo` runs commands with elevated (root) privileges
- Needed for updating DB, installing software, editing system files

---

# 🔎 find

- `find /path -name "file.txt"` → Case-sensitive match
- `find /path -iname "file.txt"` → Case-insensitive
- `find /path -type f` → Find files only
- `find /path -type d` → Find directories only
- `find /path -maxdepth 2` → Limits how deep to search
- `find /path -mindepth 2` → Skips top-level results

---

✅ Summary:
- Learned to use `locate` with `plocate`
- Explored how to check and understand the database
- Practiced using `find` with filters and depth control
- Understood how `sudo` is needed for system-level changes
  
## ✅ Day 7 – June 30, 2025
  Day 7 – June 30, 2025
### ✅ Day 7 – June 30, 2025

---

# 🔍 Advanced Find Commands

## 📊 wc (Word Count) Command
- `wc filename` → Shows lines, words, and characters count
- `wc -l` → Count lines only
- `wc -w` → Count words only
- `wc -c` → Count characters only

---

## 🔎 Finding Files by Size
- `find /path -size +100k` → Files larger than 100KB
- `find /path -size -5M` → Files smaller than 5MB
- `find /path -size +100k -size -5M` → Files between 100KB and 5MB

### Size Units:
- `c` → bytes
- `k` → kilobytes
- `M` → megabytes
- `G` → gigabytes

---

## 🔗 Boolean Operations with Find
- `find /path -name "*.txt" -o -name "*.pdf"` → Files ending with .txt OR .pdf
- `find /path -type f -a -size +1M` → Files that are regular files AND larger than 1MB
- `find /path ! -name "*.log"` → All files NOT ending with .log

### Boolean Operators:
- `-a` or `-and` → AND operation (default)
- `-o` or `-or` → OR operation
- `!` or `-not` → NOT operation

---

## ⚡ exec Command
- `find /path -name "*.txt" -exec cat {} \;` → Execute cat on each found file
- `find /path -type f -exec ls -l {} \;` → List details of each found file
- `find /path -name "*.log" -exec rm {} \;` → Delete all .log files

### exec Syntax:
- `{}` → Placeholder for the found file/directory
- `\;` → Required to terminate the exec command

---

## ⌨️ Terminal Control
- `Ctrl + C` → Cancel/interrupt current running command
- Useful when commands take too long or get stuck

---

✅ Summary:
- Learned `wc` command for counting lines, words, and characters
- Practiced finding files by size with various units
- Explored boolean operations (`-a`, `-o`, `!`) for complex searches
- Used `exec` command to perform actions on found files
- Understood the importance of `\;` terminator with exec
- Learned `Ctrl + C` for canceling stuck commands

## ✅ Day 8 – July 2, 2025
  Day 8 – July 2, 2025
### ✅ Day 8 – July 2, 2025
---

# 📄 File Content Commands

## 🐱 cat (Concatenate) Command
- `cat filename` → Display file contents
- `cat file1 file2` → Concatenate and display multiple files
- `cat file1 file2 > combined.txt` → Combine files into new file
- `cat >> file.txt` → Append text to file (Ctrl+D to finish)

### What is Concatenate?
- Combines multiple files or text streams into one continuous output
- Useful for merging configuration files, logs, or text documents

---

## 🔄 tac Command (Reverse of cat)
- `tac filename` → Display file contents in reverse line order
- `tac file1 file2` → Concatenate files but reverse the line order
- Shows last line first, first line last

---

## 📊 head Command (Top Lines)
- `head filename` → Shows first 10 lines by default
- `head -n 5 filename` → Shows first 5 lines
- `head -15 filename` → Shows first 15 lines
- `head file1 file2` → Shows first 10 lines of each file

---

## 📉 tail Command (Bottom Lines)
- `tail filename` → Shows last 10 lines by default
- `tail -n 5 filename` → Shows last 5 lines
- `tail -15 filename` → Shows last 15 lines
- `tail -f filename` → Follow file changes in real-time

---

## 📖 less Command (Pager)
- `less filename` → View file content page by page
- Navigation in less:
  - `Space` → Next page
  - `b` → Previous page
  - `q` → Quit
  - `/search` → Search forward
  - `?search` → Search backward
  - `G` → Go to end of file
  - `g` → Go to beginning of file

---

## 🔧 Combining Commands with Pipes
- `cat file.txt | head -20` → Show first 20 lines of file
- `cat file.txt | tail -15` → Show last 15 lines of file
- `head -50 file.txt | tail -10` → Show lines 41-50
- `cat file1 file2 | sort > sorted.txt` → Combine and sort files

---

## 📁 Output Redirection Practice
- `head -20 file.txt > top20.txt` → Save first 20 lines to new file
- `tail -10 file.txt >> bottom.txt` → Append last 10 lines to file
- `cat *.txt | less` → View all .txt files combined in less

---

✅ Summary:
- Learned `cat` for concatenating and displaying files
- Explored `tac` as the reverse of cat (reverse line order)
- Practiced `head` for viewing top lines with `-n` option
- Used `tail` for viewing bottom lines and real-time monitoring
- Mastered `less` for paginated file viewing with navigation
- Combined all commands with pipes and redirection
- Reviewed and practiced previously learned commands
  ## ✅ Day 9 – July 03, 2025
### ✅ Day 9 – July 03, 2025

---

# 🛠️ System Troubleshooting & Configuration

## 🐛 Issues Faced
- **Drag-and-drop** from Windows 11 to Ubuntu VM not working
- **Slow internet speeds** (~100 KBps despite 300 Mbps host connection)

## ✅ Solutions Applied

### 📦 VirtualBox Guest Additions
- Installed **VirtualBox Guest Additions** correctly
- Enables seamless integration between host and guest OS
- Required for proper drag-and-drop functionality

### 🖥️ Display Server Switch
- Switched from **Wayland** to **X11 session** in Ubuntu
- X11 provides better compatibility with VirtualBox features
- Changed at login screen for better VM performance

### 🌐 Network Configuration
- Changed VirtualBox **Network Adapter** settings:
  - Switched from `NAT` to `Bridged Adapter`
  - Used `Intel PRO/1000 MT Desktop` for best performance
  - Bridged adapter gives VM direct network access like physical machine

### 📁 File Transfer Setup
- Set up **Shared Folders** for stable file transfer
- More reliable than drag-and-drop for large files
- Provides persistent file sharing between host and guest

---

# 📄 sort Command Deep Dive

## 🔧 Sort Options Explored

| Option | Meaning | Example |
|--------|---------|---------|
| `-n` | Sort numerically | `sort -n numbers.txt` |
| `-r` | Reverse the result | `sort -r file.txt` |
| `-k` | Sort by a specific column | `sort -k 2 data.csv` |
| `-u` | Show unique lines only | `sort -u duplicates.txt` |
| `-M` | Sort by month names | `sort -M months.txt` |
| `-h` | Human-readable sizes (e.g., 1K, 5M) | `sort -h sizes.txt` |

## 🎯 Practical Examples
- `sort -nr file.txt` → Sort numerically in reverse order
- `sort -k 3 -n data.txt` → Sort by 3rd column numerically
- `sort -u -k 1,1 file.txt` → Unique values based on first column only
- `ls -lh | sort -k 5 -h` → Sort files by size (human-readable)

---

## 🔗 Combining Sort with Other Commands
- `cat file.txt | sort -u > unique.txt` → Remove duplicates and save
- `sort -n numbers.txt | head -5` → Show 5 smallest numbers
- `sort -nr scores.txt | tail -3` → Show 3 lowest scores

---

✅ Summary:
- Solved VirtualBox VM performance and connectivity issues
- Learned proper Guest Additions installation
- Configured optimal network settings for VM
- Mastered advanced `sort` command options
- Practiced combining sort with pipes and redirection
- Improved overall VM experience for better Linux learning

### ✅ Day 10 – July 05, 2025
##✅ Day 10 – July 05, 2025
#🔍 GREP – Pattern Searching in Files
   -📄 Command Overview

  -grep is used to search for patterns in files

  - Can be used with other commands via piping (|)

🛠️ Options Explored

    -i → case-insensitive search

    -c → count number of matching lines

    -v → show lines that do not match the pattern

🧪 Practical Examples

    ls -l | grep "Jan" → shows lines with 'Jan'

    ls -l | grep -v "txt" → excludes lines with 'txt'

    ls -l | grep -i "PDF" → case-insensitive match for 'pdf'

    ls -l | grep -c "log" → count lines containing 'log'

🔗 Integration with Other Commands

    ls -l | grep -i "point" → filters results for "point"

    Commonly used with ls, man, and piping

📦 Tarball Creation & Extraction
📦 What is a Tarball?

    A tarball is like a bag that contains multiple files and directories

    Used for archiving files into a single .tar file

🛠️ Creating a Tar Archive

tar -cvf archive.tar file1 file2

    -c → create archive

    -v → verbose output

    -f → specify file name

📄 Listing Contents of a Tar Archive

tar -tf archive.tar

    -t → test/list files in the archive

📤 Extracting a Tar Archive

tar -xvf archive.tar

    -x → extract files from the archive

🗜️ Compression with gzip & bzip2
🛠️ Compress While Creating Archive

    Gzip compression:

tar -cvfz archive.tar.gz file1 file2

    -z → compress using gzip

Bzip2 compression:

    tar -cvfj archive.tar.bz2 file1 file2

        -j → compress using bzip2

📤 Extracting Compressed Archives

    Gzip:

tar -xvfz archive.tar.gz

Bzip2:

    tar -xvfj archive.tar.bz2

🔬 gzip vs bzip2 – Comparison
Tool	Speed	Compression
gzip	Faster	Less efficient
bzip2	Slower	More efficient
🧱 gzip & bzip2 (Standalone Use)
🛠️ Compressing Files

gzip filename
bzip2 filename

📤 Decompressing Files

gunzip filename.gz
bunzip2 filename.bz2

📁 Working with .zip Files
🛠️ Creating Zip Archives

zip ourthing.zip file1.txt file2.txt

📤 Unzipping

unzip ourthing.zip

    Useful for compatibility with Windows and cross-platform systems

✅ Summary:

    Learned and practiced grep with practical filters and piping

    Understood tar, gzip, bzip2, and zip usage

    Practiced archiving and compression via CLI

    Mastered differences between compression methods

    Improved Linux file handling and system efficiency
    ``` This repository will be updated daily as I continue progressing toward cloud/system admin roles. 🌱💻
