# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*  $ pwd
/c/Users/14256/projects/wats1030-intro-to-unix

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
$ ls
challenge_files  LICENSE  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  README.md  super_scavengers.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*

14256@LAPTOP-2I113BDO MINGW64 ~/projects/wats1030-intro-to-unix (master)
$ ls -alh
total 78K
drwxr-xr-x 1 14256 197609    0 Jan 18 09:22 .
drwxr-xr-x 1 14256 197609    0 Jan 18 09:22 ..
drwxr-xr-x 1 14256 197609    0 Jan 18 09:22 .git
drwxr-xr-x 1 14256 197609    0 Jan 18 09:22 challenge_files
-rw-r--r-- 1 14256 197609 1.1K Jan 18 09:22 LICENSE
-rw-r--r-- 1 14256 197609 5.5K Jan 18 09:22 nix_scavenger_hunt.md
-rw-r--r-- 1 14256 197609  325 Jan 18 09:22 nix_scavenger_hunt_stretch.md
-rw-r--r-- 1 14256 197609 2.8K Jan 18 09:22 README.md
-rw-r--r-- 1 14256 197609  268 Jan 18 09:22 super_scavengers.md

not only is the directory shown byt creation date, file size are also visible

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

PC User, no man command

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*

$ ls /
bin  cmd  dev  etc  git-bash.exe  git-cmd.exe  LICENSE.txt  mingw64  proc  ReleaseNotes.html  tmp  unins000.dat  unins000.exe  unins000.msg  usr

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*


14256@LAPTOP-2I113BDO MINGW64 ~/projects/wats1030-intro-to-unix (master)
$ cd ~/projects

14256@LAPTOP-2I113BDO MINGW64 ~/projects
$ pwd
/c/Users/14256/projects

14256@LAPTOP-2I113BDO MINGW64 ~/projects
$

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

$ cd ~

14256@LAPTOP-2I113BDO MINGW64 ~
$ pwd
/c/Users/14256

14256@LAPTOP-2I113BDO MINGW64 ~
$

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
14256@LAPTOP-2I113BDO MINGW64 ~/projects/wats1030-intro-to-unix/challenge_files (master)
$ ls *.demo
2015_special_stuff.demo  cloaked-wookie.demo  scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
14256@LAPTOP-2I113BDO MINGW64 ~/projects/wats1030-intro-to-unix (master)
$
* Press the up arrow on your keyboard. *What just happened?*
previous command listed "cd .."
* Press the up arrow a few more times. *What do you see?*
cycling through all previous commands
* Run the `history` command. *What do you see?*
full listing of all previous commands in current session

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
$ whoami
14256

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
$ who

(no other users)
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
$ uptime
bash: uptime: command not found

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
$ ps aux
      PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
     1920    1785    1920       7768  cons0     197609 10:56:26 /usr/bin/ps
     1785       1    1785      16340  cons0     197609 10:10:35 /usr/bin/bash

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
$ top
bash: top: command not found

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
$ ls credit*
credit_cards.txt  credit_cards2.txt

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

$ more credit_cards.txt
bash: more: command not found

less command - last updated 1-15-15

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*

$ find -name "*modi_laboriosam.txt"
./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*

2 files
$ grep "WA" *user
Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241


* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

$ grep -r "Waldo" .
./serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt 
sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

Line 4

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*

a list of all files and folders within "challenge_files" folder, in text form, are listed in files.txt

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

It appears the ls -alh | less command produces the maximum number of files/folders in the challenge_files folder that can be viewed in the viewpoer without scrolling.  The output was reduced to only show what could be displayed without scrolling

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

$ ps aux | grep [14256]
     1015     818    1015      14876  cons0     197609 21:06:56 /usr/bin/ps
      818       1     818       8668  cons0     197609 11:17:07 /usr/bin/bash
