7 oct 2026

GOOD:
-> Wake up at 7 am [water->tea->fresh]
-> I iron my clothes
-> I clean my entire Room
-> I read the book "#invest in you" in 15 to 20 minutes
-> I controlled myself for a while


BAD
-> I lost control of myself in the last and then RELEASED.[But No Screen in this activity]
-> Bath at 3:30 pm

SKILLS: [Improvements]
-> 15 min book reading ✅
->


Learning: 
https://tryhackme.com/room/introtonetworking?vccr=1

Kali Linux Command:




# Linux Terminal Commands Master Reference Cheat Sheet

This document contains a structured reference guide for the 10 core Linux filesystem commands. Each command is grouped with common workflows, flags, and safety options using clear code snippets and inline comments.

---

## 1. ls - LIST DIRECTORY CONTENTS

```bash
# List files and folders in the current directory (standard layout)
ls

# Long listing format: Shows permissions, file size, owner, and date modified
ls -l

# Show all files, including hidden files (files starting with a dot like .bashrc)
ls -a

# Human-readable format: Shows file sizes in easy-to-read KB, MB, or GB
ls -lh

# Sort the list by modification time (newest files show up first)
ls -t
```

---

## 2. cd - CHANGE DIRECTORY

```bash
# Move forward into a specific folder
cd Documents/

# Move one step backward to the parent folder
cd ..

# Go straight to your user's personal home directory
cd ~

# Go back to the previous folder you were just working in
cd -
```

---

## 3. pwd - PRINT WORKING DIRECTORY

```bash
# Print the complete absolute path of where you are right now
pwd

# Print the physical path on disk, ignoring symbolic shortcuts/links
pwd -P
```

---

## 4. mkdir - CREATE A NEW DIRECTORY

```bash
# Create a single new empty folder
mkdir new_folder

# Create nested folders all at once (creates parent folders automatically)
mkdir -p project/src/assets

# Verbose mode: Prints a text confirmation message after creating the folder
mkdir -v finished_work
```

---

## 5. rmdir - REMOVE EMPTY DIRECTORIES

```bash
# Delete an empty folder (fails if there are any files inside it)
rmdir empty_folder

# Delete nested empty folders safely from the inside out
rmdir -p project/src/assets
```

---

## 6. rm - REMOVE FILES OR DIRECTORIES

```bash
# Permanently delete a single file
rm document.txt

# Delete multiple specific files at the same time
rm file1.txt file2.txt file3.txt

# ==========================================
# REMOVING DIRECTORIES (FOLDERS)
# ==========================================

# Recursive mode: Delete an entire folder and every single file hidden inside it
rm -r old_project/

# ==========================================
# USEFUL FLAGS & SAFETY OPTIONS
# ==========================================

# Interactive mode: Ask for your permission before deleting a file
rm -i safe_file.txt

# Force mode: Delete files forcefully, skip confirmation, and ignore warnings
rm -rf temporary_cache/
```

---

## 7. cp - COPY FILES AND DIRECTORIES

```bash
# Copy a file to another file (creates a duplicate in the same folder)
cp file1.txt file2.txt

# Copy a file into another directory (keeps the same filename)
cp file1.txt backup/

# Copy and rename a file into another directory
cp file1.txt backup/old_file.txt

# Copy multiple specific files into a directory
cp a.txt b.txt c.txt backup/

# Copy all files ending with .txt into a directory
cp *.txt backup/

# ==========================================
# COPYING DIRECTORIES (FOLDERS)
# ==========================================

# Copy a folder and all its contents recursively
cp -r folder1/ folder2/

# ==========================================
# USEFUL FLAGS & SAFETY OPTIONS
# ==========================================

# Interactive mode: Ask before overwriting an existing file
cp -i file1.txt file2.txt

# No-clobber: Do NOT overwrite a file if it already exists
cp -n file1.txt file2.txt

# Preserve: Keep the original file permissions, timestamps, and ownership
cp -p file1.txt backup/

# Verbose: Show a live text description of what is being copied
cp -v file1.txt backup/
```

---

## 8. mv - MOVE OR RENAME FILES

```bash
# Rename a file or folder in its current location
mv old_name.txt new_name.txt

# Move a file from the current folder into another directory
mv file.txt documents/

# ==========================================
# USEFUL FLAGS & SAFETY OPTIONS
# ==========================================

# Interactive mode: Ask before overwriting a duplicate file at the destination
mv -i file.txt documents/

# No-clobber: Automatically skip moving if the file already exists at the destination
mv -n file.txt documents/

# Verbose mode: Show a live description of the file as it moves
mv -v file.txt documents/
```

---

## 9. touch - CREATE AN EMPTY FILE

```bash
# Create a brand new, empty file instantly
touch logs.txt

# Create multiple empty files at the same time
touch step1.txt step2.txt step3.txt

# ==========================================
# TIMESTAMPS OPTIONS
# ==========================================

# Update the modification timestamp of an existing file to right now
touch -m existing_file.txt

# Update the access timestamp of an existing file to right now
touch -a existing_file.txt
```

---

## 10. find - SEARCH FOR FILES

```bash
# Search for a file by exact name starting inside the current directory (.)
find . -name "invoice.pdf"

# Case-insensitive search (matches invoice.pdf, INVOICE.PDF, Invoice.Pdf)
find . -iname "invoice.pdf"

# Search specifically for a directory (folder) by name instead of a file
find /home -type d -name "workspace"

# Search for all files that are larger than 100 Megabytes
find . -type f -size +100M

# Search for files that were modified within the last 7 days
find . -type f -mtime -7
```
