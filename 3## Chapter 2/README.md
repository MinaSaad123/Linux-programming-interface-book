# Chapter 2 FUNDAMENTAL CONCEPTS
This

## Table of contents

- **The Core Operating System: The Kernel**
     - Tasks performed by the kernel
     - Kernel mode and user mode
     - Process versus kernel views of the system
- **The Shell**
- **Users and Groups**
     - Users
     - Groups
     - Superuser
- **Single Directory Hierarchy, Directories, Links, and Files**
     - File types
     - Directories and links
     - Symbolic links
     - Filenames
     - Pathnames
     - Current working directory
     - File ownership and permissions
- **File I/O Model**
     - File descriptors
     - The stdio library
- **Programs**
    - Filters
    - Command-line arguments
- **Processes**
    - Process memory layout
    - Process creation and program execution
    - Process ID and parent process ID
    - Process termination and termination status
    - Process user and group identifiers (credentials)
    - Capabilities
    - The init process
    - Daemon processes
    - Environment list
    - Resource limits
- **Memory Mappings**
- **Static and Shared Libraries**
    - Static libraries
    - Shared libraries
- **Interprocess Communication and Synchronization**
- **Signals**
- **Threads**
- **Sessions, Controlling Terminals, and Controlling Processes**
- **Pseudoterminals**
- **Date and Time**
- **Client-Server Architecture**
- **Realtime**
- **The /proc File System**

## **The Core Operating System: The Kernel**

The term **operating system** is commonly used with two different meanings:
- To denote the entire package consisting of the central software managing a
computer’s resources and **all of the accompanying standard software tools,
such as command-line interpreters, graphical user interfaces, file utilities, and
editors.**
- **More narrowly**, to refer to the central software that manages and allocates computer resources.

The term kernel is often used as a synonym **for the second meaning**, and it is with
this meaning of the term operating system.

**<u>Take care:</u>** presence of a kernel greatly **simplifies the writing and use of other programs, and increases the power and flexibility available to programmers**.

**->** The Linux kernel executable typically resides at the pathname `/boot/vmlinuz`,
**vm** because it supports virtual memory, **linu** as an abbreviation for linux and **z** to **<u>signify that the kernel is a compressed executable</u>**.

### **Tasks performed by the kernel**

**<u>Process scheduling:</u>** Like other UNIX systems, Linux is a **preemptive multitasking OS**, **<u>Multitasking</u>** means that multiple processes (i.e., running programs) can simultaneously reside in memory and each may receive use of the CPU(s). **<u>Preemptive</u>** means that the rules governing which processes receive use of the CPU and for how long are determined by the kernel process scheduler.

**<u>Memory management:</u>** the kernel must share memory among processes **in an equitable and efficient fashion**. Like most modern operating systems, Linux employs virtual memory management, a technique that confers two main advantages:
1. **Processes are isolated from one another and from the kernel**, so that one process can’t read or modify the memory of another process or the kernel.

2. Only part of a process needs to be kept in memory, thereby lowering the memory requirements of each process and allowing more processes to be held in RAM simultaneously. **This leads to better CPU utilization, since it increases the likelihood that, at any moment in time, there is at least one process that the CPU(s) can execute.**

**<u>Provision of a file system:</u>** The kernel provides a file system on disk, allowing files **to be created, retrieved, updated, deleted, and so on**.

**<u>Creation and termination of processes:</u>** The kernel can load a new program into memory, providing it with the resources  that it needs in order to run. Such an instance of a running program **is termed a process**. Once a process has completed execution, **the kernel ensures that the resources it uses are freed for subsequent reuse by later programs**.

**<u>Access to devices:</u>** it allows communication of information
between the computer and the outside world, permitting input, output, or
both. **The kernel provides programs with an interface that standardizes and simplifies access to devices, while at the same time arbitrating access by multiple processes to each device.**

**<u>Networking:</u>** The kernel transmits and receives network messages (packets) **on behalf of user processes**. This task includes routing of network packets to the
target system.

**<u>Provision of a system call application programming interface (API):</u>** Processes can request the kernel to perform various tasks using kernel entry points known as system calls. The Linux system call API is the primary topic of this book

**->** In addition to the above features, **multiuser** OS such as Linux generally provide users **with the abstraction of a virtual private computer**; that is, **<u>each user can log on to the system and operate largely independently of other users</u>**. For example, each user has their own disk storage space (home directory). In addition, users can run programs, each of which gets a share of the CPU and operates in its own virtual address space, and these programs can independently access devices and transfer information over the network. The kernel resolves potential conflicts in accessing hardware resources, so users and processes are generally unaware of the 
conflicts.

### **Kernel mode and user mode**
- Modern processor architectures typically allow the CPU to operate in at least two
different modes: **user mode** and **kernel mode** (sometimes also referred to as **supervisor mode**).

