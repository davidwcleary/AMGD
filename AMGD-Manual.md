Analysing Microbial Genomic Data
================
2025-01-29

- <a href="#section" id="toc-section"></a>
- <a href="#section-1" id="toc-section-1"></a>
- <a href="#section-2" id="toc-section-2"></a>
- <a href="#section-3" id="toc-section-3"></a>
- <a href="#section-4" id="toc-section-4"></a>
- <a href="#section-5" id="toc-section-5"></a>
- <a href="#introduction" id="toc-introduction">Introduction</a>
  - <a href="#getting-started" id="toc-getting-started">Getting started</a>
  - <a href="#operating-systems-and-servers"
    id="toc-operating-systems-and-servers">Operating Systems and Servers</a>
  - <a href="#jupyter-notebook-server"
    id="toc-jupyter-notebook-server">Jupyter Notebook Server</a>
  - <a href="#bash" id="toc-bash">BASH</a>
    - <a href="#navigating-the-terminal"
      id="toc-navigating-the-terminal">Navigating the Terminal</a>
    - <a href="#history" id="toc-history">History</a>
    - <a href="#listing-directory-contents"
      id="toc-listing-directory-contents">Listing Directory Contents</a>
    - <a href="#making-directories" id="toc-making-directories">Making
      Directories</a>
      - <a href="#directory-permissions"
        id="toc-directory-permissions">Directory Permissions</a>
    - <a href="#file-manipulation" id="toc-file-manipulation">File
      Manipulation</a>
      - <a href="#peeking-at-files" id="toc-peeking-at-files">Peeking at
        Files</a>
      - <a href="#moving-and-copying-files"
        id="toc-moving-and-copying-files">Moving and Copying Files</a>
      - <a href="#merging-files" id="toc-merging-files">Merging Files</a>
      - <a href="#removing-files" id="toc-removing-files">Removing Files</a>
      - <a href="#searching-text-files" id="toc-searching-text-files">Searching
        text files</a>
      - <a href="#extracting-columns" id="toc-extracting-columns">Extracting
        Columns</a>
    - <a href="#redirecting-output" id="toc-redirecting-output">Redirecting
      Output</a>
    - <a href="#combining-commands-with-pipes"
      id="toc-combining-commands-with-pipes">Combining Commands with Pipes</a>
    - <a href="#bash-loops" id="toc-bash-loops">BASH Loops</a>
  - <a href="#using-bioinformatics-software"
    id="toc-using-bioinformatics-software">Using Bioinformatics Software</a>
  - <a href="#wgs-theory" id="toc-wgs-theory">WGS Theory</a>
  - <a href="#sequence-filetypes" id="toc-sequence-filetypes">Sequence
    Filetypes</a>
    - <a href="#fastq" id="toc-fastq">FASTQ</a>
    - <a href="#fasta" id="toc-fasta">FASTA</a>
  - <a href="#sequencing-technology"
    id="toc-sequencing-technology">Sequencing Technology</a>
    - <a href="#library-preparation" id="toc-library-preparation">Library
      Preparation</a>
  - <a href="#sequence-data-retrieval"
    id="toc-sequence-data-retrieval">Sequence Data Retrieval</a>
    - <a href="#accession-numbers" id="toc-accession-numbers">Accession
      Numbers</a>
  - <a href="#genome-assembly" id="toc-genome-assembly">Genome Assembly</a>
    - <a href="#sequence-quality" id="toc-sequence-quality">Sequence
      Quality</a>
      - <a href="#fastqc" id="toc-fastqc">FastQC</a>
    - <a href="#trimming" id="toc-trimming">Trimming</a>
      - <a href="#adapters" id="toc-adapters">Adapters</a>
      - <a href="#low-quality-sequence" id="toc-low-quality-sequence">Low
        Quality Sequence</a>
    - <a href="#assembly" id="toc-assembly">Assembly</a>
      - <a href="#spades-and-shovills" id="toc-spades-and-shovills">Spades and
        Shovills</a>
      - <a href="#managing-multiple-assemblies"
        id="toc-managing-multiple-assemblies">Managing Multiple Assemblies</a>
      - <a href="#assembly-quality" id="toc-assembly-quality">Assembly
        Quality</a>
  - <a href="#sequence-typing-and-amr"
    id="toc-sequence-typing-and-amr">Sequence Typing and AMR</a>
    - <a href="#mlst" id="toc-mlst">MLST</a>
    - <a href="#amr" id="toc-amr">AMR</a>
  - <a href="#annotation" id="toc-annotation">Annotation</a>
    - <a href="#prokka" id="toc-prokka">Prokka</a>
    - <a href="#bakta" id="toc-bakta">Bakta</a>
    - <a href="#annotation-loops" id="toc-annotation-loops">Annotation
      Loops</a>
  - <a href="#mappingalignment"
    id="toc-mappingalignment">Mapping/Alignment</a>
  - <a href="#core-and-pangenomes" id="toc-core-and-pangenomes">Core and
    Pangenomes</a>
    - <a href="#panaroo" id="toc-panaroo">Panaroo</a>
  - <a href="#phylogeny" id="toc-phylogeny">Phylogeny</a>
    - <a href="#generating-phylogenies"
      id="toc-generating-phylogenies">Generating Phylogenies</a>
    - <a href="#mash" id="toc-mash">MASH</a>
    - <a href="#parsnp" id="toc-parsnp">ParSNP</a>
    - <a href="#core-gene-alignments" id="toc-core-gene-alignments">Core Gene
      Alignments</a>
    - <a href="#removing-recombination"
      id="toc-removing-recombination">Removing Recombination</a>
    - <a href="#identifying-variable-sites"
      id="toc-identifying-variable-sites">Identifying Variable Sites</a>
    - <a href="#raxml" id="toc-raxml">RAxML</a>
    - <a href="#fasttree" id="toc-fasttree">FastTree</a>
    - <a href="#visualising-phylogenies"
      id="toc-visualising-phylogenies">Visualising Phylogenies</a>
  - <a href="#snp-distance-matrices" id="toc-snp-distance-matrices">SNP
    Distance Matrices</a>
- <a href="#wrapping-up" id="toc-wrapping-up">Wrapping Up</a>
- <a href="#bash-cheat-sheet" id="toc-bash-cheat-sheet">BASH Cheat
  Sheet</a>
- <a href="#appendix-a-flow-chart-of-methods-covered"
  id="toc-appendix-a-flow-chart-of-methods-covered">Appendix A Flow-chart
  of Methods Covered</a>
- <a href="#appendix-b-day-one" id="toc-appendix-b-day-one">Appendix B Day
  One</a>
  - <a href="#practical-one" id="toc-practical-one">Practical One</a>
    - <a href="#files" id="toc-files">Files:</a>
    - <a href="#output" id="toc-output">Output:</a>
  - <a href="#practical-two" id="toc-practical-two">Practical Two</a>
- <a href="#appendix-c-day-two" id="toc-appendix-c-day-two">Appendix C Day
  Two</a>
  - <a href="#download-data" id="toc-download-data">Download Data</a>
  - <a href="#cutadapt" id="toc-cutadapt">Cutadapt</a>
  - <a href="#sickle" id="toc-sickle">Sickle</a>
  - <a href="#shovill-assembly" id="toc-shovill-assembly">Shovill
    Assembly</a>
  - <a href="#assembly-qc" id="toc-assembly-qc">Assembly QC</a>
    - <a href="#quast-and-multiqc" id="toc-quast-and-multiqc">Quast and
      MultiQC</a>
    - <a href="#centrifuge" id="toc-centrifuge">Centrifuge</a>
- <a href="#appendix-d-day-three" id="toc-appendix-d-day-three">Appendix D
  Day Three</a>
  - <a href="#mlst-1" id="toc-mlst-1">MLST</a>
  - <a href="#abricate" id="toc-abricate">Abricate</a>
  - <a href="#prokka-1" id="toc-prokka-1">Prokka</a>
  - <a href="#mapping-and-alignment" id="toc-mapping-and-alignment">Mapping
    and Alignment</a>
- <a href="#appendix-e-day-four" id="toc-appendix-e-day-four">Appendix E
  Day Four</a>
  - <a href="#phylogeny-1" id="toc-phylogeny-1">Phylogeny</a>
    - <a href="#minhash-mash" id="toc-minhash-mash">MinhASH (MASH)</a>
    - <a href="#parsnp-1" id="toc-parsnp-1">ParSNP</a>
    - <a href="#raxml-1" id="toc-raxml-1">RAxML</a>

### 

### 

### 

### 

### 

### 

# Introduction

Welcome to the Analysing Microbial Genomic Data (AMGD) course.

This guide was written to help you gain the skills necessary to analyse
your own sequence data and begin the journey to becoming a better
bioinformatician.

The items contained within this booklet will be explained in greater
depth during the course, but we hope that this document will serve as a
handy companion piece for your learning.

## Getting started

The booklet is formatted to allow you to easily spot sections of code.
Here’s an example:

``` bash
for f in *.fasta; do echo $f; done
```

It may look alien now, but by the end of the course you’ll be surprised
at how easy it is to write your own code to accomplish a variety of
tasks.

You will have received an email with a link to a Jupyter Notebook
Server. This link will allow you to access the environment in which you
will be playing with all the fantastic bioinformatics tools and programs
we will go through.

## Operating Systems and Servers

A quick note on why you need access to a server. Most bioinformatics
software is written for Unix systems (e.g., Linux, MacOS). As everyone
has a different laptop, operating system, and available processing
power, we often use servers to host analysis platforms.

A server is simply a computer that is accessed remotely (e.g., via the
internet). It is a bit like hooking up your laptop to a display - the
display shows all the information, but it’s your laptop that’s doing the
heavy lifting. Similarly, when we connect to a server, the information
is shown on the computer in front of us, but all the work is done
remotely on the machine we are connected to.

![A simple example of connecting to a server](servers.png)

Depending on your operating system, connecting to a server can be as
simple as opening a program called Terminal on Linux or MacOS, or by
downloading a software package that allows you to perform the same
functions if you are using Windows (putty).

