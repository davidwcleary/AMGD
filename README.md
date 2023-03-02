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

Ok, let's assume you have a terminal window and what you should see is some form of prompt, typically **%** or **$**. 
Now let's start having a look around in the https://sandbox.bio/ Command Line playground. 

#### Where am I?
First, where am I? To work this out we can use the Path to Working Directory command `pwd`. This command will return the absolute path to where you are. 

```shell
$ pwd
```
In this case it will return:

> /shared/data


#### What is here?
Now let us have a look at what is here in this folder called **data**.  Here we can use the `ls` (list) command. Here we see we have another directory called **tutorials**.

```shell
$ ls
```
> guest@sandbox$ ls
> tutorials 

It's worth noting that for this command, and indeed all of those I am going to introduce you to, you can get more information by typing `man` (manual):

```shell
$ man ls
```
In this sandbox environment the manual will be shown completely on screen. In other terminals you may get an interactive page, down which you can scroll using the spacebar. In that situation, to quit simply press **Q**.

Ok, back to listing directory contents. Sometimes  you might want to know more about the files/directories that are present.  This is where we can use **flags**.  Think of these as extra bits of command you can pass to, in this case, the command `ls`.  Here we have an example of -l or long listing. In this case we get a lot more information: 

```shell
$ ls -l
```
> guest@sandbox$ ls -l

> total 1

> drwxrwxrwx 1 0 0 4096 Mar  2 10:45 tutorials

The third line begins with an overview of who has which permissions for, in this case, the directory **tutorials**. What then follows is information about ownership, file size (note this is a folder but the folder size is not what is being displayed here - more on that later), date and time last modified and finally the name.

Now try the following and see if you can work out what the flags -t -r and -h are doing.

```shell
$ ls -ltrh
```

#### Changing and Making a Directory

To move around the directory structure we can use the Change Directory `cd` command.  

```shell
$ cd tutorials/
```
Listing contents with `ls` shows us another directory so let's go ahead and move into that one...

```shell
$ ls
terminal-basics
```

...and see what's there.

```shell
$ cd terminal-basics/
$ ls -l
total 14
-rw-rw-rw- 1 0 0 105054 Mar  2 10:45 orders.tsv
-rw-rw-rw- 1 0 0     45 Mar  2 10:45 ref.fa
-rw-rw-rw- 1 0 0     45 Mar  2 10:45 ref.fa.bak
```

Now we have some files to play with but first let's look at some imporant flags for `cd`

```shell
$ cd .
```
The . here denotes current directoty

```shell
$ cd ..
```
.. means 'up one' directory level

```shell
$ cd ../someotherplace
```
from where you can then go across into someotherplace (providing it exists). Of course here `cd ../../` equates to two levels `cd ../../../` three etc. 

```shell
$ cd ~
```

As the saying goes, there's no place like home. If you're lost this is always a good one to know, and you can always check where you end up by returning to our very first command `pwd`

While we are here let's make our own directory and move into it.  We do this by using the MaKe DIRectory command `mkdir` followed by the name of the directory we want to create.  This is probably a good time to highlight the importance of file/folder naming convention. General rules are as follows:

  * Do not include spaces! my-file.txt or my-folder or my_folder NEVER my file.txt.
  * Dates help a lot 2023-03-02-myfile.txt.
  * No special characters as they get interpreted very differently on the command line to how you would read them.

Now back to `mkdir`. Let's check we are in `/shared/data/tutorials/terminal-basics` make a folder called ***test-folder*** check it is there and then move into it.

```shell
$ mkdir test-folder
$ ls
$ cd test-folder
```

#### Copying Files

Now we are in our brand new folder let's put something here. Let us copy a file from `/shared/data/tutorials/terminal-basics`. To do these we use `cp` as follows:

```shell
$ cp ../orders.tsv .
```

Now there are a few elements we are bringing together here. The first is that I am telling `cp` that the file I want to copy is one level up `../` called orders.tsv and I want to copy it to where I am `.`.

Check it is there using `ls` and to avoid confusion, let's rename it while we are here. This command is `mv`.  There are `rename` commands but `mv` does what we need very nicely. Remember to check that what happens is what you intended.

```shell
$ mv orders.tsv orders-copy.tsv
```

#### Viewing Files

There are a number of ways to view files. My preferred method for having a sneaky peak is `less` followed by the file name. There is also a similar command called `more`. Neither of these are available in this sandbox but never mind as we have `head`, `tail`, and `cat`.  Let's use these to look at our orders-copy.tsv.

`head` as you imagine shows you, by default the first 10 lines of the file.  This default behaviour can be changed by using the `-n` flag and asking for the number of lines you want to see.  Similarily `tail` does exactly the same but from the bottom. 

```shell
$ head orders-copy.tsv 
id      num     item_name
1       1       Chips and Fresh Tomato Salsa
1       1       Izze
1       1       Nantucket Nectar
1       1       Chips and Tomatillo-Green Chili Salsa
2       2       Chicken Bowl
3       1       Chicken Bowl
3       1       Side of Chips
4       1       Steak Burrito
4       1       Steak Soft Tacos

$ head -n 5 orders-copy.tsv 
id      num     item_name
1       1       Chips and Fresh Tomato Salsa
1       1       Izze
1       1       Nantucket Nectar
1       1       Chips and Tomatillo-Green Chili Salsa

$ tail -n 5 orders-copy.tsv 
1833    1       Steak Burrito
1833    1       Steak Burrito
1834    1       Chicken Salad Bowl
1834    1       Chicken Salad Bowl
1834    1       Chicken Salad Bowl
```

`cat` on the other hand will show you everything...REGARDLESS OF HOW BIG YOUR FILE IS!! So how would you know how many lines are in your file to avoid an ever scrolling terminal window.  Here we can use `wc` literally ***word count***


```shell
$ man wc
```
>       wc - print newline, word, and byte counts for each file

Ok so what the manual is telling us is that if we just use `wc` without any extra flags we get the number of newlines, then number or words and the file size printed out. Pretty useful. Generally I am only interested in the number of lines (imagine how useful that might be for counting reads in a fastq file) so I generally use `wc -l` which here gives us:

```shell 
$ wc -l orders-copy.tsv 
```
>4623 orders-copy.tsv


#### Manipulating Files