- **<u>Hardware instructions allow switching from one mode to the other</u>**. Correspondingly areas of virtual memory can be marked as being part of **user space** or **kernel space**. When running in user mode, **the CPU can access only memory that is marked as being in user space; attempts to access memory in kernel space result in a hardware exception**. When running in kernel mode, **the CPU can access both user and kernel memory space**.
- Certain operations can be performed only while the processor is operating in kernel mode. Examples include **executing the halt instruction to stop the system,accessing the memory-management hardware, and initiating device I/O operations**.

### **Process versus kernel views of the system**

In many everyday programming tasks, we are accustomed to thinking about programming in a **process-oriented** way. However, when considering various topics covered later in this book, it can be useful to **reorient our perspective to consider things from the kernel’s point of view**

- An executing process doesn’t know when it will next time out, which other processes will then be scheduled for the CPU (and in what order), or when it will next be scheduled. The delivery of signals and the occurrence of interprocess communication events are mediated by the kernel

- A process doesn’t know **where it is located in RAM** or, in general, whether a particular part of its memory space is currently resident in **memory** or held in the **swap area** **(a reserved area of disk space used to supplement the computer’s RAM**).

- a process doesn’t know where on the disk drive the files it accesses are being held; it simply refers to the **files by name**.

- a process doesn’t know where on the disk drive the files it accesses are being held; it simply refers to the files by name.

-  A process operates **<u>in isolation</u>**:

    **1.**  it can’t directly communicate with another process. 
    
    **2.** A process can’t itself create a new process or even end its own existence. 
    
   **3.** a process can’t communicate directly with the input and output devices attached to the computer.

## **The Shell**

A shell is a **special-purpose program** designed to read commands typed by a user
and execute appropriate programs in response to those commands. Such a program
is sometimes known as a **command interpreter**.

**--->** The term **login shell** is used to denote the process that is created to run a shell when the user first logs in.

Whereas on some operating systems the command interpreter is **an integral part of the kernel**, on UNIX systems, the shell is a **user process**. User can open more than one shell

**A number of important shells have appeared over time:**

**<u>Bourne shell (sh):</u>** This is the oldest of the widely used shells, and was written by **Steve Bourne**. It was the standard shell for **Seventh Edition UNIX**. The Bourne shell contains many of the features familiar in all shells: **I/O redirection**, **pipelines**, **filename generation (globbing)**, **variables**, **manipulation of environment variables**, **command substitution**, **background command execution**, and **functions**.

**<u>C shell (csh):</u>** This shell was written by Bill Joy at **the University of California at Berkeley**. The name derives from the resemblance of many of the flow-control constructs of this shell to those of the C programming language. The C shell provided several useful interactive features unavailable in the Bourne shell, including command **`history`** , **command-line editing**, **job control**, and **`aliases`**.\
Although the standard interactive shell on **BSD** was the C shell.

**<u>Korn shell (ksh):</u>** This shell was written as the successor to the Bourne shell by David Korn at AT&T Bell Laboratories. While **maintaining backward compatibility with the Bourne shell**, it also incorporated interactive features similar to those provided by the C shell.

**Bourne again shell (bash):** This shell is **the GNU project’s reimplementation** of
the **Bourne shell**. It supplies interactive features similar to those available
**in the C and Korn shells**. \
**On Linux, the Bourne shell, sh, is typically provided by bash emulating sh as closely as possible.)**

The shells are designed not merely for interactive use, **but also for the interpretation of shell scripts**, which are text files containing shell commands. For this purpose, each of the shells has the **facilities** typically associated with programming languages: variables, loop and conditional statements, I/O commands, and functions.

## **Users and Groups**
**Each user on the system is uniquely identified, and users may belong to groups.**

### **Users**

Every user of the system has a unique login name (**username**) and a corresponding
numeric user ID (**UID**). For each user, these are defined by a line in the system
password file, `/etc/passwd`, which includes the following additional information:

1. **<u>Group ID:</u>** the numeric group ID of the first of the groups of which the user is a member.

2. **<u>Home directory:</u>** the initial directory into which the user is placed after logging in.

3.  **<u>Login shell:</u>** the name of the program to be executed to interpret user commands.

The password record may also include the user’s password, in encrypted form. However, for security reasons, the password is often stored in the separate shadow password file, **<u>which is readable only by privileged users</u>**.

### **Groups**
For administrative purposes—in particular, for controlling access to files and other system resources—it is useful to organize users into groups. For example, the people in a team working on a single project, and thus sharing a common set of files, might all be made members of the same group. **In early UNIX implementations**, a user could be a member of only one group. **BSD allowed a user to simultaneously belong to multiple groups**, an idea that was taken up by other UNIX implementations and the POSIX.1-1990 standard. Each group is identified by a single line in the system group file, `/etc/group`, which includes the following information:

**<u>Group name:</u>** the (unique) name of the group.

**<u>Group ID (GID)</u>** : the numeric ID associated with this group.

**<u>User list:</u>** a comma-separated list of login names of users who are members of
this group.

### **Superuser**
has special privileges within the system. The superuser account has **user ID 0**, and normally has the login name `root`, On typical UNIX systems, **the superuser bypasses all permission checks in the system**. Thus, for example, the superuser can access any file in the system, regardless of the permissions on that file, and can send signals to any user process in the system.