Once this course is over you may find that you need to access your own
server. This might be your University’s High-Performance Compute (HPC)
cluster or perhaps the resources provided by the Cloud Infrastructure
for Microbial Informatics (CLIMB, <http://www.climb.ac.uk>) - who are
incidentally providing the resource behind the Jupyter Notebook Servers
you will be using during this course. The software you might need for
this is not something we cover.

## Jupyter Notebook Server

Once you open the link for your Jupyter notebook server you will see the
‘launcher’ window as shown below.

![Our Jupyter Notebook System](jupyter.png)

The key features here are that you can start a terminal (by clicking on
the icon), as well as opening a text file or, for the adventurous, an R,
python or markdown file. For now, all you need to worry about is the
terminal icon which will launch a terminal in a new tab as shown.

To save your workspace, including the files that you make (which you can
see in the left-hand panel), simply navigate to ‘File’ \> ‘Save
Workspace As’. That will mean that the server will remain as it is, even
if you close your web browser window.

## BASH

**B**ourne-**A**gain **SH**ell. This is the default command language
used to interact with Unix and allows you to accomplish everything you
would normally do with a mouse via written commands.

Ahead of the course, you will have been advised to complete the Command
Line Basics tutorial to gain some familiarity with BASH. The information
in that tutorial will remain available to you.

### Navigating the Terminal

When first starting out, the biggest barrier to bioinformatics is
gaining proficiency within the terminal so it’s worth spending some time
going over some of the basics.

When you first log in to your server, you will (probably) be in your
*username* directory. Let’s remind ourselves what the directory
structure might look like (your environment may look different!):

![Directory Structure](systempic.png)

A directory is equivalent to a folder you would double click on to
enter. To find out which directory we are currently in, use the
**p**rint **w**orking **d**irectory command, `pwd`:

``` bash
pwd
```

As soon as you login in using the above example it would say you were in

    /home/username 

Let’s say we want to access the data directory in the example above. We
would want to **c**hange our **d**irectory:

``` bash
cd data
```

Changing directory, or interacting with anything in the terminal, is
based on your current location. Imagine you are several folders deep
into a directory:

``` bash
pwd
```

    /username/data/raw/

If we wanted to go to the sequence folder, we can accomplish it in
several ways.

We can pass `cd` an absolute path, which is the entire path to our
directory:

``` bash
cd /data/sequence/
```

But that’s quite long winded, and the more folders you have the more
complicated it gets. That’s where the tilde `~` keystroke comes in. The
tilde is interpreted by bash as: `/home/user/` - for example let’s
assume there is a folder called course-files in shared-team. To get
there from raw all you need is:

``` bash
cd ~/shared-team/course-files
```

We can also use positional references to move back in the directory
structure. To move back a single directory, we would pass `cd` two full
stops.

``` bash
cd ..
```

Again, assuming we are in raw, then this would take us back to the data
folder. To get back to username from raw we would pass it two
double-full-stops separated by slashes i.e., we want to go back two
times:

``` bash
cd ../../
```

Obviously, this is not ideal if you are trying to go many times further
up the directory structure. Sometimes `~` or absolute paths will be much
simpler:

If you make a mistake when writing your path, `cd` won’t be able to find
the directory and you will get an error.

Luckily, there is an easy way to verify paths, and it will save you time
in the process. When typing a path, you can press the *TAB* key to
automatically complete what you are writing.

*TAB* will only complete if it can find something uniquely matching your
input. For example, if you had two folders called **Dogs** and
**Doors**, and pressed *TAB* after typing `cd do`, nothing would happen.
This is because you need a capital letter, **D**.

If you pressed *TAB* after typing `cd Do`, again nothing would happen.
This is because there are multiple matches to that string i.e., *TAB*
does not know whether you mean **Dogs** or **Doors**. You can press Tab
again to get a list of those matches.

Pressing *TAB* after `cd Doo` would automatically complete your path to:
`cd Doors/` verifying that it is correct and that the `cd` operation
would now complete.

### History

You can easily access your previous commands (your **History**) by
pressing the up-arrow key. This will allow you to step back
command-by-command and quickly rerun things or check what you have
written.

You can also search for a command you have entered previously by
pressing *Control (ctrl) and R*. This will activate reverse search
mode - simply type in part of the command you are trying to find, and
you will begin to see matches. To cycle through search results, press
*ctrl-R* again. When you have found the one you want, you can press the
right arrow key, or Enter.

To get a full list of your previous commands, you can also type:

``` bash
history
```

### Listing Directory Contents

To see a list of files within a directory, we use:

``` bash
ls
```

This will return a column bound list of all visible files. We can also
ask `ls` to give us extra information, or format it slightly differently
by providing it with extra options, called flags.

A flag is typically denoted by a single (-) or double hyphen (–)
followed by a letter or a word. If we wanted to get a list of files in a
single column, with additional information like file sizes, we’d pass
`ls` the `-l` flag:

``` bash
ls -l
```

If you try it out, you will notice the file sizes look strange. That’s
because they’re given in bytes.

We can ask `ls` to provide human readable file sizes (i.e., MB, GB) with
the `-h` flag. We can either provide `ls` with two flags separately, or
as a combined flag. Note that a lot of programs are not compatible with
combined flags.

``` bash
ls -l

ls -lh
```

Remember that we can bring up the manual for `ls` or similar commands
using `man ls`. For manuals with multiple pages we can use the
**SPACEBAR** to scroll through. To exit a manual hit **Q** on your
keyboard.

### Making Directories

To make a new directory, we use `mkdir`, followed by your desired
directory name:

``` bash
mkdir directory_name
```

In this example the new directory will be made wherever we are in our
directory structure.

#### Directory Permissions

When you list the contents of a directory you will find some useful
information relating to who can do what with the files present. The key
information is held within the following column structure:

    1  234  567 8910
    -  rwx  r-x r-x

In column 1, **d** (or **-**) denotes folder (or file).

In this example **234** tells us the owner has read, write and
executable permissions, **567** tells us that the group has read and
executable but not write, and finally that these permissions, in this
example are the same for anyone else **8910**.

### File Manipulation

#### Peeking at Files

To check the contents of a file, you can view the first or last few
lines using `head` or `tail`. You can control the number of lines using
a flag, `-n` followed by a number. The default number of lines is 10.

``` bash
head myfile.txt
tail -n 40 myfile.txt
```

If you want to look at the whole file, we need to concatenate it, using
cat.

``` bash
cat myfile.txt
```

You can also use so called *pager* programs like `less` or `more`.

``` bash
less myfile.txt
more myfile.txt
```

To scroll through the file contents which are printed to the terminal
screen use the **SPACEBAR** and to quit simply hit **Q** on your
keyboard. If in doubt about which one to use, just remember that simple
maxim “less is more” and use `less`.

#### Moving and Copying Files

If we want to move or copy a file, we use `mv` or `cp` respectively. The
syntax for these commands uses the original file location, followed by
the destination. For example:

``` bash
mv myfile.txt ~/Documents/myfile.txt 

cp myfile.txt myfilecopy.txt
```

We also use `mv` if we want to rename a file:

``` bash
mv myfile.txt newfilename.txt
```

Note that moving a file is destructive - it removes any reference to the
original file. Copying leaves the original in place.

#### Merging Files

Another useful command is `paste`. This allows us to merge files, by
column. In the following example we have two files, A and B, which we
would like to merge into a third file, C. The caveat in this example is
that we know the orders in column A and column B make sense to us.

``` bash
paste -d "," fileA fileB > fileC
```

You’ll remember the `>` redirect from the pre-course learning but this
is saying we want the output of `paste` to go into fileC. The other
important flag we have included is `-d ","`. Here we are saying that we
want the column delimiter to be a comma in fileC.

#### Removing Files

If we want to remove a file, we use `rm`. For example, to remove a file
called myfile.txt we would do:

``` bash
rm myfile.txt
```

If you try to remove a directory using the same syntax, you will get the
following error:

    rm: cannot remove ‘mydirectory/’: Is a directory

This is for your own protection and prevents accidental deleting of
entire folders worth of precious data. To remove a directory, we must
pass `rm` the `-r` flag, which means remove recursively.

``` bash
rm -r mydirectory/
```

Note that when you remove something, the reference to the file in the
hard drive is immediately and irrevocably destroyed. Use `rm` with
caution!

#### Searching text files

If you want to find a specific search pattern (called a string) in a
text file, you can use `grep` (**g**lobally search a **r**egular
**e**xpression and **p**rint matching lines). The basic grep syntax is
the string you are looking for followed by the file in which you want to
search.

Let’s assume we have a file called shoppinglist.txt, that looks like
this:

    Item    Quantity
    Apples    2
    Bananas   6
    Eggs      12
    Bread     1

If we wanted to check how many apples we need to buy, we’d do:

``` bash
grep “Apples” shoppinglist.txt
```

    Apples 2

Useful flags for \`grep’ include:

    -c count
    -n print the line number
    -i case insensitive
    -A n number of lines after
    -B n number of lines before

As you can see, grep returns the line that the search pattern is found
in. It also matches upper and lower cases by default. `grep` is a very
powerful and versatile tool and has a lot of options to help you find
exactly what you’re looking for. There could be an entire booklet
dedicated to grep functionality, but if you want to dig into it further
you can check the help with the `grep --help` flag.

#### Extracting Columns

Working with the same text example as above, if we wanted to simply
return a list of all items we want, we would want to extract the first
column. We can do this using `cut`. The syntax for `cut` uses the flag
`-f` for field, followed by an integer specifying which column we want.

``` bash
cut -f1 shoppinglist.txt
```

We can specify which column delimiter we want to use to identify the
fields using `-d`. If our list was comma separated for sample:

``` bash
cut -f1 -d "," shoppinglist.txt
```

### Redirecting Output

Whenever we call a command, the output we see is directed to what’s
referred to as **ST**andard **OUT**put (STDOUT). This is simply output
printed in the terminal window.

We can redirect output from STDOUT to other places, for example a text
file. If we wanted to create a file including only the first column of
our shopping list, we would use the `>` symbol to redirect STDOUT into
that new file.

``` bash
cut -f1 shoppinglist.txt > items.txt
```

The `>` symbol can be used with any program that prints its output to
STDOUT. This includes the previously discussed `cat`. You can use cat to
merge several files - let’s say we had two shopping lists and wanted to
merge them into one file, we would use:

``` bash
cat shoppinglist.txt shoppinglist2.txt > newlist.txt
```

Note that this will overwrite any existing file called newlist.txt - a
single `>` sign is destructive. If we wanted to append something to an
existing file, we’d use `>>`.

We’ve just remembered our friend also sent a list of items they wanted.
Let’s add it to our new list.

``` bash
cat friendslist.txt >> newlist.txt
```

newlist.txt now contains all items from shoppinglist, shoppinglist2 and
friendslist.

### Combining Commands with Pipes

We can use the output of one command for the input of another. This is
called piping and uses the very pipelike symbol `|`. This symbol is
located on the backwards slash key, or on its own key above Tab.

If we wanted to find out how many apples we intended to buy, we could
first use `grep` to find the line containing apples, and then use `cut`
to return the second column. To do this, we’d need to pipe the output
from `grep` to use as input for `cut`:

``` bash
grep apples shoppinglist.txt | cut -f2
```

Note that this time I’m not supplying a filename to `cut.` Instead,
`cut` is now using the output piped to it from `grep.` With pipes you
can achieve very complex functions in a single command line, and it is a
very powerful tool for parsing through files.

### BASH Loops

So far, we have been working through examples where we execute commands
one at a time, on a single file. In day-to-day bioinformatics, you will
often be dealing with 10s to 1000s of files that need to be analysed in
the same way. Rather than sitting and writing out 1000s of commands, we
can make BASH do the heavy lifting by using loops.

There are several types of loops (while, until, for). One of the most
useful is the for loop. Here is how it works:

    for 
    # the start of our loop

    for i in
    # for something in

    for i in list of things (variables)
    # for each something in our list of things (variables)

    for i in variables; 
      do something on it;
    # go through that list of variables (things) and do something on it

    for i in variables; 
      do something on it;
    done
    # complete when each variable has had that thing done on it.

We can demonstrate this using `echo` to just print each variable to the
terminal screen.

``` bash
for i in a b c d; 
  do echo $i;
done
```

    a
    b
    c
    d

Now, for a slightly more ‘real-world’ version. Let’s say we have a list
of files named file_1.txt, file_2.txt, file_3.txt.

If we wanted to remove the ‘file\_’ prefix, we could either sit and
write:

``` bash
mv file_1.txt 1.txt
mv file_2.txt 2.txt
mv file_3.txt 3.txt
```

Or we could write a loop to do it:

``` bash
for f in *.txt; do mv $f ${f/file_/}; done
```

Let’s break that down. The first part is our loop type `for`.

We are then setting a name for our variable (f). This could be anything,
for example:

``` bash
for amgd in *.txt; do mv $amgd ${amgd/ file_/}; done
```

Now that we’ve set up our variable name, we need to tell BASH what our
variable should contain. We do this using what is referred to as a
wildcard. The asterix (\*) is a type of wildcard that means ‘anything’.
Using this example, we are getting all files with the .txt extension in
our current working directory.

If we had extra files in our directory that we did not want to include
in our variable list, for example:

    notes_1.txt 
    notes_2.txt 
    notes 3.txt

we could change our wildcard accordingly:

``` bash
for f in file_*.txt; do mv $f ${f/file_/}; done
```

This is saying use everything with the **file\_** prefix and **.txt**
extension, with anything in between those two things. This would also
include a hypothetical file called file_123_apples_bananas_oranges.txt,
because it still has the file\_ prefix and .txt extension.

If we wanted to check what our variable is selecting, we can ask BASH to
output a list of our variables by using echo like so:

``` bash
for f in file_*.txt; do echo $f; done
```

This is the first part of our loop completed, we have specified the loop
type (for), named our variable (f), and populated our variable with
items we want to do some work on (in file\_\*.txt).

We separate out this set-up section with a semi colon, telling bash that
we’re ready for the next bit - the command.

We have to be bossy with BASH and tell it to do what we want. `do` lets
the terminal know to execute the next word as a command - in our case,
`mv`.

Again, with the `mv` syntax we have our command, followed by the
original file and the destination file. Here, in place of the original
file, we’re referring back to the name of our variable: f. We use a
dollar sign **\$** before f to let BASH know that we are referring to a
variable and not a word.

The next part employs braces - or curly brackets ({}). This allows us to
edit our variable. In our example, we are essentially doing something
similar to ‘find and replace’. We are finding all instances ‘file\_’ and
replacing it with ‘ ‘ nothing.

The syntax for curly brackets is to use a dollar sign before the first
open brace, and the variable name just after the first brace `${f`. We
then use a forward slash to define what string we would like to replace
`/file_`.

We separate our ‘find’ and ‘replace’ sections using another forward
slash . Here, we are choosing to replace with nothing, but if we wanted
to replace `file_` with `item_` we could do the following instead:

``` bash
for f in file_*.txt; do mv $f ${f/file_/item_}; done
```

Now we have finished our find and replace, we close the expression with
a close brace `}`. We have now finished the command section, so to close
the section we again use a semi colon `;`. Our loop is now finished, and
to tell BASH that, we simply end our loop with `done`. This tells BASH
to stop interpreting what we’ve entered and get on with the work.

If we wanted to check what commands our loop will run before we actually
execute them, we can again use `echo`. Here, we need to put the command
we are running in speech marks, and ask BASH to echo that command:

``` bash
for f in file_*.txt; do echo “mv $f ${f/ file_/}”; done 
```

…and this is what we would see:

    mv file_1.txt 1.txt 
    mv file_2.txt 2.txt 
    mv file_3.txt 3.txt

We are now asking BASH to `do echo`, instead of `mv`, so our terminal
will repeat our list of commands back to us. If it all looks okay, we
can remove the echo and speech marks and let BASH do its thing.

Loops could have 20 booklets dedicated to their functionality - even
after several years of experience with BASH you can still find newer and
neater ways of accomplishing a certain task.

The best way to learn how to use loops is trial and error. Just make
sure you always `echo` everything before you execute it.

## Using Bioinformatics Software

The software you’ll use will be written in different languages, have
different dependencies (programs that the software relies on), and vary
in their installation and usage difficulty.

This cannot be overstated. The number one skill you need to learn to
become a bioinformatician is to be able to read and comprehend software
manuals. You may have heard the phrase RTFM (**Read The Flipping
Manual**). If you run into any sort of problem, the number one step is
to RTFM.

Manuals will be available on the software’s website, or if hosted on a
popular service like GitHub, you will find them there.

Step one of running a new program is reading the manual in its entirety.
This avoids a lot of mistakes or wasted compute time because you forgot
to add in a useful optional flag that was three lines down from the
‘Quick Start’.

Programs often include a help section that is accessible via the command
line. The way to access these vary, but you can either just type the
name of the program, or the program followed by a flag (e.g. `-h`
`-help` `--help`). This is very handy when returning to a program to
refresh your memory on what the different flags are and what they do.

Installing software is the least fun or rewarding part of
bioinformatics. Some pieces of software have hundreds of dependencies,
each with their own dependencies, and some requiring outdated versions
that are deeply buried somewhere.

Luckily, everyone hates this. So, some kind people have developed tools
to make things a lot easier - these can be referred to as package
managers.

Package managers contain databases of recipes that allow the easy
download and installation of a range of tools. The two most famous ones
are Brew (homebrew), and Conda (Anaconda).

The discussion of these package managers is beyond the scope of this
booklet, but I’d recommend becoming familiar with one. I personally
prefer conda (but really mamba) - it seems to be the most ubiquitously
supported, and aside from some very long install times, tends to handle
installations with ease.

Sadly, not every package is available for installation this way, so
always RTFM and check the notes on installation for help. You may see
references to PIP, which is a package manager specifically for Python.
Others require the use of Make. Sometimes you can download an executable
file called a binary file.

If you don’t already, you will soon hate installation.

## WGS Theory

## Sequence Filetypes

There are two file types that you will use on this course - .fastq.gz
(or fastq) and .fasta. It’s worth outlining the difference before we get
into how they are generated.

### FASTQ

Raw sequence data (reads) are typically provided in the FASTQ format.
This is a standardised format that is composed of four lines of
information. Here’s what one read looks like in the fastq format:

    @SEQ_ID
    GATTTGGGGTTCAAAGCAGTATCGATCAAATA 
    +
    !’’*((((***+))%%%++)(%%%%).1***-

Line 1 contains the ‘@’ prefix, and contains the name/title/description
of the sequence. This will for example be the read ID generated by your
sequencing device, and the name of your sample.

Line 2 is the raw sequence data – the individual nucleotides produced
during basecalling.

Line 3 contains the ‘+’ prefix – it’s not really used in modern
sequencing but may contain a repeat of line name/title/description.

Line 4 is a little more complex – it is an ASCII encoded quality score.
It contains information on the quality of the basecall that is in the
same position on line two.

FASTQ files typically contain all reads relating to a sequenced sample.
For example, if we had 4000 reads, we would have 4 x 4000 = 16,000 lines
of text. This can be used to our advantage – if we wanted to discover
how many reads a file contains, we can use word count `wc` to find out:

``` bash
wc -l myreads.fastq
```

When we receive sequence data, it will often be ‘paired-end’, meaning
there is a fastq file for all reads in the 5’ - 3’ orientation, and a
separate file for reads in the 3’ - 5’ orientation. This is because
Illumina platforms rely on sequencing by synthesis, whereby single
stranded DNA is complemented during the process. You will typically
receive files with the suffixes ’\_R1’, ’\_R2’ or ’\_1’, ’\_2’ to
delineate between the two. For example:

    myreads_R1.fastq myreads_R2.fastq

Because of the density of information stored in these files, they can be
very large, but that can be mitigated. As reads are composed entirely of
ASCII characters, their filesizes can be dramatically reduced using
compression software. The most common program used to compress FASTQ
files is g-zip. WGS reads will often come with the ‘.gz’ extension,
indicating it has been compressed to save hard drive space and increase
transfer speeds. You can compress your own files using gzip:

``` bash
gzip myreads.fastq
```

This will create a gzipped file called ‘myreads.fastq. gz’ in your
working directory. You can also increase or decrease the level of
compression by passing a numerical flag to gzip:

``` bash
gzip -1 myreads.fastq gzip -9 myreads.fastq
```

-9 is the highest level of compression – it will produce the smallest
file sizes, but take the longest time to compress and decompress. -1 is
the lowest level, and has the opposite characteristics.

To decompress a gzipped file, we simply use:

``` bash
gunzip myreads.fastq.gz
```

Most programs are built to handle gzipped files, so it’s probably worth
leaving them compressed to save precious hard drive space!

### FASTA

FASTA files are another standardised format, and are similar to FASTQ
files, but consist of only two lines:

    >ID
    ACTGACTGTTAGGAATTGGAACCCTTGGCAGA

Line 1 contains the “\>” prefix, which contains the title/ description
of the sequence beneath. Line 2 contains sequence data.

It’s worth noting that there is no quality information encoded in the
FASTA format, which is the main difference between the two formats.
Typically, fasta files are used for assemblies, with each contig
(i.e. assembled stretch of DNA) defined by the ‘\>’ character. Here’s
what an assembly may look like:

    > contig_1
    ATCAGCTAGCATGACTGACTGACTGGGCCAACA
    > contig_2
    CGTAGCTAGTAGCTGAGCGATCGATCG
    ...
    > contig_n
    ACGTCAACAGCGCTCGGCCGCATCGCATC

Reads can also be converted to the .fasta format for particular
applications, but this isn’t very common.

## Sequencing Technology

To understand sequence data analysis, it’s useful to know a bit of
background about how DNA sequencing works. There are currently two forms
of complementary technology in the **W**hole **G**enome **S**equencing
(WGS) space – long and short read technology.

Short read technology (dubbed **N**ext **G**eneration **S**equencing, or
NGS) revolutionised the sequencing industry, and gave birth to the field
of bioinformatics. Dominated by Illumina, short read sequencing is cheap
(\~£50 a genome), accurate, and has a high throughput, meaning many
samples can be analysed in one go. Illumina reads range from 50-300 bp
in length.

Illumina uses what they call ‘sequencing by synthesis’ in which prepared
libraries are added to a flowcell containing oligonucleotides that
capture and bind single stranded DNA. Nucleotides with a fluorophore (a
light excitable molecule) attached are then sequentially washed across
the flowcell along with a polymerase that incorporates bases that are
complimentary to the bound strand. After each nucleotide addition, a set
of lasers are passed over the flowcell – any base incorporation results
in a light signal that is captured by a camera which is then converted
into a nucleotide sequence based on which nucleotide was added.

Illumina machines are expensive (hundreds of thousands of pounds), and
the kits are only cost effective when loading several samples onto a
single run - referred to as multiplexing. They are also huge and must be
recalibrated when moved.

At the time of writing, long read technology (sometimes referred to as
**T**hird **G**eneration **S**equencing or TGS) is currently serviced by
two main companies, PacBio and Oxford Nanopore. Long read technology
provides several advantages involving resolving structural variations
and increasing the accuracy and resolution of genomic assembly. It has
recently been used to sequence a *P. falciparum* chromosome from
telomere to telomere – a feat that was previously impossible.

PacBio has been in the long-read market for some time, and historically
produced large and costly machines (although in recent years that has
been changing). It has its advantages – particularly in generating
reference quality genomes – but it is largely run using a business model
similar to Illumina.

Oxford Nanopore can be described as a technology disruptor. They have
democratised long read sequencing by producing a small, cheap (\~£1000)
sequencing device, that is capable of producing reads that are as long
as the DNA you extract. The current record is in the range of megabases.
Powered by a USB connection, their devices can be used in the field and
have notoriously been used to sequence DNA in space.

### Library Preparation

Prior to sequencing, extracted DNA must be prepared for sequencing by
altering it into a format that is compatible with the sequencing device.
Illumina produce helpful videos and documentation on their library prep
workflows, and I’d recommend looking.

Briefly, Illumina library preps involve taking your DNA and chopping it
up into small fragments. Adapters are ligated to the fragmented DNA by
PCR or enzyme, which allow the DNA library to bind to the complimentary
oligonucleotides (DNA molecules) on the flowcell. Finally, barcodes are
also attached to the library, which are unique sequences of DNA that
allow you to computationally detangle reads produced on the same run –
this allows you to load 100s of samples with unique barcodes that can
later be ‘demultiplexed’.

## Sequence Data Retrieval

Storing data is a huge problem - you often hear that more than 500 hours
of video content is uploaded to YouTube every minute. And we are also
producing more and more sequence data year upon year. A single MinION
run can produce 100’s of Gbs of output files, which is unrealistic for
researchers to archive.

Luckily, large scientific initiatives have created databases with free
storage and access to house all of this data. These databases are hosted
by the National Centre for Biotechnology Information (NCBI) and European
Nucleotide Archive (ENA). The databases are for all intents and purposes
the same and they are synchronised frequently, but interacting with each
is slightly different. NCBI’s read hosting platform is called the Short
Read Archive (SRA).

Here’s a chart of data available by year - the Y axis is bases!

![The tsunami of data](data.png)

### Accession Numbers

Sequence data is archived and referenced using an accession number (the
number you use to access it).

The structure of the NCBI and ENA databases can get confusing, but the
major categories are:

Bioproject - a collection of sequence data that pertains to a specific
research goal or effort. This is ideally all data from a single study
but can be found to contain samples from an individual sequencing run.
Bioproject accession numbers are prefixed with PRJNA, followed by a
unique number.

Biosample - a sample record that contains metadata (additional
information) and important records, such as isolate ID, date of
collection, disease type, sample type etc. Biosample accession numbers
are prefixed with SAM, followed by a unique number.

Reads - the individual sequence data files relating to a given
Biosample, which are subsequently collected into a Bioproject. Read
files have slightly different prefixes. If you submit your data to the
ENA, it will be prefixed with ER followed by a letter, then a unique
number (e.g., ERX071055. Data submitted to the SRA would be prefixed
with SR instead, e.g., SRX071055).

Again, these databases are periodically synchronised, so the only things
that are different when submitting to either database is the prefix.

You can also retrieve sequence data from either database. I find it
slightly easier to work with the SRA, as they have a command line tool
that makes it simple to pull a single read file, or an entire
bioproject. Note that your transfer rate may be reduced when downloading
from the SRA because their servers are geographically further from the
UK than the ENA’s servers, so if you’re downloading 1000’s of files you
may want to look at the ENA instead.

The first step is to identify the accession number of the genome you
want to download. Open access of data is still sadly not a standard that
everyone adheres to, however several journals now mandate that all
sequence data must be publicly available. When reading a paper, there is
sometimes a dedicated section for listing the accession number of files.
You may also find them in a supplementary material.

To download read data from the SRA, you can use the `sra-toolkit`. This
is a suite of files written by NCBI to permit command line interaction
with the SRA database. The specific tool we need is the aptly named
`fastq-dump`.

To download paired end data from accession number SRA012345 we would
use:

``` bash
fastq-dump --split-files SRA012345
```

This would download the data in our current working directory and split
them in to reads 1 and 2. Easy!

Now `fastq-dump` might be a bit slow, so there is a faster method.

``` bash
parallel-fastq-dump --sra-id SRR11070866 --threads 8 --outdir fastqs/ --split-files --gzip
```

## Genome Assembly

The first part of the library preparation process is key to
understanding assembly. We have taken an organism with a genome
containing millions of base pairs and chopped it up into short
fragments. To assemble them, we need to piece those fragments back
together.

Assembling a genome from scratch is referred to as *de novo* (Latin for
of new) assembly. A popular method for *de novo* assembly utilises De
Bruijn graphs, which is the basis of the de facto assembly software
SPAdes (Saint Petersburg Assembler).

The maths is … complex. But the theory isn’t too convoluted – first,
SPAdes produces k-mers (fragments of DNA of k length) from our reads
that overlap by a single base pair. It treats these as ‘nodes’, and then
tries to find unique k-mers that form ‘bridges’ i.e., that connect two
nodes together. When a node is successfully bridged, they are joined to
form a ‘contig’. A contig is a contiguous stretch of assembled DNA. From
short read sequencing, an \*E. coli8 genome may typically have between
50-200 contigs, meaning the best approximation of its chromosome comes
in a collection of between 50 and 200 chunks.

It’s important to note that *de novo* may as well mean ‘closest guess’.
While the mathematics used to assemble the genome are sound, it’s not an
exact or infallible process. Long reads can be used alongside short
reads for hybrid assembly, and allows easier bridging of nodes. If you
imagine a book being shredded, trying to piece together the paper shreds
would be a nightmare, but if you had fully intact chapters to compare
those shreds to it would make things a lot easier.

### Sequence Quality

After a sequencing run, or perhaps after downloading public reads from
the SRA/ENA, it’s always recommended to do some Quality Control (QC).
This involves examining the reads for various issues like bad quality or
truncated length. There’s a long list of things that can go wrong with
DNA sequencing, and if you don’t QC your data you are setting yourself
up for trouble.

When a base is sequenced, it is assigned a Q-score (quality score) based
on how confident the basecaller is that it is correct. Q-scores are
provided in the Phred numerical format, which is a simple way of
expressing the chance that a base call is correct. Here is a breakdown
of what the Phred scores refer to:

![Phred Quality Scores](phred.png)

Illumina sequencing typically produces sequences with a Q-score of 30+
(99.9% accuracy). Nanopore data is slightly more complex and depends on
the way in which the data is sequenced. However, using something call
duplex basecalling and the latest Flow cells (10.4.1) you can achieve
Q30.

Because integers aren’t fixed in length, it wouldn’t be possible to
positionally encode quality using numbers.

Instead, the FASTQ format uses ASCII characters (another standardised
format for character types) in their place. Thankfully, there are
programs to interpret the ASCII characters, so don’t worry about this
too much.

#### FastQC

There are many programs that make QC a breeze. One of the most
well-known is `FastQC`, which generates easy to use html reports
containing several things that can help you identify problematic data.
Running FastQC is simple. First, we create a directory for our output,
and then point `FastQC` to your forward and reverse reads:

``` bash
mkdir fastqc
```

``` bash
fastqc Sample01_R1.fastq.gz Sample01_R2.fastq.gz -o fastqc
```

This will generate a report file in html format for each read you
specify. They will be named according to the read file name (e.g.,
`Sample01_R1.html`). To read the report you can either right click on
the file in the file browser window and open in new browser tab or, even
better, open with HTML Viewer which opens it for you in another tab in
the Jupyter notebook.

Note: If you are doing this somewhere else chances are you’ll need to
copy the HTML to your local computer. On windows you can do this with
WinSCP by connecting to your server, navigating to the FastQC output
directory, and double clicking the output .html. Similarly, on Mac you
can use Cyber Duck. You can also use `scp` to copy files directly from
the command line (Appendix 3).

The output html contains several graphs that chart various metrics.
We’ll be looking at FastQC in depth during the course, but two of the
main graphs of importance are the ‘Per base sequence quality’ and
‘Adapter content’.

The latter allows you to identify whether any of the adapters used to
prepare libraries for sequencing are still present in the reads.
Typically, these will be trimmed from your files by the basecaller, but
if for some reason they aren’t they will make their way into the final
assembly. The SRA/ENA are plagued by assemblies with adapter content -
don’t be one of those people who forget to QC!

The per base sequence quality chart graphs the distribution of quality
scores across the length of your reads. Sometimes, with Illumina
sequencing, you see a declining base quality towards the end of the
read. Here are examples of a good and bad quality distribution:

![FastQC output - Good data. Taken from
<https://www.bioinformatics.babraham.ac.uk/projects/fastqc/>](good-fastq.png)

![FastQC output - Bad data. Taken from
<https://www.bioinformatics.babraham.ac.uk/projects/fastqc/>](bad-fastq.png)

### Trimming

So, you’ve been responsible and QC’ed your data, and sadly have
discovered that there’s adapter content and a declining base quality
towards the end of your reads. Whilst not ideal, all is not lost!

You can trim your data to remove those pesky adapters and mitigate the
declining base quality by intelligently removing some of the troublesome
sections. There’s a long list of programs that can accomplish these
tasks, some programs like `trimmomatic` can be used to do both.

The `trimmomatic` command is quite complex, so here we will look at
`cutadapt` to remove adapters, and `sickle` to trim your reads based on
quality.

#### Adapters

For adapters, `cutadapt` is highly configurable and very simple to
implement. Depending on what sequencing methodology and library prep kit
you have used, you may have different adapter sequences present in your
read. Illumina has an easily accessible list of their adapter sequences
online - simply identify the adapter you want to trim - for this example
ACTGAC for the forward read and ACTCTG for the reverse read - and then
implement `cutadapt` like so:

``` bash
cutadapt 
  -a ACTGAC 
  -A ACTCTG 
  -o Sample01_R1_cutadapt.fastq.gz 
  -p Sample01_R2_cutadapt.fastq.gz 
  Sample01_R1.fastq.gz 
  Sample0_R2.fastq.gz
```

Here, we supply the forward adapter with the `-a` flag, and the reverse
adapter with the `-A` flag. Next, we identify where we want to output
our processed reads with `-o` for the forward and `-p` for the reverse.
Finally, we point `cutadapt` to our read files. This will take a few
minutes depending on how much data you are processing.

#### Low Quality Sequence

For quality trimming, `sickle` implements a method called sliding window
quality. This looks at user definable subsections of your reads called
windows and averages the Q-scores of all bases in that window. If the
average Q score falls below a defined value, the read will be trimmed.

We will set our window size to 20, and our quality cut off to 15. That
means if any 20 base pair stretch of DNA drops below an average quality
of 15, the read will be trimmed.

The window moves (slides) along the read, for example bases 1-20, 2-21,
3-22 etc. Here’s what that command would look like in practice:

``` bash
sickle pe -q 15 -l 20 
  -f Sample01_R1_ cutadapt.fastq.gz 
  -r Sample01_R2_cutadapt.fastq.gz 
  -t sanger 
  -o Sample01_R1_trimmed.fastq.gz 
  -p Sample01_R2_trimmed.fastq.gz 
  -s Sample01_singletons.fastq.gz
```

Firstly, we are telling sickle we have paired end data with sickle `pe`
(because we have two sets of reads, forward and reverse). Next, we
provide the quality cut off (`-q`) and window length (`-l`). The `-t`
flag specifies how sickle should interpret the Q-scores - remember the
ASCII formatted Q-scores in our FastQ files? Well, as the field
developed there were different ways of encoding this data. Modern
sequencers all use the Sanger standard. Now we tell sickle where our
forward (`-f`) and reverse (`-r`) reads are, and where to stick our
trimmed reads (`-o` and `-p`). Finally, we provide the `-s` flag, which
produces a file of singletons. Singletons are reads that have no ‘mate
pairs’ - this would occur if a read in the forward file is trimmed, but
the corresponding read in the reverse file is not trimmed. Because there
is no complementary read, we want to get rid of them so as not to
interfere with downstream applications. Check the output sizes of your
files with `ls -lh`. Your singletons file should be very small, if its
large then that indicates there is an issue with one of your read files.

This was a bit of a whistle stop tour of QC. Don’t let its brevity mask
the importance of this stage - incorrect QC will lead to incorrect
results, so we’d recommend doing some background reading. FastQC’s
website, along with the manual for Trimmomatic are excellent starting
points. If you notice something wrong on FastQC, read up on that
section - most things can be mitigated or fixed entirely.

### Assembly

#### Spades and Shovills

As mentioned in the WGS theory section, the go-to assembler for short
read data is SPAdes. SPAdes takes paired end fastq data, and produces an
assembly in the fasta file format. To invoke spades, we need to point it
in the direction of our reads and tell it where to put the resulting
files. SPAdes is invoked from a python wrapper, as such we invoke it
using `spades.py`. Here’s an example command:

``` bash
spades.py 
  -1 myreads_R1.fastq 
  -2 myreads_R2.fastq 
  -o assembly_output 
  --careful 
  -t 4
```

Breaking that down, `-1` points to the first read file, `-2` to the
second, `-o` to the desired output directory, `--careful` increases
compute time, but reduces errors, and `-t` specifies the number of
threads that the program is allowed to use. A greater number of threads
will increase the speed at which your assembly is produced, but
including more threads than you have available can cause errors.

SPAdes will output several files in your specified output directory, the
important ones are `contigs.fasta` and `scaffolds.fasta`.

Scaffolding creates bridges between two contigs that the assembler know
are connected, but cannot identify which bases constitute the bridge.
Instead, it links them together by writing in ‘N’ characters. If you
want to get a file without these N characters, you can take
`contigs.fasta`.

Assemblies can take anywhere from 30 minutes to a few hours. If you have
hundreds of files to assemble then you don’t want to have to sit and
wait to enter your next command when an assembly finishes. Luckily, we
can get BASH to do that for us, by using what we learned earlier about
for loops. Let’s say we have a list of files with the following filename
structure:

    Sample01_R1_trimmed.fastq.gz
    Sample01_R2_trimmed.fastq.gz
    Sample02_R1_trimmed.fastq.gz
    Sample02_R2_trimmed.fastq.gz
    …
    Samplen_R1_trimmed.fastq.gz 
    Samplen_R2_trimmed.fastq.gz

A for loop to assemble all of these files would look like this:

``` bash
for f in *_R1_*; 
  do spades.py -1 $f -2 ${f/_R1_/_R2_} -o ${f/_R1_trimmed.fastq.gz/} --careful -t4; 
done
```

Again, remembering our for loop syntax from earlier, we are asking BASH
to collect all items with `_R1_` in their filename, and create a list
for our variable `f`. As this is our first read file, we pass our
variable to spades forward read flag `-1`. For the reverse read flag
`-2`, we want to pass it our `_R2_` file, so we use a variable edit
inside our curly brackets to find and replace `_R1_` with `_R2_`.

Remember, to see what effect this has, you can use echo to get BASH to
repeat your variable back to you:

``` bash
for f in *_R1_*; 
  do echo $f ${f/_R1_/_R2_}; 
done
```

Next, we want to specify our output directory. Because our unique sample
names are right at the front of our filename, we want to remove
`_R1_trimmed.fastq.gz` from our variable.

Here, we are essentially saying find that string, and replace it with
nothing. An alternative way of accomplishing the same function is to use
the `%` symbol, which essentially means delete the following string at
the end of the variable - it won’t work on strings at the start, or in
the middle of your variable.

Here are examples of these two methods accomplishing the same thing:

``` bash
for f in *_R1_*; 
  do echo $f ${f/_R1_ trimmed.fastq.gz/}; 
done

for f in *_R1_*; 
  do echo $f ${f%_R1_ trimmed.fastq.gz}; 
done
```

Finally, we ask SPAdes to run in careful mode to reduce errors and tell
it how many threads to use. BASH will tick along through all the files
matching your input variable, and you can come back a little while
afterwards to a folder full of assemblies.

Shovill is a pipeline that is designed to speed up the SPAdes assembly
process, whilst achieving the same quality or improved assemblies. It
also optionally integrates quality and adapter trimming features,
meaning you only need a single command to go from raw reads to an
assembled genome:

``` bash
shovill 
  --R1 sample_R1.fastq.gz 
  --R2 sample_R2.fastq.gz 
  --outdir output-directory 
  --cpus threads 
  --trim
```

As a loop:

``` bash
for f in *_R1_*; 
  do shovill 
    --R1 $f 
    --R2 ${f/_R1_/_R2_} 
    --outdir ${f/_R1_trimmed.fastq.gz/} 
    --cpus 4 
    --trim; 
done
```

Shovill produces assemblies with more informative contig IDs which are
readily compatible with downstream processes.

#### Managing Multiple Assemblies

You will see that whilst the directory name is informative, assemblies
within each are all called `contigs.fasta` or `contigs.fa` when using
shovill.

What we need is to go from:

    SRR123ABCD/contigs.fa 
    # to
    SRR123ABCD/SRR123ABCD_contigs.fa

The steps we want are:

1.  Get a variable name for the folder that we can use.

2.  move into \$folder

3.  change the name of the contigs.fa file to have \$folder at the start

4.  move back to original directory

5.  close the loops

We can get a list of the all lur assembly directories with:

``` bash
for folder in $(ls); do echo $folder; done
```

and then use that `$folder` variable in the next part of a loop.

``` bash
for folder in $(ls); 
  do cd $folder; 
  cp contigs.fasta "$folder"_contigs.fa; 
  cd .. ; 
done
```

To get them all in one Place (note we could have done this within the
above loop), we can use `find`

``` bash
find . -type f -name "S*_contigs.fa" -exec cp {} /shared/team/assemblies/renamed-assemblies/ \;
```

Find here, files with the name, then `exec`ute the cp on the file `{}`
to the directory. Semicolon `;` ends the command executed by `exec`. It
needs to be escaped with `\` so that the shell you run `find` inside
does not treat it as its own special character, but rather passes it to
`find`.

Now we have a directory called `renamed-assemblies` with meaningfully
labelled assembly files.

#### Assembly Quality

We can check the quality and accuracy of our assemblies and check for
contamination using quast and centrifuge respectively.

Let’s start with the most straightforward, quast.

``` bash
quast.py contigs.fa -o quast_output
```

This program generates several different files. For a quick overview we
can check `report.txt`. This file contains many different metrics. Here
are some of the most important ones:

- Number of contigs: how many stretches of DNA the assembly has been
  resolved to. Lower is better.
- N50: this can be a hard concept to grasp, but it essentially states
  that 50% of your genome is in contigs of this length or greater. N75
  is 75%, N90 90% etc. Larger is better.
- N’s per 100 kbp: this measures your assembly bridges. A perfect
  assembly has one contig per chromosome with no bridges, so less N’s is
  better.

There isn’t really a cut off for these values, as each assembly is
different. However, checking the distribution of your data will easily
identify problematic assemblies. To do this you can generate simple
scatter plots in R, Prism, or even Excel. These will enable you to
easily identify outliers which can then be investigated further.

It is really important to run QC on assemblies … as the saying goes
‘garbage in, garbage out’.

Centrifuge is a rapid microbial classifier that predicts the taxonomic
identity of sequence reads or contigs. We can use it to check that the
contigs we’ve assembled are from the microbe we are expecting. It is run
using the following command:

``` bash
centrifuge 
  -x /path/to/p_compressed+h+v+c 
  -p threads 
  -f 
  -U /path/to/<prefix>_contigs.fa 
  --report-file /path/to/report-file 
  -S /path/to/summary_file.txt
```

Here, `-x` is the indexed database you want to use, `-f` specifies that
we are using a fasta file, `-U` points to our input fasta,
`--report-file` and `-S` tell centrifuge where we want our outputs.

Centrifuge creates a report for each genome showing the number of
sequences that it assigns to each taxonomic group. It is worth noting
that centrifuge cannot distinguish regions of highly homologous
sequence, or regions that have undergone horizontal gene transfer and
recombination. Finally, no database is perfect and may not include
organisms that are infrequently identified.

## Sequence Typing and AMR

You now have an assembled genome (or maybe lots of them!). Some initial
quick analyses you may want to do include MLST typing and AMR gene
screening.

### MLST

MLST (**M**ulti-**L**ocus **S**equence **T**yping) uses a set of highly
conserved ‘house-keeping’ genes that are essential for cell growth. It
looks at the sequence of these genes, and assigns each allele (i.e.,
unique sequence of a gene) with a number.

The combination of numbers across all house-keeping genes is then
assigned to a sequence type.

![The theory of MLST](mlst-overview.png)

![The output of the ‘MLST’ tool](mlst-output.png)

Sequence types are one way of quickly identifying the relatedness of a
given strain to others, and through geographic and epidemiological
studies can inform potential sources and phenotypes associated with
those groups. The software used to quickly obtain an MLST type is called
… `mlst`! It can be invoked using:

``` bash
mlst --quiet <prefix>_contigs.fa
```

The `--quiet` flag supresses several dialogs that clog up your screen.
MLST will automatically determines which species database your file
belongs to and returns a list of alleles for that species MLST genes. If
there is a non-ambiguous match to an existing allele at each house
keeping gene, you will also receive a sequence type.

If you are running MLST on a group of fasta files, you may want to write
the output to a file (by default it is tab delimited). Remember our BASH
operators from earlier, this is done like so:

``` bash
mlst --quiet *.fa > mlst_types.tsv.
```

Remember, the `*` symbol means match anything, and as we’ve added the
`.fa` extension, we are asking BASH to execute mlst on all `.fa` files
in our current directory.

Because this is a simple command with no variable edits it is much
easier to use the `*` wildcard than to use a for loop. But what if our
`.fa` files are stored in subdirectories? Well, we can still use our
wildcard, like so:

``` bash
mlst --quiet */*_contigs.fa > mlst_types.tsv
```

This means in any directory beaneth the point I am at now, execute
`mlst` on the file with the suffix `_contigs.fa`. If there’s no file
matching that name then it won’t do anything.

### AMR

AMR prediction from genomes is tricky - you can’t definitively prove
that the presence or absence of a gene will result in a resistant or
sensitive phenotype. However, you can still quickly and easily screen
for a list of common antibiotic resistance genes.

This is quickly accomplished by `ABRicate`. `ABRicate` uses BLAST to
find sequences defined by numerous curated and widely used databases and
produces a nicely tab separated output. It’s written by the same author
(Torsten Seeman) as `mlst`, so you may find some similarities in how you
handle it. To run abricate:

``` bash
abricate <prefix>_contigs.fa
```

## Annotation

As discussed in the theory section, annotation is the process of gene
identification within the assembly.

### Prokka

The most common program for annotation **was** Prokka, which is yet
another program from Torsten, so usage is a breeze:

``` bash
prokka 
  --cpus 4 
  --outdir isolate_name 
  --prefix isolate_name 
  <prefix>_contigs.fa
```

Here, we are using `--cpus` instead of `-t` to specify the number of
threads, and `--outdir` instead of `-o` to point to our output
directory. The `--prefix` flag renames the output files (*you may want
to put the name of your isolate here*) if you do not include this, your
files will be encoded with the date of execution (e.g.,
PROKKA_20190922). Finally, we provide prokka with the input assembly
file.

You may see an error referencing contig IDs - this is due to something
called the genbank compliance standard that limits the permitted length
of contig headers. To fix this, use the flags `--compliant` and
`--centre X`.

Prokka automatically determines which database of proteins to use based
on the input genus, however if you want to use a specific genus
database, you must pass two flags: `--genus GenusName` and `--usegenus`,
for example:

``` bash
prokka 
  --cpus 4 
  --outdir isolate_name 
  --prefix isolate_name 
  --genus Escherichia 
  --usegenus 
  <prefix>_contigs.fa
```

Prokka is quick. You should have an annotation in under 10 minutes. You
will get several output files:

    <prefix>.gff    This is the master annotation in GFF3 format. 
    <prefix>.gbk    This is a standard Genbank file derived from the master .gff.
    <prefix>.fna    Nucleotide FASTA file of the input contig sequences.
    <prefix>.faa    Protein FASTA file of the translated CDS sequences.
    <prefix>.ffn    Nucleotide FASTA file of all the prediction transcripts 
    <prefix>.sqn    An ASN1 format "Sequin" file for submission to Genbank. 
    <prefix>.fsa    Nucleotide FASTA file of the input contig sequences
    <prefix>.tbl    Feature Table file, used by "tbl2asn" to create the .sqn file.
    <prefix>.err    Unacceptable annotations - the NCBI discrepancy report.
    <prefix>.log    Contains all the output that Prokka produced during its run.
    <prefix>.txt    Statistics relating to the annotated features found.
    <prefix>.tsv    Tab-separated file of all features.

The most important ones are the `.gff` and `.gbk`. These contain a list
of genes and their sequence - in the case of the genbank (`.gbk`) file
this sequence is also provided as translated amino acids.

### Bakta

However, a word of warning. At the time of writing Prokka is no longer
being actively supported. As a result ‘we’ suggest moving to Bakta. You
will see from the below that there are a number of similarities to
Prokka in terms of `--flags`.

``` bash
bakta 
  --db <db-path> 
  --threads 4
  --output isolate_name
  --prefix isolate_name
  --genus Escherichia
  -v 
  <prefix>_contigs.fa
```

The main difference is the `--db`. Here we are providing Bakta with a
path to a database which we need to download. For the purposes of the
course you will be given the path to that directory.

The results of Bakta are provided in a number of formats:

    <prefix>.tsv: annotations as simple human readble TSV
    <prefix>.gff3: annotations & sequences in GFF3 format
    <prefix>.gbff: annotations & sequences in (multi) GenBank format
    <prefix>.embl: annotations & sequences in (multi) EMBL format
    <prefix>.fna: replicon/contig DNA sequences as FASTA
    <prefix>.ffn: feature nucleotide sequences as FASTA
    <prefix>.faa: CDS/sORF amino acid sequences as FASTA
    <prefix>.inference.tsv: inference metrics (score, evalue, coverage, identity) for annotated accessions as TSV
    <prefix>.hypotheticals.tsv: further information on hypothetical protein CDS as simple human readble tab separated values
    <prefix>.hypotheticals.faa: hypothetical protein CDS amino acid sequences as FASTA
    <prefix>.txt: summary as TXT
    <prefix>.png: circular genome annotation plot as PNG
    <prefix>.svg: circular genome annotation plot as SVG
    <prefix>.json: all (internal) annotation & sequence information as JSON

### Annotation Loops

Wrapping either of these annotation tools into a for loop works just
like the assembly examples and we will make use of that
`renamed-assemblies` directory from earlier.

``` bash
cd renamed-assemblies
```

``` bash
for f in *.fa; 
  do 
    prokka 
    --cpus 4 
    --outdir ${f/\/_contigs.fa/_annotations} 
    --prefix ${f%_contgs.fa}
    --genus Escherichia 
    --usegenus 
    $f; 
done
```

Or in Bakta:

``` bash
for f in *.fasta; 
  do 
    bakta 
    --db <db-path> 
    --threads 4
    --outdir ${f/\/_contigs.fa/_annotations} 
    --prefix ${f%_contgs.fa} 
    --genus Escherichia
    -v 
    $f
done
```

In both examples we are taking `$f` are using the filename without the
suffix `_contigs.fa` to name the output directory and individual output
files. We are also, for `--outdir`, replacing it with a suffix
`_annotations`. We can now collect all these in a new directory here
called `collated-annotations`

``` bash
mkdir collated-annotations
```

``` bash
mv *_annotations collated-annotations
```

This way, everything is neatly stored. Coming back to these files later,
or running further downstream analyses, will be much easier. Ultimately,
you will develop your own ways of working, and your own preferred file
and for loop structures. Don’t take the examples above as gospel,
experiment and see what works for you.

## Mapping/Alignment

The terms mapping and alignment can mean slightly different things in
fields like human genomics, but for bacterial genomics they are largely
interchangeable. In general terms, mapping can be used to detect
differences between a set of sequences. You can map sequence A against
sequence B, or align sequence A against sequence B.

The important things to know about mapping and alignment is that you
have what’s called a reference sequence, and query sequence(s). For
example, if you have strains collected from a suspected outbreak, you
may generate an assembly for the earliest available isolate (used as a
reference), and then map sequence reads (query sequences) from all other
isolates against that reference.

During mapping, each individual read is compared to the reference to
find overlaps in the sequence data. This allows you to find regions that
differ between your reads and your query sequences.

This includes single base pair changes, called **S**ingle **N**ucleotide
**P**olymorphisms (SNPs). SNPs can have important biological functions,
for example: a single base pair change in the gene gyrA confers
resistance to fluroquinolones.

They can also provide important epidemiological context, linking
isolates to each other based on their level of similarity. Over the
course of an outbreak, a monoclonal isolate may acquire a few SNPs, but
a completely different clone from the same sequence type may contain
1000’s of SNPs. Mapping can therefore be used to infer which isolates
belong to a suspected outbreak.

Many other types of variations are identifiable via read mapping, some
of the important ones are InDels and MNPs. **IN**sertion and
**DEL**etion events (Indels) are occasions where a stretch of DNA is
removed or added, altering the length of the mapped region. **M**ultiple
**N**ucleotide **P**olymorphisms (MNPs) are several base pairs of
difference between reference and query but differ from InDels in that
both the reference and query have the same sequence length.

One of the most famous examples of the utility of read mapping occurred
during 2001’s Amerithrax investigation. Spores from *Bacillus
anthracis* - the causative agent of Anthrax - were discovered in several
letters sent to media outlets and governmental officials. *B. anthracis*
is highly invariant, acquiring only a handful of SNPs across long spans
of time. Given its threat to national security, intelligence agencies
have access to databases of known *B. anthracis* genomes, with rich
metadata reporting exact geographic and temporal origin. By comparing
the sequence data obtained from 2001’s Amerithrax attack to their
existing databases, they were able to track the exact source and
identify the suspects responsible for sending the letters. You can read
more in one of the coolest bacterial genomics papers: *Bacillus
anthracis* comparative genome analysis in support of the Amerithrax
investigation, in PNAS. At the time of writing there is also quite a
good Netflix documentary.

Read mapping involves a complex pipeline of tools, with several
different file formats for both intermediate and output files. Here’s an
example read mapping workflow:

![An example of read mapping](mapping.png)

Luckily, as it’s such a common task, there are several premade pipelines
that make things a little easier. One such pipeline is Snippy. Another
of Torsten Seeman’s classics, Snippy combines everything needed to go
from your input reads and reference to a neat and informative output
file. Another pipeline that you might want to check out is Breseq - we
won’t be going over that here, but it is a much more comprehensive
utility, and produces rich html outputs that include several additional
filters for errorsome variant calls.

Using Snippy is simple. Hopefully by now you can recognise what each
flag is doing, but if you want some extra help, just check Snippy’s very
helpful Github page.

``` bash
snippy 
  --ref reference.gbk 
  --R1 query_ R1.fastq.gz 
  --R2 query_R2.fastq.gz 
  --outdir out_directory
```

If you wanted to run Snippy in a loop, using the same reference file, it
would look like this:

``` bash
for f in query_R1.fastq.gz; 
  do snippy 
    --ref reference.gbk 
    --R1 $f 
    --R2 ${f/_R1/_R2}
    --outdir ${f%_R1.fastq.gz}; 
done
```

Notice that we’ve used a genbank annotation file for our reference. You
can also use a fasta assembly, but using a genbank file allows Snippy to
provide additional information about our variants, telling us in which
gene the variant was found, and its putative function.

Let’s look at what Snippy is doing under the hood. The first stage of
read mapping is to run the alignment software - this is the thing that
will compare your query reads to your reference sequence. Snippy uses
bwa mem for read alignment - another popular aligner is Bowtie2, which
you may see referenced in some microbial genomics papers.

The read aligner produces an output file in `.sam` and/or `.bam`
outputs. These files are part of a framework built around a standardised
file type encoding read alignment information. A `sam` file is
essentially a text file containing a list of reads and the positions in
the reference where they are found to match. A `bam` file is the same
file, but in binary format. This makes it easier for the computer to
read and interpret.

The next step is to use our `.bam` file to identify variants using a
variant caller. Snippy uses Freebayes. Freebayes looks at our sam file
and finds positions where the query and reference differ. Variant
callers output their results in the **V**ariant **C**all **F**ormat
(vcf), which is a comma separated file that contains multitudes of data.

The first few lines of a VCF are headers that contain information about
how the VCF was produced (e.g., program, flags). The actual variant
calls are displayed below, with column headings showing what each field
refers to. Here’s an example of a `.vcf` file:

![An example VCF file](vcf-example.png)

There’s lot to unpack here. But Snippy is not done yet - after the
`.vcf` is produced, it parses through your annotation file to provide
better information about your variants. It assigns genetic context to
each variant, identifying mutations both in and between genes
(intergenic variants), and filters the VCF output to include the
pertinent information. Here’s an example of Snippy’s most useful output
file - `snps.tab`:

    CHROM POS TYPE REF ALT EVIDENCE FTYPE STRAND NT_POS AA_POS LOCUS_TAG GENE PRODUCT EFFECT 
    chr 5958 snp A G G:44 A:0 CDS + 41/600 13/200 ECO_0001 dnaA replication protein DnaA missense_variant c.548A>C p.Lys183Thr 

The headings include:

- CHROM, the number of the contig that the variant was detected in.
- POS, the position within that contig - note that each new contig
  restarts the POS to 1.
- TYPE, what type of variant was detected (e.g., SNP, INS, DEL, MNP).
  REF, the basecall in the reference sequence.
- ALT, the variant as detected in the query.
- EVIDENCE, the number of reads that support either the REF or ALT base.

If your variant was found to be within a gene, you will also see some
extra information.

- AA_POS, is the number of the affected amino acid residue within that
  gene.
- EFFECT tells you whether the variant is Synonymous or Non-Synonymous.

The codons (three base sequences) that are translated to amino acids
have a level of redundancy, that means that multiple codons can encode
the same amino acid. If a variant occurs that does NOT change the amino
acid, it is called a Synonymous variant. If the variant causes a change
of amino acid, it is called a Non-Synonymous variant. You will also see
these variants describes as S/NS.

There are important things present in the VCF that aren’t in Snippy’s
`snps.tab` output file. To find the vcf, look in the snippy output
directory for `snps.vcf`. These include information relating to Depth
and Quality. Depth refers to the number of reads that have mapped to a
particular base. When we sequence a genome, we often obtain enough data
to cover the entire genome multiple times, which makes assembly and
variant calling easier and more reliable. As such, there will be many
reads that cover any given section of your reference file. If there are
30 reads that cover your variant, it would have a depth of 30. This
information is actually available in the `snps.tab` file but is
disguised - if you check the EVIDENCE column, the depth is the sum of
the ref and alt base calls.

There are two types of Quality score of note in the `.vcf` file - the
base quality, and the mapping quality. These are again formatted in the
old favourite standard, Phred. Base quality refers to the average
quality of the reads at a variant position. Mapping quality is a measure
of how confident the variant caller is that the variant is correct. This
is derived from several metrics, such as the depth, base quality, and
whether the read maps uniquely to the variant region. For example, if a
read maps to multiple parts in the genome your mapping quality will
decrease. By default, Snippy includes some commonly used cut-off filters
to weed out low quality variants. You can configure these manually -
just check out the manual.

## Core and Pangenomes

Pangenomes refer to the total gene content amongst a group of organisms.
This contrasts with a core genome, which includes only genes that are
shared amongst all organisms in that group.

Let’s assume we have a group of three organisms, each containing five
genes. Let’s look at each organism’s gene content:

![](pangenome1.png)

So, there is a total of 8 unique genes. How would that gene content look
as a core genome?

![](pangenome2.png)

As you can see, there are three core genes. Even though the gene umuC is
present in organism 1 and 2, it’s absent from organism 3 and as such
does not constitute a core gene.

Now let’s look at the pangenome:

![](pangenome3.png)

We can display the same information in a matrix format, giving us an
easier overview of the gene content and allowing us to quickly see which
genes are shared, and which genes are unique to a particular isolate:

![](pangenome4.png)

Bacterial genomes are plastic - they change over time, acquiring (and
losing) genetic elements via horizontal transfer (e.g., transposons,
plasmids). By studying the pangenome, we can identify genotypes that may
be associated with a particular phenotype of interest.

Pangenomes can also provide additional genomic context to groups of
bacteria. Perhaps you have identified a set of isolates that have very
little variation at a SNP level but have a variable phenotype - for
example, some of those strains may be resistant to colistin. Simply
looking at variation at a nucleotide level would not reveal the
underlying cause for this, but by examining their pangenome you could
identify genes that may be related to that resistance (i.e., mcr-1).

### Panaroo

Constructing pangenomes is still a challenging task, in part due to the
‘best-guess’ nature of *de novo* assemblies. Genes are grouped together
based on sequence similarity, but different similarity cutoffs can
produce different results. Genes may not be assembled in full - or not
covered at all.

Two main options for building pangenomes are Roary and Panaroo. Roary
has been around for longer, but generates errors that could be
misleading in downstream analysis. Today, a more popular option is
Panaroo, which was designed to avoid some of the errors made by Roary.

Whilst roary has been a mainstay for a long time, it is not without
issues and a more robust, efficient tool to consider using is Panaroo.

Panaroo uses `.gff` annotation files from Prokka or `.gff3` files from
Bakta and can align both core and pan-genomes. Invocation is very
straightforward:

``` bash
panaroo 
  –i *.gff 
  –o outdir 
  –t 8 
  --clean-mode moderate 
  -a core
```

Before running Panaroo, you may wish to collect your `gff` or `gff3`
annotation files into a single directory in order to make things easier.

There is a slight nuance whne using Bakta output in that you have to
provide a list of the `gff3` files you want panaroo to work with. This
is simply a text file with a path for each file per line. I’m sure you
can think of way to use `ls` to accomplish such a task.

``` bash
panaroo 
  -i <path-to-list-of-gff3s> 
  -o outdir 
  -t 8
  --clean-mode moderate 
  -a core
```

Panaroo works by parsing through annotation files, converting the CDS
into amino acids, and then clustering the AA sequences based on
homology. Several filtering steps involving all-against-all comparisons
and refinement of the gene clustering are then performed to produce the
final output.

Panaroo offers an improvement over the Roary, another popular pangenome
tool, by constructing pangenome graphs, showing how genes are ordered in
different genomes. The graph is used to identify possible mistakes in
the clustering process, like the accidental splitting of a gene family
into different groups, or the inclusion of contaminating DNA during
sequencing.

Panaroo outputs several files - one of the most useful is the
`gene_presence_absence.csv`. This is a comma separated data matrix,
which allows us to look at the presence and absence of genes across our
collection of genomes.

## Phylogeny

Phylogenies are a way of showing the relatedness of sequences,
organisms, or phenotypic features. They date back to the late 19th
century, with the most famous early example coming from Charles Darwin’s
notebook.

![Darwins tree of life - Charles Darwin, Public domain, via Wikimedia
Commons](Darwin_Tree_1837.png)

There are many ways of displaying phylogenetic trees, depending on what
you want to show. Why would you want to create a phylogenetic tree?
Well, it’s one way of charting evolutionary histories, or showing how
similar a set of organisms are from each other. From a bacterial
genomics standpoint, this can be used to show the relatedness of
organisms e.g., from an outbreak.

While phylogenies can look very different, they all have a common set of
features that help with reading and interpreting them. Let’s look at
some of them. We will use visual aids here, as phylogeny is inherently
visual data. Each feature we are describing will be highlighted in
coloured circles to make things easier.

![](tree1.png)

**TAXA** Named individual e.g., species, gene or sample number.
Sometimes called leaves or labels.

![](tree2.png)

**NODES** Represent divergence between taxa e.g., common ancestor, gene
family, sequence type.

![](tree3.png)

**CLADE** A group of taxa that share a common ancestor / node. Can be
composed of multiple sub-clades.

![](tree4.png)

**ROOT** Represents origin of inferred common ancestor of all taxa

Phylogeny could be the focus of its own week-long course, and is a very
dense subject area. If you want to learn more about phylogeny, EMBL-EBI
offer excellent web-based guides. There is also a very helpful section
in one of the best general microbiology textbooks, Brock’s Biology of
Microorganisms. I’ve yet to find a university library that does not
stock several copies of this book, so don’t worry about needing to spend
money on buying your own.

### Generating Phylogenies

There are several ways to make a phylogeny, each with varying levels of
complexity and accuracy. These range from quick and dirty trees that can
chart 1000’s of whole genomes in minutes, to highly complex dated
phylogenies that use Bayesian statistics and take several months to
complete.

We’ll cover three methods of generating a phylogeny, the quick and dirty
method: Mash, an intermediate method that is a little more accurate but
still quick: ParSNP, and a complex (i.e., takes a long time) but
accurate and industry standard method: RAxML.

### MASH

The first step in generating a tree is to figure out how different your
sequences are to each other. This could be done via alignment, as
discussed in the previous chapter. But alignment is slow, and for quick
and dirty trees you need quick and dirty comparison methods. Enter
**M**inH**ASH** (MASH).

MASH splits up your input sequences into small k-mers, and assigns each
unique k-mer with a computationally easy-to-digest ‘hash’ value. Hashing
is similar to the way the Dewey Decimal system makes archiving and
locating books easier.

Next, distances between these hashes are calculated, which are then used
to inform and draw our phylogeny. The maths behind this is …

![](mash.jpg)

Yeah, thank god we aren’t doing this from scratch! There’s a program to
do all of this for you: `MashTree`, which uses this MinHASH method along
with a common phylogeny creation tool FastTree to generate a phylogeny.
`Mashtree` (written in perl, hence the .pl below) is invoked very
simply:

``` bash
mashtree.pl *.fasta > out.tree
```

Another wildcard, again collecting all fasta files in our current
working directory. The output format is given the `.tree` extension.

A common way of storing phylogenetic information is in the Newick
format. It is essentially a text file that contains a list of nodes, and
information on the distance between each node. Here’s an example of a
Newick formatted tree, and what that tree looks like as a basic
visualisation.

    ((raccoon:19.19959,bear:6.80041):0.84600,((sea_lion:11.99700, seal:12.00300):7.52973,((monkey:100.85930,cat:47.14069):20.59201, weasel:18.87953):2.09460):3.87382,dog:25.46154);

![An example newick tree image](newick-image.png)

It might be hard to see, but at the top left of that image is a new
thing we haven’t talked about yet. The scale bar. A common mistake when
reading phylogenies is to assume that vertical distance - or the lack
thereof - makes two taxa highly similar. However, the only thing the Y
axis is useful for is when considering how taxa are organised into
clades. It is clades that tell you if taxa are related, with horizontal
distance giving an idea of how different each taxa are to each other.

Here, we can see that Monkey and Cat are in the same clade. but the long
horizontal lines (if not our own common sense) show us they are very
different from each other. The scale bar provides context to the
horizontal distance, here we have an arbitrary unit of ‘10’. In
bacterial genomics you would (hopefully) have a more descriptive unit in
the figure legend.

### ParSNP

ParSNP also uses a method of compressing the amount of information it
needs to compare when assessing how different input sequences are from
each other. It is a core-genome aligner.

This already reduces the amount of information that needs to be
compared - which can be a good or a bad thing, depending on your use
case. ParSNP also has a few more tricks up its sleeve to increase
compute speed - if you want to know specifics, check out their
documentation pages.

To run ParSNP, you need to point it to a directory containing the
`.fasta` files you want to analyse. It’s important that this directory
contains only the files you want to analyse, so it’s worth setting up a
new folder. Here’s an example command:

``` bash
parsnp -r reference.fasta -d assembly_ directory -p 4
```

By default, your tree will be named `parsnp.tree`. ParSNP generates its
own output directory, named according to the date and time of execution.

Remember our scale bar? Well, we can provide that all important context
by figuring out the core-genome size identified by ParSNP.

You may have fed ParSNP tens of 5.2 Mb *E. coli* genomes, but if the
isolates are very different then they will have a very small core
genome. Identifying the size of the comparison used to generate a
phylogeny is essential to correctly interpret the horizontal distance.

To calculate your core genome size, we need to look at the
`parsnpAligner.log` file. Within this file there is a line that gives
the per sequence coverage, to calculate the core genome size take the
length of the input assembly (also listed in the log file) and multiply
it by the % of coverage. We can quickly view these lines using grep -
each input sequence is assigned a sequence number, so to check the first
sequence:

``` bash
grep -i ‘Sequence 1’ --after-context 3 parsnpAligner.log
```

This returns a few extra lines, but we’re interested in Length, and
Coverage. Here’s an alignment with a core genome size of 4,374,206 bp.

    Sequence 1 : path/to/file
    Sample01.fasta.ref
    Length:   ***5176576 bps***
    --
    Cluster coverage in Sequence 1:***84.5%***

5176576 X 0.845 = 4,374,206 bp

### Core Gene Alignments

Some tree-building tools require you to provide a sequence alignment to
build the tree. This may include whole genome alignments, core genome
alignments, or perhaps smaller single gene alignments (e.g., 16S rRNA).
There are many ways to generate an alignment - we’ve already used a
program that can do it for us - Snippy!

Snippy has a module we haven’t talked about yet, and that’s core-genome
alignment (invoked with `snippy-core`). This is exactly same principle
as `ParSNP`, but `snippy-core` generates core alignments in a more
robust way (i.e., mapping).

To use `snippy`-core, you need to have multiple snippy output
directories that were generated by mapping a set of reads to a single
common reference. You can then generate your core alignment by pointing
`snippy-core` to those directories:

``` bash
snippy-core Sample01/ Sample02/ Sample03/
```

`snippy-core` again identifies variable genomic positions that are
present in all of your files, and then outputs the `core.aln` alignment
file. We can then use this file with to build a tree.

Panaroo is also able to produce a core genome alignment, by passing it
an extra flag.

``` bash
panaroo –i *.gff –a core –o outdir –t 8
```

The alignment file is called `core_gene_alignment.aln`.

### Removing Recombination

Recombinogenic bacteria can exchange and integrate DNA from homologous
sources, which can obviously complicate variant calling and phylogenetic
reconstruction.

Areas of recombination will contain many variants within a short stretch
of DNA, and as such can make highly similar isolates appear distantly
related, even from a single recombination event.

To account for this, you can use Gubbins. Gubbins (which stands for
**G**enealogies **U**nbiased by recom**B**inations **I**n **N**ucleotide
**S**equences) takes an alignment file and identifies loci with a high
density of variants. You can use the full alignment generated by
`snippy-core`:

``` bash
run_gubbins.py core.full.aln
```

Gubbins outputs a recombination-free alignment file in multi-fasta and
phylip formats. You can then use these alignments in downstream
applications for phylogeny construction for example.

Gubbins is highly customisable, and many of the options will be organism
or case specific. As always, ensure that you read the manual and be
cognisant of the underlying question you are trying to answer.

Note: as with every program, Gubbins is not the only way to look at
recombination. If you find yourselves becoming familiar with the R
programming language, then I would strongly encourage you to check out
ClonalFrame ML.

### Identifying Variable Sites

Running the entire core genome through a tree builder can be
resource-intensive and unnecessary. Instead, we can input just the parts
of the alignment that vary between samples. Snippy does this
automatically, but you will need to run a tool like snp-sites to get
this from a Panaroo core gene alignment.

### RAxML

Whilst the previous programs have generated their own genetic
comparisons using scaled-down methods, RAxML requires you to provide it
with a precomputed alignment file. RAxML is a tool designed purely for
tree inference. It will produce the most accurate phylogenies possible
from the data that you supply to it. It is a statistical and programming
tour-de-force, and is the gold standard for generating phylogenies.
Nearly every Nature or PNAS paper containing a phylogeny will have used
RAxML to generate their tree, and with good reason - it’s highly
accurate. This in part because it uses statistical models to
contextualise variants. If you thought that last algorithm was scary,
have a look at this bad boy:

![The GTR Model](GTR.png)

And that’s just one of the many possible models of evolution. It happens
to be the most frequently used model for microbial genomics, GTR-GAMMA.
This is yet another example of a subject that could be the focus of its
own course. I would recommend background reading on the maths behind it,
but honestly, I find it too dense and complex to get into. If you’re
from a mathematical discipline you’ll likely fair a lot better, so give
it a go! We’ll go over theory behind evolutionary models in the course,
which will hopefully give you a base level of understanding of what the
models are and why they’re useful.

As an aside, RAxML has undergone many revisions since its release. There
are many different versions of the package that suit different server
architectures (e.g., HPC, P-THREADS, AVX). The most contemporary
iteration - `raxml-ng` was written from the ground up and makes a number
of improvements over the older version. This includes the ability to use
checkpoints as it can take a long time to run, and if it fails after 30
days with 10% of the work left, before you would be out of luck.
`raxml-ng` allows you to restart a job from the most recent checkpoint,
saving you a lot of time and stress.

We can invoke raxml-ng like so:

``` bash
raxml-ng -all --msa core.aln --model GTR+G --tree pars{10} --bs-trees 100
```

`raxml-ng` has several modules for different things, first, we use
`--all` to tell it to use all modules. Next we point it to our Multiple
Sequence Alignment file generated by `snippy-core` (`--msa core.aln`).
Remember that horrible equation? Maybe you’re trying to forget about it.
In any case, we ask raxml-ng to use this model (`--model GTR+G`). The
next two parts are a little more complicated and rely on concepts known
as parsimony and bootstrapping.

Parsimony is a way of constructing a tree that assumes the simplest
method (i.e, the fewest evolutionary events, or number of clades) is the
correct one. In this context, `raxml-ng` looks at our data, and produces
a few rough ‘best guess’ phylogenies which it will refine into a work of
art. Here, we’re saying make 10 of those trees and choose the best one.

Bootstrapping is a way of providing statistically robust phylogenies. It
involves repeatedly generating the phylogeny with subsets of data, and
seeing how many times a given node appears in the same evolutionary
position. We are asking `raxml-ng` to do this 100 times, which provides
a good amount of statistical confidence while limiting the compute time.

For all its bells and whistle, RAxML still outputs a humble newick
formatted tree file - you’ll find it with the `.tree` extension.

### FastTree

Alternatively, if a quicker and less accurate tree is suitable for your
analysis, you may consider running `FastTree`:

``` bash
FastTree –nt –gtr core_gene_alignment.aln > output.tree
```

FastTree is still capable of using statistical models of evolution, but
as its name implies is much quicker. This is obviously at the cost of
accuracy and statistical robustness, but in some applications, this
isn’t of critical importance.

### Visualising Phylogenies

Now to get those newick trees into something a bit more tree like… there
are many programs that handle phylogenetic tree visualisation, but two
of the most popular ones are iTOL and FigTree.

iTOL - or the Interactive Tree of Life - is not really a program at all,
it’s hosted on a webserver that’s accessible due to its high ranking by
a quick Google search. You can either paste in or attach your newick
tree file and will be greeted with a slightly ugly phylogenetic tree.
iTOL is blessed by great manual pages, so check out their tips for
refining your tree, and even adding additional data as annotations, like
sequence or resistance types.

FigTree is a freely downloadable, multi-platform program that is a
little bit better at handling basic tree manipulation. Point it to your
tree file, and away you go. Here’s that same lame monkey/cat tree opened
in FigTree:

![Figtree output - an unrooted phylogeny](figtree.png)

One very useful feature of FigTree is the ability to reroot the tree.
Remembering our terminology, the root is the imputed sequence that all
taxa are related to, or the most-recent common ancestor of all taxa.

A popular way of showing phylogenies is using the midpoint root. As its
name implies, this involves finding the middle point of the longest
branch between any two tips and sets the root there. Here’s what that
looks like:

![Figtree output - a midpoint rooted phylogeny](midpoint.png)

Notice the difference between the monkey and cat taxa? This is a
phylogeny that makes much more sense (but won’t explain why your cat is
addicted to bananas). It might be hard to see, but to mid-point your
tree in FigTree, on the left-hand menu click the ‘Tree’ drop down icon,
click the ‘Root tree’ tick box, and select ‘midpoint’.

The coolest thing I stumbled across in FigTree is that it supports
pasting from the clipboard. That means on your server you can view your
newick formatted tree:

``` bash
cat lamemonkeycat.tree
```

Highlight and copy the text, and then paste that directly to the FigTree
window.

The tree file can be used in conjunction with a pangenome constructed
from the same isolates - this allows you to easily visualise the sharing
of gene content in the context of phylogenetic distribution. Here’s an
example:

![Pangenome visualised in the context of a
phylogeny](phylopangenome.png)

The pangenome is visualised as blue blocks, with each block on the X
axis representing a gene. One method of generating this type of
pangenome annotated phylogeny is with Phandango. Phandango is a
web-based application that takes a newick formatted phylogenetic tree,
and the `gene_presence_absence.csv` file generated by Panaroo.

Simply drag and drop your files onto the Phandango splash page, and
you’ll get a neatly annotated phylogeny.

## SNP Distance Matrices

To quickly compare multiple samples, you can produce a SNP distance
matrix. This shows you how many SNPs are present across all samples in a
pair-wise fashion.

`snp-dists` is included as part of `snippy-core`, but can also be run
separately using:

``` bash
snp-dists sequence.aln > distances.tab
```

This program outputs in a tab separated format, which can easily be
viewed within terminal (using `less -S`, for example) or in Excel.

Here’s an example of four sequences:

![A snp distrance matrix](snpdists.png)

In this example, seq1 is most related to seq2. We can see that seq4 is
the most distantly related to all sequences, and whilst seq3 is more
closely related to 1 and 2 it is still distantly related to seq4.

You can use SNP distances to annotate trees, providing contextual
information to clades and horizontal branch lengths, or just to quickly
see which isolates are closely or distantly related.

# Wrapping Up

The information in this booklet covers the main topics we’ll go over
during the course. The course is structured to include the tools and
techniques that are routinely used when analysing microbial genomic data
but is obviously not an exhaustive resource.

As you become familiar with BASH and become a better bioinformatician,
your skill set and approach to analyses will inevitably evolve. As a
relatively new field, bioinformatics tools and techniques are constantly
evolving, so make sure to keep on top of the literature.

A great way of doing this is by checking out X, formerly Twitter, (or
whichever alternative is popular by the time you come to read this
manual). New tools that gain buzz are often worth checking out, and it’s
a good way of searching for recommendations.

The journals Bioinformatics, Microbial Genomics, BMC Genomics, as well
as the ‘Glam’ journals (PNAS, Nature etc.) are all excellent resources
for checking out how to do a particular analysis type. Head to the
methods and supplementary materials for details on how published
research is conducted.

We hope that this booklet has been helpful and may serve as a reference
point for your first forays into the world of microbial genomics.

Good luck!

# BASH Cheat Sheet

| Command                |                                 Explanation |
|------------------------|--------------------------------------------:|
| ssh <user@ip.add.ress> |                         connect to a server |
| screen -S name         |                   create a new named screen |
| screen -dr name        |                        reattach to a screen |
| top                    |                see list of active processes |
| Ctrl + c               |                      cancel current process |
| TAB                    |             autocomplete commands and paths |
| pwd                    |                     print working directory |
| ls -ltrh               |                                        list |
| mv                     |                       move or rename a file |
| cp                     |                                        copy |
| rm                     |                                      remove |
| rm -r                  | remove a dir and (recursively) its contents |
| mkdir                  |                              make directory |
| cd ( ../ )             |                            change directory |
| cat                    |                            read to terminal |
| head / tail            |          read first/last 10 lines of a file |
| less / more            |                         scroll through file |
| grep                   |                                      search |
| conda activate env     |                        activate environment |
| \> (\>\>)              |                                 output to … |
| \*                     |                                    wildcard |
| Ctrl + E / A           |                 jump to end / start of line |
| du -h                  |                              check disk use |

# Appendix A Flow-chart of Methods Covered

![](flow.png)

# Appendix B Day One

## Practical One

Files available in /shared/team/course-files/day1/p1/

### Files:

- MyFile-9.txt pspC
- my-file-2.txt Darwin pt2
- my-file-four.txt bad jokes
- my-file-1.txt Darwin pt1
- my-file-3.txt pspC
- my-file-10 fastq
- sequence1 E. coli genome
- rugby-stats-1.txt players
- rugby-stats-3.txt points
- rugby-stats-2.txt country

Combining all the rugby stats into one file sorted by most points (note
that column number might change if they have combined them differently)

``` bash
paste -d "," rugby-stats-1.txt rugby-stats-2.txt rugby-stats-3.txt | cat | sort -k 3 -t , -n -r
```

### Output:

The students should have a Darwin file, a multi-fasta of two pspC genes,
relabeled sequence1 to E.coli-genome or similar, created relevant
directories and file names, identified one file as containing bad jokes
and be able to tell us that Ramos (the French player) is currently the
leading points scorer.

## Practical Two

`cp` (don’t `mv`) the DX_fastq.gz files to your home directory

Task 1 (hard): rename files so that they are e.g., D2_2023_R1.fastq.gz

Task 2 (easier): use echo within a loop to create a file of R1 file
names only

- D2_R1.fastq.gz

- D2_R2.fastq.gz

- D9_R1.fastq.gz

- D9_R2.fastq.gz

Hard:

``` bash
for f in D*_* ; 
  do 
    echo "mv $f ${f/_R/_2023_R}"; 
  done
```

Easier:

``` bash
for f in *_R1*; do echo $f >> newfile.txt; done
```

# Appendix C Day Two

## Download Data

Downloading data from SRA. Could have list of accessions in a for loop:

``` bash
for l in $(cat accessions-file); do something $l; done
```

However, for reasons related to where commands runs, the better syntax
is to use a while read loop:

``` bash
while read -r line; 
  do parallel-fastq-dump 
    --sra-id $line 
    --threads 8 
    --outdir /path/to/somewhere/ 
    --split-files 
    --gzip; 
done < SraAccList_4Playing.csv
```

If you want to know how long it takes just add `time` do the beginning
of the command. In my case:

    real 42m55.599s
    user 191m41.507s
    sys 2m10.245s

Test data for download is PRJEB39742 (SraAcclist-4Playing.csv in
`shared/team/course-files/day2/`). Download only the first five lines.
This will test the download; it’s a small read set for *Moraxella
catarrhalis*.

## Cutadapt

Populate cutadapt command with a variable called \$SAMPLE

Test the loop:

``` bash
for i in /shared/team/fastqs-prjna565698/*_1.fastq.gz; 
  do SAMPLE=$(echo ${i} | sed "s/_1.fastq.gz//"); 
  echo ${SAMPLE}; 
done
```

``` bash
for i in /shared/team/fastqs-prjna565698/*_1.fastq.gz; 
  do SAMPLE=$(echo ${i} | sed "s/_1.fastq.gz//");
    echo ${SAMPLE}_1.fastq.gz ${SAMPLE}_2.fastq.gz;
    cutadapt 
      -a ACTGAC 
      -A ACTCTG 
      -o ${SAMPLE}_cutadapt_1.fastq.gz 
      -p ${SAMPLE}_cutadapt_2.fastq.gz 
      ${SAMPLE}_1.fastq.gz ${SAMPLE}_2.fastq.gz; 
done
```

## Sickle

Populate sickle command with a variable called \$SAMPLE

``` bash
for i in *_1.fastq.gz; 
  do SAMPLE=$(echo ${i} | sed "s/_1.fastq.gz//");
    echo ${SAMPLE}_1.fastq.gz ${SAMPLE}_2.fastq.gz;
    sickle pe 
      -q 15 
      -g 
      -f ${SAMPLE}_1.fastq.gz 
      -r ${SAMPLE}_2.fastq.gz 
      -t sanger 
      -o ${SAMPLE}_sickled_1.fastq.gz 
      -p ${SAMPLE}_sickled_2.fastq.gz 
      -s ${SAMPLE}_singletons.fastq.gz; 
done
```

## Shovill Assembly

Note - shovill does read trimming.

``` bash
shovill 
  --R1 SRR10242885_1.fastq.gz 
  --R2 SRR10242885_2.fastq.gz 
  --outdir SRR10242885 
  --cpus 8 
  --trim
```

Populate shovill command with a variable called \$SAMPLE

``` bash
for i in *_1.fastq.gz;  
  do SAMPLE=$(echo ${i} | sed "s/_1.fastq.gz//"); 
    echo ${SAMPLE}_1.fastq.gz ${SAMPLE}_2.fastq.gz; 
    shovill 
      --R1 ${SAMPLE}_1.fastq.gz 
      --R2 ${SAMPLE}_2.fastq.gz 
      --outdir ${SAMPLE} 
      --cpus 8 
      --trim;  
done
```

## Assembly QC

### Quast and MultiQC

``` bash
quast assemblies/*.fasta -o quast-out
```

run multiQC

``` bash
multiqc quast-out/
```

### Centrifuge

To make database available

``` bash
export CENTRIFUGE_BASE="/shared/team/centrifuge_db"
echo $CENTRIFUGE_BASE
# Needs to be done every time after logging out
```

To run

``` bash
conda activate conda-envs/centrifuge/
```

``` bash
centrifuge 
  -x /shared/team/centrifuge_db/p_compressed+h+v 
  -p 8 
  -f 
  -U SRR10242855_contigs.fasta 
  --report-file test1 
  -S test2 
```

# Appendix D Day Three

## MLST

``` bash
#to show available schemes
mlst --longlist
```

``` bash
#an example on one
mlst --quiet --scheme ecoli SRR10242880_contigs.fa
```

``` bash
#an example for many
mlst --quiet --scheme ecoli *_contigs.fa > output.txt
```

## Abricate

``` bash
#run on all .fasta and then combine into single report
abricate *_contigs.fa > results.tab
abricate --summary results.tab > summary.tab
```

## Prokka

``` bash
# just an example
prokka --cpus 8 --outdir SRR10242855 --prefix SRR10242855 --compliant SRR10242855_contigs.fa
```

## Mapping and Alignment

Using snippy

``` bash
conda activate /shared/team/conda-envs/snippy
```

``` bash
#Do this from the folder with the input fastq.gz files OR specificy the full path them. 
#Do you need another folder in the directory in order to put all the _snps outputs?

while read –r line; 
  do snippy 
    --cpus 8 
    –-ref SBEC.gbk 
    --R1 $line”_1.fastq.gz” 
    --R2 $line”_2.fastq.gz” 
    --outdir /shared/team/yourname/“$line”_snps; 
done < /shared/team/course-files/SraAccList-prjna565698.txt

#Supply path to reference
#Note you can supply --ref with a .fasta file as well but this will be less informative.
```

# Appendix E Day Four

## Phylogeny

### MinhASH (MASH)

``` bash
mashtree /path/to/assemblies/*_contigs.fa > mash-out.tree
```

### ParSNP

ParSNP will automatically kick out genomes whose length seems erroneous
compared to the references. Have to add `--vcf` flag to output a vcf
file, but harvest-tools can convert .ggr into a vcf as well.

``` bash
parsnp -r /path/to/reference/file.fasta -d /path/to/directory/ -p 8 --vcf
```

``` bash
#to calcualte core genome from parsnpAligner.log
# sequence 1 is reference
#--after-context is the same as -A
grep -i 'sequence 1' --after-context 3 parsnpAligner.log
```

Multiply reference genome length by cluster coverage to get core genome
size.

### RAxML

``` bash
snippy-core -r /path/to/reference/ snippy-out/*
```

Output files:

- .aln A core SNP alignment in the

- –aformat format (default FASTA)

- .full.aln A whole genome SNP alignment (includes invariant sites)

- .tab Tab-separated columnar list of core SNP sites with alleles but NO
  annotations

- .vcf Multi-sample VCF file with genotype GT tags for all discovered
  alleles

- .txt Tab-separated columnar list of alignment/core-size statistics

- .ref.fa FASTA version/copy of the –ref

Useful message that comes out:
`Run 'snp-sites -b -c -o phylo.aln core.full.aln' for IQTree, BEAST, RaxML`

``` bash
snp-sites -b -c -o phylo.aln gubbins.filtered_polymorphic_sites.fasta
```

``` bash
raxml-ng -all --msa phylo.aln --model GTR+G --tree pars{10} --bs-trees 100
```

– -all all modules

– -msa multiple sequence alignment file

– -model

– -tree make 10 parsimonious trees and pick the best as the starting
point

– -bs-trees 100 bootstraps
