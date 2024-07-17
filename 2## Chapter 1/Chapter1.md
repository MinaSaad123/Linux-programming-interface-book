# **Chapter 1 History and standarads**

## **UNIX**

UNIX implementations had diverged over time, which had led to difficulty in writing applications that
worked on all UNIX implementations. This had led to a drive for standardization of UNIX implementations.

**There are two definitions of UNIX:**

- One of these denotes those operating systems that have passed the official conformance tests for the Single UNIX Specification, and thus are officially granted the right to be branded as **“UNIX”**.

- The other common meaning attached to the term UNIX denotes those systems that look and behave like classical UNIX systems.

***According to the second definition Linux is generally considered to be UNIX system.***

### **What is the meaning of UNIX implementation?**
This term refers to the various versions or derivatives of the UNIX OS.

## **History of UNIX**

The name UNIX was a pun on **MULTICS** (Multiplexed Information and
Computing Service). This project had been a cooperation between MIT, AT&T and general electronics. Ken Thompson participated in this project, but eventually  AT&T **withdrawn** from the project in frustration at its initial failure to develop an economically useful system.

### **What Ken Thompson did?**

<img align= "right" src="https://media.geeksforgeeks.org/wp-content/uploads/18834419_1198504446945937_35839918_n-300x291.png" alt= "The Shell" >

He had drawn several ideas for his new operating system from MULTICS, including a tree-structured file system, a separate program for interpreting commands (the shell), and the notion of files as unstructured streams of bytes.

### **C programming language arise**

Dennis Ritchie, one of Thompson’s colleagues at Bell Laboratories and an early collaborator on UNIX, had designed and implemented the C programming language. This had been an evolutionary process; C followed an earlier interpreted language, the B programming language had initially been implemented by Thompson.

***One of the importances of High-Level language is it made subsequent porting to other hardware architectures possible, while perserving almost the same language morphology and features.***

***

### **UNIX editions evolution**

- **First Edition**, November 1971: By this time, UNIX was running on the PDP-11
and already had a FORTRAN compiler and versions of many programs still
used today, including `ar` ,`cat`, `chmod`, `chown`, `cp`, `dc`, `ed`, `find`, `ln`, `ls`, `mail`, `mkdir`, `mv`, `rm`, `sh`, `su`, and `who`.

- **Second Edition**, June 1972: By this time, UNIX was installed on ten machines
within AT&T.

-  **Third Edition**, February 1973: This edition included a C compiler and the first
implementation of pipes.

- **Fourth Edition**, November 1973: This was the first version to be almost totally
written in C.

-  **Fifth Edition**, June 1974: By this time, UNIX was installed on more than 50 systems.

-  **Sixth Edition**, May 1975: This was the first edition to be widely used outside
AT&T.

- **Seventh Edition**, which had improved the reliability of the system and provided an enhanced file system. This release also contained a number of new tools, including `awk`, `make`, `sed`, `tar`, `uucp`, the Bourne shell, and a FORTRAN 77 compiler.

**Then** UNIX diverged into two important variants: **BSD** and **SystemV**

#### **Berkeley Software Distribution (BSD)**
>  Over time, many new tools and features were developed at Berkeley, including the C shell, the `vi` editor, an improved file system (the Berkeley Fast File System), `sendmail`, a Pascal compiler, and virtual memory management
>> In 1983, the Computer Systems Research Group at the University of California at
Berkeley released **4.2BSD**. This release was significant because it contained a complete **TCP/IP implementation** including the **sockets application programming
interface (API)** and a variety of networking tools. **4.2BSD** and its predecessor **4.1BSD** became widely distributed within universities around the world. They also formed the basis for SunOS.
>>> Later, it is worth noting that free UNIX was already available for the x86-32 during the early 1990s. **Bill and Lynne Jolitz** had developed a port of the already
mature BSD system for the x86-32, known as 386/BSD. This port had been based on the
BSD Net/2 release (June 1991), a version of the **4.3BSD** source code **<u>in which all remaining proprietary AT&T source code had either been replaced or, in the case of six source code files that could not be trivially rewritten, removed</u>**
>>>> After an initial wave of success and popularity, **work on 386/BSD lagged for various reasons**. In the face of an increasingly large backlog of patches, two
alternative development groups soon appeared, creating their own releases based
on: **NetBSD**, **<u>which emphasizes portability to a wide range of hardware platforms</u>**, and **FreeBSD**, **<u>which emphasizes performance and is the most widespread of the modern BSDs</u>**.
>>>>> Probably no discussion of the BSDs in the early 1990s is complete without mention of the lawsuits between **UNIX System Laboratories** (*USL*, the AT&T subsidiary
spun off to develop and market UNIX) and Berkeley. After a lot of lawsuits from USL and countersuits from University of California, There is settlement are done that includes the University of California being required **<u>to remove 3 of the 18,000 files in the Net/2 release, make some minor changes to a few other files, and add USL copyright notices to around 70 other files</u>**, which the university nevertheless could
continue to distribute freely. This modified system was released as 4.4BSD-Lite in June 1994.

