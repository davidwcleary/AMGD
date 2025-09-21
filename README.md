# Analysing Microbial Genomic Data

<p align="center" width="100%">
 <img src="https://github.com/davidwcleary/AMGD/blob/main/images/AMGD-2025.png" width="400" height="400">
</p>

# Command Line Basics

Welcome to the command line basics tutorial for the Analysing Microbial Genomic Data course run by the Institute of Microbiology and Infection, University of Birmingham.

The following short guide is designed purely to demystify the command line, introducing course participants to the very basics of the environment, as well as some simple commands to navigate, find, view and edit files using Bash.

## UNIX

So, what is Unix? Unix is an operating system that was developed in the 1960s. For us bioinformaticians it is particularly important as it provides a means to perform operations on our computers when there is no Graphical User Interface (GUI). This is very common for programs and tools developed for analysing sequence data. It's worth knowing that there are differnt versions of Unix. Some of you may have heard of Linux for example. This is a family of open-source Unix-like operating systems based on the Linux kernel, an operating system developed and released by Linus (hence the name) Torvalds in the early 90's. At this point there is no need to go further down this particular rabbit hole.

The shell is the interface between you and that operating system kernel, the bit that is actually doing all the work. You may have come across BASH. This is the Bourne-Again Shell. Bash is both a unix shell and command language and is/was the default shell for most unix operating systems. Those of us with new Macbooks will see our default shell is now Zsh (the Z-shell), which is an extended, improved Bash. Confused? Don't worry. These are the idiosyncracies that one learns over time.

The important point is that the shell is the **command line interpreter** which takes the instructions (commands) that you write and gives them what they need to run i.e., allocating memory and compute to tasks.

As you become more accustomed to working in these unix-like environments it is worth getting to know some of the basic details of how they work, but for now we only need to concern ourselves with navigating the file system and performing some basic file manipulations. 

### Directory Structure

The file system can be thought of, diagramatically, as un upside down tree with the root (signified by `/` ) at the top and a hierachical arrangement of directories and files beneath as the branches and leaves if we want to torture this metaphor further. 

<img src="https://github.com/davidwcleary/AMGD/blob/main/file-system.png" width="150" height="150">

Where any particular file or folder is located can be referred to by its' path. When we talk about **absolute path** this refers to the address of where you, or the thing you are looking for, is in that hierachy from the root. That is to say, starting at `/` what is the full path to the file.  In the above example the absolute path for the file sequence.fasta would be:

> /home/data/sequence/sequence.fasta

## Basic Commands

For the purposes of getting started without having to worry about installing software we are going to make use of a fantastic free resource at https://sandbox.bio/ Go to that address, scroll down to 'Terminal Basics' and click 'Start'. You should now have a terminal window in your browser that looks like the below.

<img src="https://github.com/davidwcleary/AMGD/blob/008950de4a23ed4b0254659afbaac226c97dd1ab/Screenshot%202024-06-20%20at%2015.10.00.png">

The first thing you might notice is the prompt **root@localhost:~/tutorial#** this shows that the shell is ready and waiting for some form of command. In other terminals the prompt may look different, but typically has **%** or **$** at the end. For ease all the example commands we encounter will be shown from a prompt of **$**

To make it clear, every command is shown as:

```shell
$ some-command
```

With the subsequent output shown as:

> command output

### Where am I?
First, where am I? Always a useful starting point. To work this out we can use our very first command. The Path to Working Directory command `pwd`. This command will return the absolute path to where you are. 

```shell
$ pwd
```
In this case it will return:

> /home/sandbox/terminal-basics

### What is here?
Now let us have a look at what is here in this folder called **tutorial**.  Here we can use the `ls` (list) command. Here we see we have three files called **orders.tsv** **ref.fa** and **ref.fa.bak**. 

```shell
$ ls 
```

> orders.tsv  ref.fa  ref.fa.bak

It's worth noting that for this command, and indeed all of those I am going to introduce you to, you can get more information by typing `man` (for manual) followed by the command name. For example:

```shell
$ man ls
```
You are now in an interactive page which you can scroll down using the spacebar. To quit the manual simply press **q**. This applies to all manual pages.

Ok, back to listing directory contents. Sometimes you might want to know more about the files/directories that are present in that directory.  This is where we can use **flags**. Think of these as extra bits of command you can pass to the command, in this case `ls`.  Here we have an example of `-l` which denotes long listing. By using this flag we get a lot more information: 

