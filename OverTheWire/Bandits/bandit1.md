Level 1 – Find the Password
Objective

The password for the next level is stored in a file called readme in the home directory.

Step 1: List the files
ls

Output:
readme


Step 2: Read the file
cat readme

This displays the password for bandit1.

Step 3: Log into Level 1

Use the password obtained from readme:

ssh bandit1@bandit.labs.overthewire.org -p 2220


What I Learned
ls lists files and directories.
cat displays the contents of a file.
The password found in one level is used to access the next level.
SSH is used to connect to each Bandit level.