#### **System V**

In the meantime, US antitrust legislation forced the breakup of AT&T (legal
maneuvers began in the mid-1970s, and the breakup became effective in 1982),
with the consequence that, since it no longer held a monopoly on the telephone
system, the company was **permitted** to market UNIX,**The first release of System V (five) followed in 1983**.

---

One of the most important **contribution** to increase the awarness within people is a paper made by (Ritchie & Thompson, 1974) in the widely read journal **Communications of the ACM**.

## **History of LINUX**

The term Linux is commonly used to refer to the entire UNIX-like operating system of which the Linux kernel forms a part. However, this is something of a **misnomer**, since many of the key components contained within a typical commercial Linux distribution ___<u>actually originate from a project that predates the inception of Linux by several years</u>__

### **The GNU Project**

- **<u>Richard Stallman</u>**, an exceptionally talented programmer who had been
working at MIT, set to work on creating a “free” UNIX implementation

- Stallman started the GNU project **(a recursively defined acronym for “GNU’s not UNIX”)** to develop an entire, freely available UNIX implementation In 1985, Stallman founded the Free Software Foundation (FSF), a nonprofit organization to support the GNU project as well as the development of free
software in general.

- In 1985, Stallman founded the **Free Software Foundation (FSF)**, a nonprofit
organization to support the GNU project as well as the development of free
software in general.

- One of the important results of the GNU project was the development of the GNU **General Public License (GPL)**, the legal embodiment of Stallman’s notion of free software

### **GPL license policy**

1. Software licensed under the GPL **<u>must be made available in source code form, and must be freely redistributable under the terms of the GPL</u>**.

2. Modifications to GPL-licensed software **are freely permitted**, but any distribution of such modified software must also be under the terms of the GPL. If the modified software is distributed in executable form, the author **<u>must also allow any recipients the option of obtaining the modified source for no more than the cost of distribution</u>**.

### **The genesis of LINUX kernel**

> #### **The beginning**
>The GNU project did not initially produce a working UNIX kernel, but did produce a wide range of other programs like:
> 1. **Emacs** text editor
>2. **GCC** **(** originally the **GNU C compiler**, **<u>but now renamed the GNU >compiler collection</u>**, comprising compilers for C, C++, and other languages **)**
> 3. **the bash shell**
> 4. **glibc** (the GNU C library).
> > #### **Linus Torvalds Contribution**
> > Torvalds  started on a project to create an efficient, full-featured UNIX kernel to run on the 386. Over a few months, **<u>Torvalds developed a basic kernel that allowed him to compile and run various GNU programs</u>**, Torvalds requested the help of other programmers, According to that The call for support proved effective. Other programmers joined Torvalds in the development of Linux, adding various features, such as an improved file system, networking support, device drivers, and multiprocessor support.

### **Linux kernel version numbers**

the kernel developers
adopted a kernel version numbering scheme with each release numbered **x.y.z** : **x**
representing a major version, **y** a minor version within that major version, and **z** a revision of the minor version (minor improvements and bug fixes).

### **LINUX vs GNU/LINUX**

Because a significant part of the program code that constitutes what is commonly known as the Linux system actually derives from the GNU project, Stallman prefers to use the term GNU/Linux to refer to the entire system. **<u>The question of naming (Linux versus GNU/Linux) is the source of some debate in the free software community</u>**.