```shell
$ ls -l
```

> total 118
> 
> -rw-r--r-- 1 root root 105054 Jun 20  2024  orders.tsv
>
> -rw-r--r-- 1 root root     45 Jun 20  2024  ref.fa
>
> -rw-r--r-- 1 root root     45 Jun 20  2024  ref.fa.bak
>
> -rw-r--r-- 1 root root  13400 Jun 20  2024 'tty rows 40 cols 35'

Let's briefly go through the output. 

The line begins with an overview of who has which permissions for the file **order.tsv**. What then follows is information about ownership, file size, date and time last modified and finally the name.

Most commands have a multitude of flags, all listed in the manual and all enabling the command to work in slightly different ways. Try the following and see if you can work out what the flags -t -r and -h are doing.

```shell
$ ls -ltrh
```

### Making a New Directory and Moving Around

While we are here let's make our own directory and move into it.  We do this by using the MaKe DIRectory command `mkdir` followed by the name of the directory we want to create.  This is probably a good time to highlight the importance of file/folder naming convention. General rules:

  * Do not include spaces! my-file.txt or my-folder or my_folder NEVER my file.txt.
  * Dates help a lot 2023-03-02-myfile.txt.
  * No special characters as they get interpreted very differently on the command line to how you would read them.

Now back to `mkdir`. Let's check we are in `/root/tutorial` make a folder called **test-folder** and then check it is there. The commands you will need to do this are as follows:

```shell
$ pwd
```
```shell
$ mkdir test-folder
```
```shell
$ ls -ltrh
```

> total 118K
> 
> -rw-r--r-- 1 root root 105054 Jun 20  2024  orders.tsv
>
> -rw-r--r-- 1 root root     45 Jun 20  2024  ref.fa
>
> -rw-r--r-- 1 root root     45 Jun 20  2024  ref.fa.bak
>
> -rw-r--r-- 1 root root  13400 Jun 20  2024 'tty rows 40 cols 35'
>
> drwxr-xr-x 2 root root    0 Jun 20  2024  test-folder

Now we want to move into that new folder. To move around the directory structure we can use the Change Directory `cd` command specifying where we want to go.  

```shell
$ cd test-folder/
```

Before we move on, let's look at some important flags for `cd`. As you might imagine change directory is a very vague command and therefore comes with useful add-ons:

```shell
$ cd .
```
The . here denotes current directory

```shell
$ cd ..
```
.. means 'up one' or 'Parent' directory level. You don't need to name the destination, simply typing this will send you up one level.

```shell
$ cd ../someotherplace
```
You can add on further destinations to make life easier. In this example you are going one up and then down into another folder called 'someotherplace' (providing it exists). It should be no surprise that `cd ../../` equates to two levels `cd ../../../` three etc etc.

```shell
$ cd ~
```

As the saying goes, there's no place like home `~`. If you're lost this is always a good one to know, and you can always check where you end up by returning to our very first command `pwd`.


### Copying Files

Now we are in our brand new folder let's put something in it. Let's copy a file from `/root/tutorial/` so that we having something to play with. To do these we use `cp` as follows:

```shell
$ cp ../orders.tsv .
```

Now there are a few elements we are bringing together here. The first is that I am telling `cp` that the file I want to copy is one level up `../` called **orders.tsv** and I want to copy it to where I am `.`. I could specify the absolute path to the file using **/root/tutorial/orders.tsv** but typing can be boring and where there is safe shortcut we should try and use it.

Have you tried autocompleting with **TAB** yet? I'll let you find that joy all by yourself.

Back to our file we have just copied across. Check it is there using `ls` and to avoid confusion, let's rename it. The command to do this is `mv`.  There are `rename` commands but `mv` does what we need very nicely. Remember to always check that what happens is what you intended!

```shell
$ mv orders.tsv orders-copy.tsv
```

This is simply telling `mv` to change the name from **orders.tsv** to **orders-copy.tsv**.  Note that the order of FROM TO is imporant here.

### Viewing Files

There are a number of ways to view the contents of files. My preferred method for having a sneaky peak is `less` followed by the file name. There is also a similar command called `more`. Neither of these are available in this sandbox unfortunately but it's not a problem as we have `head`, `tail`, and `cat`.  Let's use these to look at our orders-copy.tsv.

