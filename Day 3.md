# Daily Progress & Technical Reference Log
**Date:** 7 October 2026

---

## 1. Daily Review & Reflection

### GOOD:
* **Morning Routine:** Woke up at 7:00 AM (hydration $\rightarrow$ tea $\rightarrow$ fresh).
* **Chore Management:** Ironed clothes and cleaned the entire room thoroughly.
* **Habit Building:** Read the book *"#invest in you"* for 15–20 minutes.
* **Discipline:** Successfully exercised self-control for a major portion of the day.

### BAD:
* **Setback:** Lost control toward the end and then RELEASED (Note: Maintained zero screen use during this activity).
* **Schedule Shift:** Delayed bath until 3:30 PM.

### SKILLS & IMPROVEMENTS:
* 15-minute daily book reading: **COMPLETED ✅**
* 10 Basic Linux command
* OSI Model [La]

### LEARNING RESOURCE:
* [TryHackMe - Intro to Networking Room](https://tryhackme.com/room/introtonetworking?vccr=1)

---

# OSI Model & Network Fundamentals - Study Notes

## 1. Overview of the OSI Model
* **Purpose:** A standardized theoretical model used to explain computer networking concepts.
* **Real-world Counterpart:** The more compact **TCP/IP model** is used in practice, but the OSI model provides an easier conceptual foundation.
* **Mnemonic for Layers (7 to 1):** *Anxious Pale Shakespeare Treated Nervous Drunks Patiently*

---

## 2. The 7 Layers of the OSI Model

| Layer | Name | Key Functions & Protocols |
| :--- | :--- | :--- |
| **Layer 7** | Application | Provides networking options to programs/applications (e.g., FTP, HTTP). |
| **Layer 6** | Presentation | Translates data into a standardized format; handles **encryption, compression, and transformations**. |
| **Layer 5** | Session | Establishes, maintains, and synchronizes unique communication sessions between hosts (allows multi-tab browsing). |
| **Layer 4** | Transport | Chooses protocols (**TCP** for reliable/connection-based; **UDP** for fast/unreliable streaming) and divides data into **segments** (TCP) or **datagrams** (UDP). |
| **Layer 3** | Network | Handles **logical addressing (IP addresses, IPv4)** and routing across networks. |
| **Layer 2** | Data Link | Uses physical **MAC addresses** (burned into the NIC) for node-to-node delivery, formats data for transmission, and performs **error checking** for corruption. |
| **Layer 1** | Physical | Hardware layer; converts binary data into electrical/physical signals for transmission across physical media. |

---

## 3. TryHackMe Questions & Answer Key

1. **Which layer would choose to send data over TCP or UDP?**
   * **Answer:** `4` (Transport Layer)

2. **Which layer checks received information to make sure that it hasn't been corrupted?**
   * **Answer:** `2` (Data Link Layer)

3. **In which layer would data be formatted in preparation for transmission?**
   * **Answer:** `2` (Data Link Layer)

4. **Which layer transmits and receives data?**
   * **Answer:** `1` (Physical Layer)

5. **Which layer encrypts, compresses, or otherwise transforms the initial data to give it a standardised format?**
   * **Answer:** `6` (Presentation Layer)

6. **Which layer tracks communications between the host and receiving computers?**
   * **Answer:** `5` (Session Layer)

7. **Which layer accepts communication requests from applications?**
   * **Answer:** `7` (Application Layer)

8. **Which layer handles logical addressing?**
   * **Answer:** `3` (Network Layer)

9. **When sending data over TCP, what would you call the "bite-sized" pieces of data?**
   * **Answer:** Segments

10. **[Research] Which layer would the FTP protocol communicate with?**
    * **Answer:** `7` (Application Layer)

11. **Which transport layer protocol would be best suited to transmit a live video?**
    * **Answer:** UDP
---

## 3. Kali Linux Command Reference

# Linux Terminal Commands Master Reference Cheat Sheet

This document contains a structured reference guide for the 10 core Linux filesystem commands. Each command is grouped with common workflows, flags, and safety options using clear code snippets and inline comments.

---

## Commands ls,cd,pwd,mkdir,rmdir,cp,mv,touch,find,rm

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

# Move forward into a specific folder
cd Documents/

# Move one step backward to the parent folder
cd ..

# Go straight to your user's personal home directory
cd ~

# Go back to the previous folder you were just working in
cd -

# Print the complete absolute path of where you are right now
pwd

# Print the physical path on disk, ignoring symbolic shortcuts/links
pwd -P

# Create a single new empty folder
mkdir new_folder

# Create nested folders all at once (creates parent folders automatically)
mkdir -p project/src/assets

# Verbose mode: Prints a text confirmation message after creating the folder
mkdir -v finished_work

# Delete an empty folder (fails if there are any files inside it)
rmdir empty_folder

# Delete nested empty folders safely from the inside out
rmdir -p project/src/assets

# Permanently delete a single file
rm document.txt

# Delete multiple specific files at the same time
rm file1.txt file2.txt file3.txt

# ============================================
# REMOVING DIRECTORIES (FOLDERS)
# ============================================

# Recursive mode: Delete an entire folder and every single file hidden inside it
rm -r old_project/

# ============================================
# USEFUL FLAGS & SAFETY OPTIONS
# ============================================

# Interactive mode: Ask for your permission before deleting a file
rm -i safe_file.txt

# Force mode: Delete files forcefully, skip confirmation, and ignore warnings
rm -rf temporary_cache/

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

# ============================================
# COPYING DIRECTORIES (FOLDERS)
# ============================================

# Copy a folder and all its contents recursively
cp -r folder1/ folder2/

# ============================================
# USEFUL FLAGS & SAFETY OPTIONS
# ============================================

# Interactive mode: Ask before overwriting an existing file
cp -i file1.txt file2.txt

# No-clobber: Do NOT overwrite a file if it already exists
cp -n file1.txt file2.txt

# Preserve: Keep the original file permissions, timestamps, and ownership
cp -p file1.txt backup/

# Verbose: Show a live text description of what is being copied
cp -v file1.txt backup/

# Rename a file or folder in its current location
mv old_name.txt new_name.txt

# Move a file from the current folder into another directory
mv file.txt documents/

# ============================================
# USEFUL FLAGS & SAFETY OPTIONS
# ============================================

# Interactive mode: Ask before overwriting a duplicate file at the destination
mv -i file.txt documents/

# No-clobber: Automatically skip moving if the file already exists at the destination
mv -n file.txt documents/

# Verbose mode: Show a live description of the file as it moves
mv -v file.txt documents/

# Create a brand new, empty file instantly
touch logs.txt

# Create multiple empty files at the same time
touch step1.txt step2.txt step3.txt

# ============================================
# TIMESTAMPS OPTIONS
# ============================================

# Update the modification timestamp of an existing file to right now
touch -m existing_file.txt

# Update the access timestamp of an existing file to right now
touch -a existing_file.txt

# Create a brand new, empty file instantly
touch logs.txt

# Create multiple empty files at the same time
touch step1.txt step2.txt step3.txt

# ============================================
# TIMESTAMPS OPTIONS
# ============================================

# Update the modification timestamp of an existing file to right now
touch -m existing_file.txt

# Update the access timestamp of an existing file to right now
touch -a existing_file.txt

# Search for a file by exact name starting inside the current directory (.)
find . -name "invoice.pdf"

# Case-insensitive search (matches invoice.pdf, INVOICE.PDF, Invoice.Pdf)
find . -iname "invoice.pdf"

# Search specifically for a directory (folder) by name instead of a file
find /home -type d -name "workspace"

# Find all files that are larger than 100 Megabytes
find . -type f -size +100M

# Search for files that were modified within the last 7 days
find . -type f -mtime -7
