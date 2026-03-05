# Day 1 - Linux File System Practice

## Problem Statement

Perform the following file and directory operations using the Linux command line:

1. Create a directory named `btech_project`.
2. Change into the `btech_project` directory.
3. Create a file named `data.txt` and insert the text:
   > **Final Year B.Tech Project Data**
4. Display the contents of `data.txt`.
5. Create another directory named `backup` inside `btech_project`.
6. Copy `data.txt` into the `backup` folder.
7. Rename `data.txt` to `project_data.txt`.
8. Delete the copied file from the `backup` directory.
9. Remove the empty `backup` directory.

---

## Solution

```bash
# 1. Create a directory named btech_project
mkdir btech_project

# 2. Change into the btech_project directory
cd btech_project

# 3. Create a file named data.txt and insert the text
echo "Final Year B.Tech Project Data" > data.txt

# 4. Display the contents of data.txt
cat data.txt

# 5. Create another directory named backup inside btech_project
mkdir backup

# 6. Copy data.txt into the backup folder
cp data.txt backup/

# 7. Rename data.txt to project_data.txt
mv data.txt project_data.txt

# 8. Delete the copied file from the backup directory
rm backup/data.txt

# 9. Remove the empty backup directory
rmdir backup
```