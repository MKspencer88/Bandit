# Bandit A Security Learning Journey

# Overview

When I was researching what I can do to gain cybersecurity experience without having a job, overthewire.org was the one of the first thing suggested. Bandit is a Linux-based wargame designed to teach foundational security skills through hands-on puzzles. This project documents how each level shaped my understanding of:

- Command-line navigation
- Permissions
- Processes
- Networking
- Problem-solving

# Tools Used

- Linux
- SSH
- bash
- ls, cat, file, find, du
- grep, sort uniq strings

# Level 0 --> Level 1 

The password for the next level is in a file called **readme** located in the home directory.

# What I did

- First I logged into the Bandit server by using **SSH** explored the home directory with **ls**. This revealed a files named **readme**, which I opened using **cat** to view the password for the next level

<img width="823" height="46" alt="Screenshot 2026-02-27 151359" src="https://github.com/user-attachments/assets/421d91ff-5631-4424-9af4-233e5a2ba367" />

<img width="496" height="202" alt="image" src="https://github.com/user-attachments/assets/427cf608-5b24-484e-ba50-e2a87833c727" />

 <img width="906" height="169" alt="Screenshot 2026-02-27 151742" src="https://github.com/user-attachments/assets/f34b202a-0bd1-4f85-a34b-70c7bd4d9151" />

# Commands Used

- **SSH:** Established a secure remote connection to the Bandit server
- **ls:** Listed files within the current directory
- **cat readme:** Displayed contents of *readme* 

# Key Insight

This level demonstrates that cybersecurity work begins with systematic exploration and that before anything, you need to understand the environment you're working in

# Real-World Relevance

Connecting to remote systems with SSH is a core skill in cybersecurity and IT. Almost every real environment uses SSH for server access, log review, and incident investigation.

# What I Learned

Working through this level reminded me tha even the simpliest of tasks the cybersecurity start with understanding the environment. Logging in, listing files, and reading a basic text file may seem small, but they are the foundation of everything that comes later. This level helped me slow down, get comfortable navigating a remote Linux system, and build confidence with SSH and basic shell commands before moving into more complex challenges.

# Level 1 --> Level 2

The password in store in a file called **-**. 

# What I did

I listed files in the home directory using **ls**, the command reavealed a file called **'-'**. I first used the command **cat -** but the filename **-** caused an issue becuase many Linux commmand interpret **-** as an option flag and not a file name. As a result, **cat -** waited for input instead of displaying the file contents. After some research I found that the command **cat ./-** was the one that worked, becuase this **./-** is the direct path to the file. 

<img width="909" height="271" alt="image" src="https://github.com/user-attachments/assets/b49b0964-5dfb-4761-8585-3256fa8dba13" />

<img width="320" height="156" alt="image" src="https://github.com/user-attachments/assets/a624ad60-3cd5-48c6-8b97-d019d4a630b1" />

<img width="418" height="100" alt="image" src="https://github.com/user-attachments/assets/2f6b735d-47d3-43b9-954d-7109e1c6bb57" />

# Commands Used

- **ssh** -- Established a secure a remote connection to the Bandit server
- **ls** -- Lists the files in the Current directory
- **cat ./-** -- this is the direct path to the file

# Key Insights

- Linux treats anything witha **-** as an option, not a filename.
- You can forve the shell to treat a werid filename literally by using a path prefix
- Understanding how the shell parses arguements is essential for handling edge cases.
- There multiple safe wasy to reference trickey filenames.

# Real-World Relevance

- Malware and attackers often use "weird" filenames to hide in plain sight.
- System administrators regularly encounter misnamed or auto-generated files.
- Understanding argument parsing prevents accidental command misuse.

# What I Learned

This level taught me how Linux interprets command-line arguments and how to safely handle files with misleading or special names. It reinforced the importance of understanding how the shell parses options versus literal filenames. A small detail that has big implications in real security and system administration work.

# Level 2 --> Level 3

The password is stored in a file called --spaces in this filename--.

# What I did

- I used **ssh** to establish a secure connection.
<img width="774" height="617" alt="image" src="https://github.com/user-attachments/assets/8d93a884-d5c1-43ed-bc3b-1d0ebf2ac66d" />

- The **ls** command listed all the files in the directory. The file that was revealed was called **--spaces in this filename--**.
<img width="253" height="77" alt="image" src="https://github.com/user-attachments/assets/1b089a0a-ac1f-4af4-aead-c015738a8dd0" />

- The command **cat --space in this filename--** doesn't work because **'--"** looks like an option not a file kinda like the previous level. So the command **cat --spaces in this filename--** is being treated as four seperate arguments. The correct command **cat ./--spaces\ in\ this\ filename--**. **./** tells the shell that this a file and not an option. \ keeps the spaces together so the shell sees one filename instead of several. This command works because **./** forces the shell to treat the name as a real files instead of an option, and escaping the spaces keeps the entire filename together as one argument.

