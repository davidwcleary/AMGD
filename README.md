# AMGD
# Command Line Basics

Welcome to the command line basics tutorial for the Analysing Microbial Genomic Data course. 

The following short guide is designed to demystify the UNIX command line, introducing course participants to the very basics of the environment, as well as simple commands to navigate, find, view and edit files using simple Bash commands.


## UNIX

So, What is Unix? Unix is an operating system developed in the 1960s. It provides a means to perform operations on your computer when there is no Graphical User Interface (GUI). It's worth remembering that there are differnt versions of UNIX. Some of you may have heard of Linux. This is a family of open-source Unix-like operating systems based on the Linux kernal, and operating system developed and released by Linus (hence the name) Torvalds in the early 90's.

The shell is the interface between you and the kernel, the bit that is actually doing all the work.  You may have come across BASH.  This is the Bourne-Again Shell. Bash is both a unix shell and command language and is/was the default shell for most unix operating systems. Those of us with new Macbooks will see our default shell is now Zsh (the Z-shell), which is an extended, improved Bash. Confused? Don't worry. These are the idiosyncracies that one learns over time.

The important point is that the shell is the **command line interpreter** which takes the instructions (commands) that you write and gives them what they need to run. 

### Directory Structure

The file system can be thought of as un upside down tree, with the root (signified by / )at the top and then a hierachical arrangement of directories and files beneath.

When we talk about **absolute paths** that refers to the address of where you, or the thing you are looking for, is in that hierachy.  In the above example the absolute path for the file sequence.fasta would be:

<img src="https://github.com/davidwcleary/AMGD/blob/main/file-system.png" width="150" height="150">

> /home/data/sequence/sequence.fasta

## Basic Commands

For the purposes of getting you started without having to worry about installing software we are going to make use of a fantastic free resource called at https://sandbox.bio/ Go to that address and click on the 'Command Line' Playground. You should now have a terminal window in your browser.

<img src="https://github.com/davidwcleary/AMGD/blob/main/Screenshot%202023-03-02%20at%2015.12.15.png">

The first thing you might notice is the prompt **guest@sandbox$** this shows that the shell is ready and waiting for some form of command. In other terminals the prompt may look different but typically has **%** or **$** at the end. For ease all the example commands below will be shown from a prompt of **$**

### Where am I?
First, where am I? To work this out we can use the Path to Working Directory command `pwd`. This command will return the absolute path to where you are. 

```shell
$ pwd
```
In this case it will return:

> /shared/data


### What is here?
Now let us have a look at what is here in this folder called **data**.  Here we can use the `ls` (list) command. Here we see we have another directory called **tutorials**.

```shell
$ ls
tutorials 
```

It's worth noting that for this command, and indeed all of those I am going to introduce you to, you can get more information by typing `man` (manual):

```shell
$ man ls
```
In this sandbox environment the manual will be shown completely on screen. In other terminals you may get an interactive page, which you can scroll down using the spacebar. In that situation, to quit the manual simply press **Q**.

Ok, back to listing directory contents. Sometimes  you might want to know more about the files/directories that are present.  This is where we can use **flags**.  Think of these as extra bits of command you can pass to, in this case, the command `ls`.  Here we have an example of -l or long listing. In this case we get a lot more information: 

```shell
$ ls -l
total 1
drwxrwxrwx 1 0 0 4096 Mar  2 10:45 tutorials
```

The third line begins with an overview of who has which permissions for, in this case, the directory **tutorials**. What then follows is information about ownership, file size (note this is a folder but the folder size is not what is being displayed here - more on that later), date and time last modified and finally the name.

Now try the following and see if you can work out what the flags -t -r and -h are doing.

```shell
$ ls -ltrh
```

### Changing Directory and Making a New Directory

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

Now we have some files to play with, but first let's look at some important flags for `cd`

```shell
$ cd .
```
The . here denotes current directory

```shell
$ cd ..
```
.. means 'up one' or 'Parent' directory level

```shell
$ cd ../someotherplace
```
from where you can then go across into 'someotherplace' (providing it exists). Of course here `cd ../../` equates to two levels `cd ../../../` three etc. 

```shell
$ cd ~
```

As the saying goes, there's no place like home. If you're lost this is always a good one to know, and you can always check where you end up by returning to our very first command `pwd`

While we are here let's make our own directory and move into it.  We do this by using the MaKe DIRectory command `mkdir` followed by the name of the directory we want to create.  This is probably a good time to highlight the importance of file/folder naming convention. General rules:

  * Do not include spaces! my-file.txt or my-folder or my_folder NEVER my file.txt.
  * Dates help a lot 2023-03-02-myfile.txt.
  * No special characters as they get interpreted very differently on the command line to how you would read them.

Now back to `mkdir`. Let's check we are in `/shared/data/tutorials/terminal-basics` make a folder called ***test-folder*** check it is there and then move into it.

```shell
$ mkdir test-folder
$ ls
$ cd test-folder
$ pwd
```

### Copying Files

Now we are in our brand new folder let's put something in it. Let's copy a file from `/shared/data/tutorials/terminal-basics`. To do these we use `cp` as follows:

```shell
$ cp ../orders.tsv .
```

Now there are a few elements we are bringing together here. The first is that I am telling `cp` that the file I want to copy is one level up `../` called orders.tsv and I want to copy it to where I am `.`. I could specify the absolute path to the file using /shared/data/tutorials/terminal-basics/orders.tsv but typing can be boring and where there is safe shortcut we should try and use it.

