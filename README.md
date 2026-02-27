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

# Level 0

# Objective

Log into the Bandit server using ssh and navigate the environment to find the password.

# What I did

- First I logged into bandit0 using SSH.

<img width="823" height="46" alt="Screenshot 2026-02-27 151359" src="https://github.com/user-attachments/assets/421d91ff-5631-4424-9af4-233e5a2ba367" />

Once I logged in I used **ls* to check inside the current directory

<img width="496" height="202" alt="image" src="https://github.com/user-attachments/assets/427cf608-5b24-484e-ba50-e2a87833c727" />

Revealing the file readme. 

- I used **cat** to view it's contents

<img width="906" height="169" alt="Screenshot 2026-02-27 151742" src="https://github.com/user-attachments/assets/f34b202a-0bd1-4f85-a34b-70c7bd4d9151" />

# Commands Used

- The basics of navigating a Linux environment
- **SSH:** Established a secure remote connection to the Bandit server
- **ls:** Listed files within the current directory
- **cat readme:** Displayed contents of *readme* 

# Key Insight

Level 0 demonstrates that cybersecurity work begins with systematic explortaion and that before exploiting the system you need to first understand how it works.  


# Level 0 --> Level 1

# What I Did

- The first thing I did was **SSH**'d my way into bandit1

<img width="909" height="271" alt="image" src="https://github.com/user-attachments/assets/b49b0964-5dfb-4761-8585-3256fa8dba13" />

Once in I used **ls** to list files in the directory. A file with the name **-** is in there. 

Unfortunately you can't run the command cat - I ran it and it just goes to the next line with no output

<img width="320" height="156" alt="image" src="https://github.com/user-attachments/assets/a624ad60-3cd5-48c6-8b97-d019d4a630b1" />

The command **cat ./-** is the correct one to view the contents of the file

<img width="418" height="100" alt="image" src="https://github.com/user-attachments/assets/2f6b735d-47d3-43b9-954d-7109e1c6bb57" />

# Why It Matter


























  

