# AMGD
## Command Line Basics

Welcome to the command line basics tutorial for the Analysing Microbial Genomic Data course. 

The following short guide is designed to demystify the UNIX command line, introducing course participants to the very basics of the environment, as well as simple commands to navigate, find, view and edit files using simple Bash commands.

Firstly, please complete the Terminal Basics tutorial at https://sandbox.bio/ This will be an excellent starting point. Once you've completed that go to 'Command Line' Playground at the same address. Here you can use the commands which I will introduce you to and have a bit of a play. 

### UNIX

So, What is Unix? Unix is an operating system developed in the 1960s. It provides a means to perform operations on your computer when there is no Graphical User Interface (GUI). It's worth remembering that there are differnt versions of UNIX. Some of you may have heard of Linux. This is a family of open-source Unix-like operating systems based on the Linux kernal, and operating system developed and released by Linus (hence the name) Torvalds in the early 90's.

The shell is the interface between you and the kernel, the bit that is actually doing all the work.  You may have come across BASH.  This is the Bourne-Again Shell. Bash is both a unix shell and command language and is/was the default shell for most unix operating systems. Those of us with new Macbooks will see our default shell is now Zsh (the Z-shell), which is an extended, improved Bash. Confused? Don't worry. These are the idiosyncracies that one learns over time.

The important point is that the shell is the **command line interpreter** which takes the instructions (commands) that you write and gives them what they need to run. 

### Directory Structure

The file system can be thought of as un upside down tree, with the root (signified by / )at the top and then a hierachical arrangement of directories and files beneath.

When we talk about **absolute paths** that refers to the address of where you, or the thing you are looking for, is in that hierachy.  In the above example the absolute path for the file sequence.fasta would be:

<img src="https://github.com/davidwcleary/AMGD/blob/main/file-system.png" width="150" height="150">

> /home/data/sequence/sequence.fasta

### Basic Commands

Ok, let's assume you have a terminal window and what you should see is some form of prompt, typically **%**. 
Now let's start having a look around in the https://sandbox.bio/ Command Line playground. 

First, where am I? To work this out we can use the Path to Working Directory command `pwd`. This command will return the absolute path to where you are. 

```shell
% pwd
```
In this case it will return:

> /shared/data

Now let us have a look at what is present:

```shell
% ls
```
> guest@sandbox$ ls
> tutorials 

For this command, and indeed all of those I am going to introduce you to, you can get more information by typing:

```shell
% man ls
```
In this sandbox environment the manual will be shown on screen, in other terminals you may get a page down which you can scroll using the spacebar.  In that situation, to quit simply press **Q**.

Ok, bak to listing directory contents. Sometimes though you might want to know more about the files that are present.  This is where we can use **flags**.  Think of these as extra bits of command you can pass to `ls`.  Here we have an example of -l or long listing. In this case we get a lot more information: 

```shell
% ls -l
```
> guest@sandbox$ ls -l
> total 1
> drwxrwxrwx 1 0 0 4096 Mar  2 10:45 tutorials

The third line begins with an overview of who has which permissions for, in this case, the directory **tutorials**. What then follows is information about ownership, file size (note this is a folder but the folder size is not what is being displayed here - more on that later), date and time last modified and finally the name.

Now try the following and see if you can work out what the flags -t -r and -h are doing.

```shell
% ls -ltrh
```







