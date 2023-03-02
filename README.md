# AMGD
## Command Line Basics

Welcome to the command line basics tutorial for the Analysing Microbial Genomic Data course. 

The following short guide is designed to demystify the UNIX command line, introducing course participants to the very basics of the environment, as well as simple commands to navigate, find, view and edit files using simple Bash commands.

Firstly complete the Terminal Basics tutorial at https://sandbox.bio/ This will be an excellent starting point.  Once you've completed that go to 'Command Line' Playground at the same address. Here you can use the commands I will introduce you to and have a bit of a play. 

### UNIX

So, What is Unix? Unix is an operating system developed in the 1960s. It provides a means to perform operations on your computer when there is no Graphical User Interface (GUI). It's worth remembering that there are differnt versions of UNIX. Some of you may have heard of Linux. This is a family of open-source Unix-like operating systems based on the Linux kernal, and operating system developed and released by Linus (hence the name) Torvalds in the early 90's.

The shell is the interface between you and the kernel, the bit that is actually doing all the work.  You may have come across BASH.  This is the Bourne-Again Shell. Bash is both a unix shell and command language and is/was the default shell for most unix operating systems. Those of us with new Macbooks will see our default shell is now Zsh (the Z-shell), which is an extended, improved Bash. Confused? Don't worry. These are the idiosyncracies that one learns over time.

The important point is that the shell is the **command line interpreter** taking the commands you write and giving them what they need to run properly. 

### Directory Structure

The file system can be thought of as un upside down tree, with the root (signified by / )at the top and then a hierachical arrangement of directories and files beneath.

When we talk about **absolute paths** that refers to the address of where you, or the thing you are looking for, is in that hierachy.  In the above example the absolute path for the file sequuence.fasta would be:

[file-system] ()

> /home/data/raw/sequence.fasta

### Basic Commands

```shell
pwd
```
This command will return the absolute path to where you are. In this case it will return:

> /shared/data

```shell
ls
```

To find out what is in your directory type ls. This will list all contents: 
