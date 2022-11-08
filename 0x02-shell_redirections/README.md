# Shell, I/O Redirections and filters :page_with_curl: 0x02-shell_redirections
## About this project:
In this project i learn and practiced Shell Input/Output Redirections and filters;
#### I/O Redirection
- What do the commands `head`, `tail`, `find`, `wc`, `sort`, `uniq`, `grep`, `tr` do
- How to redirect standard output to a file
- How to get standard input from a file instead of the keyboard
- How to send the output from one program to the input of another program
- How to combine commands and filters with redirections
#### Special Characters
- What are special characters
- Understand what do the white spaces, single quotes, double quotes, backslash, comment, pipe, command separator, tilde and how and when to use them
#### Others
- How to display a line of text
- How to concatenate files and print on the standard output
- How to reverse a string
- How to remove sections from each line of files
- What is the `/etc/passwd` file and what is its format
- What is the `/etc/shadow` file and what is its format
## Tasks file descriptions;
  * [0-hello_world](./0-hello_world): Bash script that prints "Hello, World"
  followed by a new line to the standard output.

* [1-confused_smiley](./1-confused_smiley): Bash script that displays a confused smiley
  `"(Ôo)'`.

* [2-hellofile](./2-hellofile): Bash script that displays the content of the
  `/etc/passwd` file.

* [3-twofiles](./3-twofiles): Bash script that displays the content of
  `etc/passwd` and `/etc/hosts`.

* [4-lastlines](./4-lastlines): Bash script that displays the last 10 lines of `/etc/passwd`.

* [5-firstlines](./5-firstlines): Bash script that displays the first 10 lines
  of `/etc/passwd`.

* [6-third_line](./6-third_line): Bash script that displays the third line
  of the file `iacta`.

* [7-file](./7-file): Bash script that creates a file named exactly
  `\*\\'"Holberton School"\'\\*$\?\*\*\*\*\*:)` containing the text
  `Holberton School` ending by a new line.

* [8-cwd_state](./8-cwd_state): Bash script that writes into the file `ls_cwd_content` the
  result of the command `ls -la`.

* [9-duplicate_last_line](./9-duplicate_last_line): Bash script that duplicates the last
  line of the file `iacta`.

* [10-no_more_js](./10-no_more_js): Bash script that deletes all the regular files (not
  directories) with a `.js` extension that are present in the current directory
  and all its subfolders.

* [11-directories](./11-directories): Bash script that counts the number of directories and
  sub-directories in the current directory, not including the current and parent
  directories but counting hidden ones.

* [12-newest_file](./12-newest_files): Bash script that displays the 10 newest files in the
  current directory, one file per line, sorted from newest to oldest.
  
* [13-unique](./13-unique): Bash script that takes a list of words as input and only
  prints words that appear exactly once, one word per line, sorted.

* [14-findthatword](./14-findthatword): Bash script that displays lines containing
  the pattern "root" from the file `/etc/passwd`.

* [15-countthatword](./15-countthatword): Bash script that displays the number of lines
  containing the pattern "bin" in the file `/etc/passwd`.

* [16-whatsnext](./16-whatsnext): Bash script that displays lines containing the pattern
  "root" and 3 lines after them in the file `/etc/passwd`.

* [17-hidethisword](./17-hidethisword): Bash script that displays all lines in the file
  `/etc/passwd` that do not contain the pattern "bin".

* [18-letteronly](./18-letteronly): Bash script that displays all lines of the file
  `/etc/ssh/sshd_config` starting with a letter, including capital letters.

* [19-AZ](./19-AZ): Bash script that replaces all characters `A` and `c` from input
  to `Z` and `e` respectively.

* [20-hiago](./20-hiago): Bash script that removes all letters `c` and `C` from input.

* [21-reverse](./21-reverse): Bash script that reverses its input.

* [22-users_and_homes](./22-users_and_homes): Bash script that displays all users and
  their home directories, sorted by users, based on the `/etc/passwd` file.

* [100-empty_casks](./100-empty_casks): Bash script that finds all empty files
  and directories in the current directory and all sub-directories as follows:
    * Only the names of the files and directories are displayed.
    * Hidden files included.
    * One file name per line.

* [101-gifs](./101-gifs): Bash script that lists all the files with a `.gif` extension
  in the current directory and all its sub-directories as follows:
    * Hidden files included.
    * Only regular files (not directories) listed.
    * File names displayed without extensions.
    * Files sorted by byte values, but case insensitive.
    * One file name per line.

* [102-acrostic](./102-acrostic): Bash script that decodes acrostics that use the first
  letter of each line.

* [103-the_biggest_fan](./103-the_biggest_fan): Bash script that parses web
  server logs in TSV format as input and displays the 11 hosts or IP addresses
  which did the most requests.
  * Ordered by number of requests, with most active hosts or IP's at the top.
