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

    ``` This repository will be updated daily as I continue progressing toward cloud/system admin roles. 🌱💻