> Have you tried autocompleting with TAB yet? I'll let you find that joy all buy yourself.

Back to our file we have just copied across. Check it is there using `ls` and to avoid confusion, let's rename. This command to do this is `mv`.  There are `rename` commands but `mv` does what we need very nicely. Remember to alwasys check that what happens is what you intended!

```shell
$ mv orders.tsv orders-copy.tsv
```

### Viewing Files

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
WC(1)                         User Commands                         WC(1)

NAME
       wc - print newline, word, and byte counts for each file

SYNOPSIS
       wc [OPTION]... [FILE]...
       wc [OPTION]... --files0-from=F

DESCRIPTION
       Print  newline,  word,  and byte counts for each FILE, and a total
       line  if  more  than  one  FILE  is  specified.   A  word   is   a
       non-zero-length sequence of characters delimited by white space.
```

Ok so what the manual is telling us is that if we just use `wc` without any extra flags we get the number of newlines, then number or words and the file size printed out. Pretty useful. Generally I am only interested in the number of lines (imagine how useful that might be for counting reads in a fastq file) so I generally use `wc -l` which here gives us:

```shell 
$ wc -l orders-copy.tsv 
4623 orders-copy.tsv
```
So now we know. There are just over 4600 lines in our file. Are we really interested in all of it? If not, how can we extract the information we need. Onwards to manipulating files.

### Manipulating Files

Here's a question. orders-copy.tsv is a tab sepated text file (.tsv) that contains individual orders from my restaurant. Problem is that this information just is not that helpful. I want to know what the most popular Burrito dish is but I don't want to trawl through 4000-odd orders and manually count them.  What can I do? Bash to the rescue, and more specifically pipes or `|` as they are shown.  Pipes allow me to take one command and pass the output of that into another command. Let's see how this might work in practise.

The first thing is to get the contents of my file and for this I know I can use the `cat` but what I really want is just teh third column, the one with all the food listed.  Here I will use `cut` with `-f` to specify which field I want, in this case number 3.

$ cat orders-copy.tsv | cut -f 3

That still leaves me with all the dishes I am not interested in though. 

Now I can use `grep`. There is no time to go through the complexities of grep except to say it stands for **get regular expression** and is a incredibly useful tool for searching and finding.  Here I want to tell grep to search the ouput of the `cut` command for "Burrito", making sure it's not case sensitive by also using the `-i` flag.

```shell 
$ cat orders-copy.tsv | cut -f 3 | grep -i "Burrito" 
Steak Burrito
Steak Burrito
Chicken Burrito
Chicken Burrito
Barbacoa Burrito
Chicken Burrito
Carnitas Burrito
Chicken Burrito
Steak Burrito
Steak Burrito
```

Great, that's looking better. The problem I have now though is that my counting command requires all things to be counted as the same next to each other i.e., steak, chicken, steak will not return two steaks but one of each. So what I need to do first is `sort` by name and then group (or in other words identify all the unique dish names) and count how many are in each group.  I do all of this by adding `| sort | uniq -c `

```shell 
$ cat orders-copy.tsv | cut -f 3 | grep -i "Burrito" | sort| uniq -c
     91 Barbacoa Burrito
      6 Burrito
     59 Carnitas Burrito
    553 Chicken Burrito
    368 Steak Burrito
     95 Veggie Burrito
```

Much better! Now to sort numerically by column 1 using `|sort -k1n` and there we have it, chicken burritos are the most popular dish. But hang on. Do I need to do this ever time I want to find this information out? What if I forget, or I want to find third most popular dish. Easy.  Let's just redirect the output of this one line of Bash into a new file...just like so.


```shell 
$ cat orders-copy.tsv | cut -f 3 | grep -i "Burrito" | sort| uniq -c > burritos.tsv
```

et voila we have a new file that will contain all the information we need for as long as we need it. The best part about all of this? Look at the original file and you will see that nothing has happened to it, it's exactly as it was to begin with.

Ok, I hear you say but I want to look at Tacos as well, and I want that information in with the Burrito numbers I've worked so hard to get. No problem I say. Let's just repeat the above and this time **append** our burrito file.

```shell 
$ cat orders-copy.tsv | cut -f 3 | grep -i "Taco" | sort| uniq -c >> burritos.tsv
```

Did you spot it? The ABSOLUTELY CRITICAL difference `>>` instead of `>`?  I had used the latter my output from the Taco search would simply have overwritten the burritos.  By using `>>` I make sure to add the new data to the end of the first file.

Let's finish with the `rm` command, or remove. To get rid of burritos.tsv you can type

```shell 
$ rm burritos.tsv
```

Be warned however, there is no recycle bin, no undo, no amount of swearing, praying or IT support that can bring a file back once it has been subjected to `rm`.  This goes for folder, sub-folders and operating systems.  There is a command that I will not spell out here that it used whilst in `/` will wipe out everything in your computer before your very eyes. So, make sure you know what it is you are deleting.

## Other Useful Commands

These are some that also come in useful. I'll continue to populate as I think of them. There is also a Terminal Basics tutorial at the same sandbox, do feel free to work through that as well...it shouldn't take you long.

* If your screen is looking terribly confusing, then have a good clear out with `clear`
* Can't remember what you did, use `history` to bring up a list of previously used commands. How many it returns can be altered in terminal preferences.

## Summary

By now you will hopefully have recognised the simple power of Bash. This is the tip, of the tip of the iceberg of what it can do for you. I hope this leaves you inspired and keen to learn more. Good luck with the journey. 