`head`, as you may imagine shows you the top or HEAD of the file by printing this to the terminal window and then returning a prompt ready for the next command. By default, and most commands have a default behaviour, it shows the first 10 lines only.  This default behaviour can be changed by using the `-n` flag and asking for the number of lines you want to see.  Similarily `tail` does exactly the same but from the BOTTOM. 

```shell
$ head orders-copy.tsv 
```

> id      num     item_name
> 
> 1       1       Chips and Fresh Tomato Salsa
> 
> 1       1       Izze
> 
> 1       1       Nantucket Nectar
> 
> 1       1       Chips and Tomatillo-Green Chili Salsa
> 
> 2       2       Chicken Bowl
> 
> 3       1       Chicken Bowl
> 
> 3       1       Side of Chips
> 
> 4       1       Steak Burrito
> 
> 4       1       Steak Soft Tacos

```shell
$ head -n 5 orders-copy.tsv 
```

> id      num     item_name
> 
> 1       1       Chips and Fresh Tomato Salsa
> 
> 1       1       Izze
> 
> 1       1       Nantucket Nectar
> 
> 1       1       Chips and Tomatillo-Green Chili Salsa

```shell
$ tail -n 5 orders-copy.tsv 
```

> 1833    1       Steak Burrito
> 
> 1833    1       Steak Burrito
> 
> 1834    1       Chicken Salad Bowl
> 
> 1834    1       Chicken Salad Bowl
> 
> 1834    1       Chicken Salad Bowl

`cat` on the other hand will show you everything...REGARDLESS OF HOW BIG YOUR FILE IS!! So how would you know how many lines or characters are in your file to avoid an ever scrolling terminal screen.  Here we can use `wc` literally ***word count*** to find out.  Let's use `man wc` to look first at the default behaviour.

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

Ok so what the manual is telling us is that if we just use `wc` without any extra flags we get the number of newlines, then number of words and the file size printed to the terminal. Pretty useful! Generally I am only interested in the number of lines (imagine how useful that might be for counting reads in a fastq file) so I generally use `wc -l` which here gives us:

```shell 
$ wc -l orders-copy.tsv 
```

> 4623 orders-copy.tsv

So now we know. There are just over 4600 lines in our file. Are we really interested in all of it? If not, how can we extract only information we need. Onwards to manipulating files!

### What did I just type?

So far we have used fairly easy, short commands, and not that many of them either. However, I guarantee you that at some point you will need to look at a previous command and/or run it again.  

