# Linux Fundamentals for Cybersecurity

## Overview

This project documents my hands-on learning and practice of Linux fundamentals as part of my cybersecurity training.

I completed practical labs using Kali Linux to build foundational skills needed for entry-level cybersecurity roles. The labs focused on Linux navigation, file management, permissions, users, processes, services, networking, logs, and file investigation.

## Environment

- Operating System: Kali Linux
- Platform: VirtualBox
- Command Line: Linux Terminal

## Skills and Labs Completed

### Lab 1: Linux Navigation and Files

I practiced navigating the Linux file system and working with files and directories.

Commands practiced:

`pwd`, `ls`, `cd`, `mkdir`, `touch`

### Lab 2: File Management

I practiced creating, copying, moving, renaming, and deleting files and directories.

Commands practiced:

`cp`, `mv`, `rm`, `rmdir`

### Lab 3: Finding and Inspecting Files

I learned how to locate files and inspect their contents.

Commands practiced:

`find`, `locate`, `which`, `cat`, `less`, `head`, `tail`

### Lab 4: Permissions and Ownership

I learned how Linux file permissions and ownership work.

Commands practiced:

`ls -l`, `chmod`, `chown`

Permission basics:

- `r` = read
- `w` = write
- `x` = execute

### Lab 5: Users, Groups, and Privileges

I practiced identifying users, groups, and elevated privileges.

Commands practiced:

`whoami`, `id`, `groups`, `sudo`, `sudo -l`

### Lab 6: Processes and Services

I learned how to identify and investigate running processes and services.

Commands practiced:

`ps`, `top`, `systemctl`

### Lab 7: Networking Basics

I learned how to inspect network interfaces, IP addresses, routes, connectivity, and listening ports.

Commands practiced:

`ip addr`, `ip route`, `ping`, `hostname`, `hostnamectl`, `ss -tuln`, `ss -tulnp`

### Lab 8: Linux Logs and Investigation

I learned how to locate and investigate Linux logs.

Key location:

`/var/log`

Commands practiced:

`journalctl`, `grep`, `head`, `tail`, `less`

### Lab 9: File Investigation and Hashing

I learned how to investigate files using file type, metadata, permissions, and SHA-256 hashes.

Commands practiced:

`file`, `stat`, `sha256sum`, `grep`, `find`

I learned that a file extension alone does not always identify the actual type of a file.

### Lab 10: Linux Security Investigation

I completed a basic Linux security review using the skills developed throughout the previous labs.

The investigation included:

- Identifying the current user
- Reviewing privileges
- Checking running processes
- Reviewing active services
- Checking listening ports
- Reviewing recent system events
- Searching for failed events
- Investigating files
- Reviewing file permissions
- Creating SHA-256 hashes
- Documenting findings

## Investigation Workflow

```text
IDENTITY
↓
PRIVILEGES
↓
PROCESSES
↓
SERVICES
↓
NETWORK
↓
LOGS
↓
FILES
↓
FINDINGS