<img width="448" height="51" alt="image" src="https://github.com/user-attachments/assets/dc947651-02d6-4e6f-9d8f-47ec768a7cce" />

<img width="507" height="60" alt="image" src="https://github.com/user-attachments/assets/3f625f06-3ca2-4fbc-ad6d-ed1902a88e08" />

# Commands Used 

- **ssh**
- **ls**
- **cat ./--spaces\ in\ this\ filename--**

# Key Insights

- Filenames with spaces must be treated as a single argument.
- Filenames starting with dashes are interpreted as options unless you force the shell to treat them literally.
- Combining both techniques lets you safely access tricky filenames.

# Real-World Relevance

- Attakers and malware often use confusing filenames to hide.
- System logs and automated tools sometimes generate odd filenames.
- Correct arguments handling prevents accidental misuse of commands.

# What I Learned

This level taught me how important it is to understand how the shell interprets filenames. I learned how to handle files that contain spaces or start with dashes, and how to to use qouting, escaping, or path prefixes to avoid mistakes. It made me more confident working with unusual filenames and more aware of how easily the shall can misinterpret arguments if not precise.

# Level 3 --> Level 4

The password is stored in a hidden file in the **inhere** directory. 

# What I Did

- I used **ssh** to gain access to the Bandit server
<img width="678" height="581" alt="image" src="https://github.com/user-attachments/assets/b264f590-9d56-4d28-8db2-e654d117a95f" />

- I searched the home **(~)** directory and it listed another directory called **inhere**.
<img width="214" height="70" alt="image" src="https://github.com/user-attachments/assets/878ce6a9-9b49-45f7-83fd-8b553a5eaee3" />

- I navigated into the **inhere** directory with the command **cd inhere**. Once I was in the **inhere** directory I listed the directory again and nothing happened. When I remembered in the objective the file is **hidden**.
<img width="280" height="73" alt="image" src="https://github.com/user-attachments/assets/dd779f12-39d7-4566-8397-52afe3f3df01" />

- The command **ls -la** is what is going to list ALL the files in the directory. The **-a** is the option to show all the files. The output reveals a file called ...Hiding-From-You. The reason why this is hidden is because it starts with a dot.
<img width="608" height="119" alt="image" src="https://github.com/user-attachments/assets/e08284fd-f4b2-4174-8453-b7d8b3fc348e" />

- I open the file using **cat ...Hiding-From-You** and it gives me the password to the next level. 
<img width="467" height="71" alt="image" src="https://github.com/user-attachments/assets/9ec5cf3a-8a68-4974-ae9c-d66d03231cbd" />

# Key Insights

- Linux hides any file or directory that begins with a dot.
- ** ls -la** reveals everything, including hidden files and directories. The **-a** flat is essential when exploring unfamiliar environments because it shows what would otherwise be invisible.
- Never assume a directory is emptpy just because ls shows nothing.

# Real-World Relevence

- Hidden files are everywhere in real systems.
- Malware frequently hides in dot-folders. Attckers use hidden directories to avoid detection.
- Troubleshooting often depends on checking hidden fuiles. Many issues live in places you wouldn't see without ls -la.

# What I learned

I learned that first view of a directory doesn't always tell the full story. When ls showed nothing, it didn't mean the directory was empty. Using **ls -la** helped me uncover hidden files and made me more aware of how Linux organizes important system data. This level reinforced the habit of always checking for hidden items when exploring or troubleshooting a system.

# Level 4 --> Level 5

The password is stored in the only human-readable file in the **inhere** directory. 

# What I Did

- Gained access to bandit4 through ssh, listed the directory and found the **inhere** directory. I moved into that directory using **cd**. 
<img width="636" height="583" alt="image" src="https://github.com/user-attachments/assets/b3d1a034-8b09-4594-86f6-effa85f1bd62" />

- I listed the **inhere** directory and a bunch of files were listed. My goal is to find the only human-readable file in this directory.
<img width="835" height="125" alt="image" src="https://github.com/user-attachments/assets/1af2eafd-833e-42a1-b034-4208677b7c42" />

- The **file** command looks inisde of a file and identifies the content. So when I run the commmand **file ./*** it shows me what content is in each file. ASCII text is human-readable data. The command cat ./-file07 is going to open the ASCII text file and reveal the password. 
<img width="402" height="216" alt="image" src="https://github.com/user-attachments/assets/24e6a450-6af6-473a-96a3-024f9c9e3153" />
<img width="362" height="47" alt="image" src="https://github.com/user-attachments/assets/08f9f57d-3b8d-48a2-8e2c-387d844bda50" />

# Key Inisights

- The **file** command indentifies what type of data a file contains, regardless of its name or extenstion. This make it easy to spot which files are readable and which are binary, empty, or junk.
- When a directory contains many unknown files, guessing or opening them one by one is inefficient. Using **file ./*** OR **file inhere/*** (this works if you are not in the inhere directory.)














































  