Here there are two very easy ways to do this. 1. you can simply use the up arrow key (^) whilst on a prompt ```$``` to scroll through in chronological order (most recent to oldest) the commands you have entered, or 2. you can make use of ```$ history```.  This command will bring up a numbered list of commands (the number varies and can be altered in terminal preferences).  To run a command from this list either stick to the old favourite of copy and paste or you can invoke that command in a number of ways e.g., ```!35``` to run number 35 for example (note this doesn't work in this sanbox environment). 

### Manipulating Files

Here's a question. orders-copy.tsv is a tab sepated text file (.tsv) that contains individual orders from a restaurant. The problem is that this information just is not that helpful in it's current form. Let's say that all I really want to know is what is the most popular Burrito dish. The last thing I want to do is trawl through 4000-odd orders and manually count them.  What can I do instead? Bash to the rescue, and more specifically pipes or `|` as they are shown. Pipes allow me to take one command and pass the output of that into another command. Let's see how this might work in practise.

The first thing is to get the contents of my file and for this I know I can use `cat` but what I really want is just the third column of my file, the one with the food listed. Here I will use `cut` with `-f` to specify which field (column) I want to extract, in this case column number 3.

```shell
$ cat orders-copy.tsv | cut -f 3
```

Of course that still leaves me with all the dishes, and I am still only interested in Burritos. 

Now I can employ the power of `grep`. There is no time to go through the complexities of `grep` except to say it stands for **get regular expression** and is a incredibly useful tool for searching and finding.  Here I want to tell `grep` to search the ouput of the `cut` command for patterns (expressions) which match "Burrito". Whilst I am at it I can make sure my search is not case sensitive by also using the `-i` flag.

```shell 
$ cat orders-copy.tsv | cut -f 3 | grep -i "Burrito" 
```

> Steak Burrito
> 
> Steak Burrito
> 
> Chicken Burrito
> 
> Chicken Burrito
> 
> Barbacoa Burrito
> 
> Chicken Burrito
> 
> Carnitas Burrito
> 
> Chicken Burrito
> 
> Steak Burrito
> 
> Steak Burrito

Great, that's looking better. Now I just need to generate a count table. 

Here I run into a little problem. My counting command requires all things Burrito that need to be grouped together and counted (i.e., steak, chicken etc) need to be next to each other in the listed. In other words sorted. If I tried to count as it is and had for example steak, chicken, steak I will not get  steak x2 and chicken x1 but steak x1, chicken x1 and steak x 1. So what I need to do first is `sort` by name and then group (or in other words identify all the unique dish names) and count how many are in each group.  I do all of this by adding `| sort | uniq -c ` to the end of my command.

```shell 
$ cat orders-copy.tsv | cut -f 3 | grep -i "Burrito" | sort | uniq -c
```

> 91 Barbacoa Burrito
> 
> 6 Burrito
> 
> 59 Carnitas Burrito
> 
> 553 Chicken Burrito
> 
> 368 Steak Burrito
> 
> 95 Veggie Burrito

Much better! Now to sort numerically by column 1 using `| sort -k1n` 

```shell
$ cat orders-copy.tsv | cut -f 3 | grep -i "Burrito" | sort | uniq -c | sort -k1n
```

> 6 Burrito
> 
> 59 Carnitas Burrito
> 
> 91 Barbacoa Burrito
> 
> 95 Veggie Burrito   
> 
> 368 Steak Burrito
> 
> 553 Chicken Burrito 

And there we have it. Chicken burritos are the most popular dish. 

But hang on. Do I need to do this every time I want to find this information? What if I forget? Or I want to find third most popular dish? Easy. Let's just redirect the output of this one line of Bash into a new file...just like so.

```shell 
$ cat orders-copy.tsv | cut -f 3 | grep -i "Burrito" | sort | uniq -c > burritos.tsv
```

et voila, we have a new file that will contain all the information we collated for as long as we need it. 

The best part about all of this? Look at the original file. Has anything changed? 

Ok that's all very clever I hear you say. But what I really want is to look at Tacos AS WELL. I also want that information in the same file as the Burrito numbers. No problem I say. Let's just repeat the above, using "Taco" as our search term instead of "Burrito" and  **append** our burrito file with the output of this new command.

```shell 
$ cat orders-copy.tsv | cut -f 3 | grep -i "Taco" | sort | uniq -c >> burritos.tsv
```

Did you spot it? The ABSOLUTELY CRITICAL difference. This time we used `>>` instead of `>`. If I had used the latter my output from the Taco search would simply have overwritten the Burrito data.  By using `>>` I make sure to add the new data to the end of the first file.

Let's finish with the `rm` command, or remove. To get rid of burritos.tsv you can type

```shell 
$ rm burritos.tsv
```

Be warned however, there is no recycle bin, no undo, no amount of swearing, praying or IT support that can bring a file back once it has been subjected to `rm`.  This goes for folder, sub-folders and operating systems.  There is a command, which I will not spell out here, that if used whilst in `/` will wipe everything on your computer before your very eyes. So, make sure you know what it is you are deleting.

## Activity

***Using the commands you have been introduced to let me know whether salad or salsa is the most popular side dish.***

## Other Useful Commands / Information

These are some that also come in useful. I'll continue to populate as I think of them. There is also a Terminal Basics tutorial at the same sandbox, do feel free to work through that as well...it shouldn't take you long.

* If your screen is looking terribly confusing, then have a good clear out with `clear`
* If a command is running for longer than you think it should ctrl-c will kill it and return a prompt.
* In addition to man (command) most commands also come with help that can be accessed by `-h` or `--help`
* I mentioned **absolute path** at the very start - the location of a file or folder from `/`.  We did cover **relative path** but did not explicitly say that's what it was. This would be when you use `../`, for example, to begin your journey to another destination from where you are rather than from the root.

## Summary

By now you will hopefully have recognised the simple power of Bash. This is the tip of the tip of the iceberg of what it can do for you. I hope this leaves you inspired and keen to learn more. Good luck with the journey. 