### **The C programming language versions**

- A created drive for C standardization that culminated in 1989
with the approval of the **American National Standards Institute** (**ANSI**) C standard
(X3.159-1989), which was subsequently adopted in 1990 as an **International Standards Organization** (**ISO**) standard **(ISO/IEC 9899:1990)**., **<u>this standard described the operation of the standard C library</u>**, which includes the `stdio` functions, `string`-handling functions, `math` functions, various header files, and so on. This version of C is usually **known as `C89`, `ANSI C` or (less commonly) `ISO C90`**.

- A revision of the C standard was adopted by **(ISO/IEC 9899:1999)** This standard is usually referred to as `C99`, and includes a range of changes to the language and its standard library. **<u>These changes include the addition of long long and Boolean data
types, C++-style (//) comments, restricted pointers, and variable-length arrays</u>**, Now it's called `ANSI C`.

## **POSIX Standards**

The term **POSIX** (an abbreviation of **Portable Operating System Interface**) refers to a group of standards developed under the auspices of **the Institute of Electrical and Electronic Engineers** (IEEE), specifically its **Portable Application Standards Committee**.

### **POSIX.1 and POSIX.2**

#### **POSIX.1**

**<u>POSIX.1 became an IEEE standard in 1988</u>** and, with minor revisions, was adopted **as an ISO standard in 1990** (ISO/IEC 9945-1:1990).

POSIX.1 is based on **the UNIX system call and the C library function API**, but
it doesn’t require any particular implementation to be associated with this interface.
This means that the **<u>interface can be implemented by any operating system, not specifically a UNIX operating system</u>**.

The POSIX.1 realtime extensions include file **synchronization; asynchronous I/O; process scheduling; high-precision clocks and timers; and interprocess communication using semaphores, shared memory, and message queues. The prefix POSIX is often applied to the three interprocess communication methods to distinguish them from the similar, but older, System V semaphores, shared memory, and message queues.**

####  **POSIX.2**

POSIX.2 (1992, ISO/IEC 9945-2:1993), **standardized the shell and various UNIX utilities, including the command-line interface of the C compiler**.

---

## **Beginning of X/Open company, Open Group and SUS**

- X/Open Company was formed by an international group of computer
vendors **<u>to adopt and adapt existing standards in order to produce a comprehensive, consistent set of open systems standards</u>**. It produced the X/Open
Portability Guide, a series of portability guides based on the POSIX standards. The
first important release of this guide was Issue 3 **(XPG3)** in 1989, followed by XPG4
in 1992. XPG4 was revised in 1994, which resulted in XPG4 version 2.

- When Novell, which acquired the UNIX systems business from AT&T in early
1993, **later divested itself of that business, it transferred the rights to the UNIX trademark to X/Open**, The consequence XPG4 version 2 was subsequently
repackaged **as the Single UNIX Specification**.

- Later, X/Open merged with the Open Software Foundation (**OSF**) **<u>to form The Open Group</u>**, Nearly every company or organization involved with the UNIX system
is now a member of The Open Group, **<u>which continues to develop API standards</u>**.

#### **So what's SUS standards ?**

is a standard developed and maintained by **The Open Group** that defines a superset of the POSIX standard. It specifies a broader set of APIs, shell commands, and utilities for UNIX-like operating systems.**SUS aims to ensure compatibility and interoperability across different UNIX implementation**.

---

#### **What is OSF**
OSF was one of two vendor consortia formed during the UNIX wars of the late
1980s. Among others, OSF **included Digital, IBM, HP, Apollo, Bull, Nixdorf,
and Siemens**, OSF was formed primarily in response **to the threat created by a business alliance between AT&T** (the originators of UNIX) and **Sun** (the most
powerful player in the UNIX workstation market).


## **SUSv3 and POSIX.1-2001**

- Beginning in 1999, the IEEE, The Open Group, and the ISO/IEC Joint Technical
Committee 1 collaborated in the Austin Common Standards Revision Group with the aim of **<u>revising and consolidating the POSIX standards and the Single UNIX Specification</u>**, This resulted in **the ratification of POSIX 1003.1-2001**

- **POSIX 1003.1-2001** replaces SUSv2, POSIX.1, POSIX.2, and a raft of other earlier
POSIX standards. **This standard is also known as the Single UNIX Specification Version 3**, and we’ll generally refer to it in the remainder of this book as `SUSv3`.

The SUSv3 base specifications consists of **around 3700 pages**, divided into the
following four parts:

1. **Base Definitions** (XBD): This part contains definitions, terms, concepts, and
specifications of the contents of header files. **<u>A total of 84 header file specifications are provided</u>**.

2. **System Interfaces** (XSH): This part begins with various useful background information. Its bulk consists of the specification of various functions (which are implemented as either system calls or library functions on specific UNIX implementations).**A total of 1123 system interfaces are included in this part**.

3. **Shell and Utilities** (XCU): This specifies the operation of the shell and various
UNIX commands. **A total of 160 utilities are specified in this part**.

4. **Rationale** (XRAT): This part includes informative text and justifications relating to the earlier parts.

**SUS standards made mandatory many of the interfaces and behaviors that were deemed optional in POSIX**.

## **SUSv4 and POSIX.1-2008**

In 2008, the Austin group completed **<u>a revision of the combined POSIX.1 and Single UNIX Specification</u>**. As with the preceding version of the standard, it consists of a base specification coupled with an XSI extension. We’ll refer to this revision as **SUSv4**.

### **Different between SUS Standards and POSIX standarads**

#### **POSIX standards**

- Define the application programming interface (API) and shell/utilities interface for operating systems, particularly UNIX-like systems.

- A family of standards specified by the IEEE **to promote portability of application programs at the source code level** defining a standard API for the operating system, including system calls, shell, and some utility programs.

#### **SUS standards**

A standard developed and maintained by **The Open Group** that defines a superset of the POSIX standard. It specifies a broader set of APIs, shell commands, and utilities for UNIX-like operating systems.**SUS aims to ensure compatibility and interoperability across different UNIX implementation**.

## **POSIX conformance, XSI conformance, and the XSI extension**

**POSIX conformance:** This defines a baseline of interfaces that a conforming
implementation must provide. It permits the implementation to provide other
optional interfaces.

**X/Open System Interface (XSI) conformance:** To be XSI conformant, an implementation
must meet all of the requirements of **<u>POSIX conformance</u>** and also must
**<u>provide a number of interfaces and behaviors that are only optionally required
for POSIX conformance</u>**. An implementation must reach this level of conformance
in order to obtain the **UNIX 03 branding** from The Open Group.

**In later chapters, when we talk about SUSv3 conformance, we mean XSI
conformance.**

---
### **XSI extension**

The additional interfaces and behaviors required for XSI conformance.

## **Unspecified, weakly specified and legacy features**

Occasionally, we refer to an interface as being **“unspecified”** or **“weakly specified”**
within SUSv3.

 - **<u>unspecified interface:</u>** we mean one that **is not defined at all in the formal standard**, although in a few cases **there are background notes or rationale text that mention the interface.**

- **<u>weakly specified:</u>** is shorthand for saying that, while the
interface is included in the standard, important details are left unspecified (**commonly because the committee members could not reach an agreement due to differences in existing implementations**).

- **<u>LEGACY features</u>:** Sometimes, we note that SUSv3 marks a specified feature as LEGACY. **This term denotes a feature that is retained for compatibility with older applications**, but whose limitations mean that its use should be avoided in new applications. In many cases, some other API exists that provides equivalent functionality.

## **UNIX Standards Timeline**

<img  src="https://i.imgur.com/6yGiLF8.png" alt= "Standarads history" >

The solid lines indicate direct descent between standards, and the dashed arrows indicate cases where one standard influenced another standard, was incorporated as part of another standard, or simply deferred to another standard.

|POSIX "Portable Operating System Interface" |SUS "the Single UNIX Specification" |
|--------------------------------------------|------------------------------------|
|                                    |                                 |


## **The Linux Standard Base (LSB)**
**is an effort to ensure compatibility among the various Linux distributions.** 

To do this, the LSB **develops and promotes a set of standards for
Linux systems with the aim of ensuring that binary applications** (i.e., compiled programs) can run on any LSB-conformant system.