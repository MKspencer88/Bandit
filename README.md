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

# What I did

First I logged into the Bandit server by using **SSH** and explored the home directory with **ls**. This revealed a files named **readme**, which I opened using **cat** to view the password for the next level

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

This level taughe me how Linux interprets command-line arguments and how to safely handle files with misleading or special names. It reinforced the importance of understanding how the shall parses options versus literal filenames. A small detial that has big implications in real security and system administration work.

Level 2 --> Level 3

# What I did

I used **ssh** to establish a secure connection. The **ls** command listed all the files in the directory. The file that was revealed was called **--spaces in this filename--**. The command **cat --space in this filename--** doesn't work because **'--"** looks like an option not a file kinda like the previous level. So the command **cat --spaces in this filename--** is being treated as four seperate arguments. The correct command **cat ./--spaces\ in\ this\ filename--**. **./** tells the shell that this a file and not an option. \ keeps the spaces together so the shell sees one filename instead of several. This command works because **./** forces the shell to treat the name as a real files instead of an option, and escaping the spaces keeps the entire filename together as one argument.

<img width="774" height="617" alt="image" src="https://github.com/user-attachments/assets/8d93a884-d5c1-43ed-bc3b-1d0ebf2ac66d" />

<img width="774" height="617" alt="image" src="https://github.com/user-attachments/assets/0bbd47ae-1703-4b17-80be-9260de81385f" />

<img width="253" height="77" alt="image" src="https://github.com/user-attachments/assets/1b089a0a-ac1f-4af4-aead-c015738a8dd0" />

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

This level taught me how important it is to understand how the shell interprets filenames. I learned how to handle files that contain spaces or start with dashes, and how to to use qouting, es







































  

