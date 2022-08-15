<h1 id="top">Bandit Writeup</h1>
<p><strong>Link to the site:</strong> <a
        href="https://overthewire.org/wargames/bandit">https://overthewire.org/wargames/bandit</a>
    <br>
    <br><strong>Note:</strong> For the commands given in the Bandit hints, you can type in man [command_name] or help
    [command_name] to read the documentation on its options and how to use it. Or there is always googling. :p
</p>

```bash
man [command_name]

or

help [command_name]
```

<p>The purpose of the bandit war-games is to introduce beginners to Linux and get them familiar with its command line.
    The things learned during these challenges can be applied to OverTheWire's other war-games and CTFs. Note that for
    some levels there are multiple approaches and commands to get the credentials and in this walkthrough, you'll see
    what I did.
</p>
<br>
<p align="center"> <img
        src="https://user-images.githubusercontent.com/70291944/183759480-db061ce1-25a7-4054-a1b1-b0add1582407.png"
        width="100%" height="100%"> </p>
<br>

<!-- Table of Contents -->
<h2 id="table">Table of Contents</h2>
<ul>
    <li> <a href="#level_0">Level 0: SSH login</a> </li>
    <li> <a href="#level_0-1">Level 0 → 1: List and concatenate</a> </li>
    <li> <a href="#level_1-2">Level 1 → 2: Concatenate files with dash in name</a> </li>
    <li> <a href="#level_2-3">Level 2 → 3: Concatenate files with spaces in name</a> </li>
    <li> <a href="#level_3-4">Level 3 → 4: List hidden files</a> </li>
    <li> <a href="#level_4-5">Level 4 → 5: checking file content type</a> </li>
    <li> <a href="#level_5-6">Level 5 → 6 : Finding files using parameters</a> </li>
    <li> <a href="#level_6-7">Level 6 → 7 : Finding files with user and group parameters</a> </li>
    <li> <a href="#level_7-8">Level 7 → 8: Finding text within file</a> </li>
    <li> <a href="#level_8-9">Level 8 → 9 : Finding unique lines</a> </li>
    <li><a href="#level_9-10">Level 9 → 10: Searching for readable strings</a></li>
    <li><a href="#level_10-11">Level 10 → 11: Decoding base64 inputs</a></li>
    <li><a href="#level_11-12">Level 11 → 12: Decrypting with tr</a></li>
    <li><a href="#level_12-13">Level 12 → 13: Decompressing gzip, bzip2, tar</a></li>
    <li><a href="#level_13-14">Level 13 → 14: SSH login with SSH keys</a></li>
    <li><a href="#level_14-15">Level 14 → 15: Netcat connection</a></li>
    <li><a href="#level_15-16">Level 15 → 16: Port connection with SSL encryption</a></li>
    <li><a href="#level_16-17">Level 16 → 17: Portscanning with Nmap</a></li>
</ul>

<!-- Level 0: Section Beginning -->
<h2 id="level_0">Level 0: SSH login</h2>
<p>The goal of this level is for you to log into the game using SSH. The host to which you need to connect is
    bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go
    to the Level 1 page to find out how to beat Level 1.
<p>
<h3>Notes:</h3>
<p>SSH(Secure Shell):</p>
<ul>
    <li>Allows us to remotely execute commands on another device or server</li>
    <li>Data sent between the two devices are encrypted when sent over a network</li>
</ul>
<p>SSH Login Format:</p>
<ul>
    <li>ssh [options] user@host_ip</li>
    <li>ssh user@host_ip [options]</li>
</ul>

```bash
ssh [options] [user]@[host_ip]
or
ssh [user]@[host_ip] [options]

To see ssh options:
man ssh
```
<h3>Solution:</h3>
<p>To log into the game server, I log into ssh, using the format above. My user would be bandit0 and my host would be
    bandit.labs.overthewire.org. Since a port is specified in the directions, I used the -p flag to specify the host
    port I want to log in to.
</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183810241-9a5ffec1-7789-40ca-a3d5-c74ccad931b5.png"
        width="100%" height="100%">
</p>
<h3>Resources</h3>
<p>SSH command options and background info:
    <a href="https://www.ssh.com/academy/ssh/command">https://www.ssh.com/academy/ssh/command</a>
    <br>More SSH info:
    <a href="https://www.ssh.com/academy/ssh/command">https://www.ssh.com/academy/ssh/command</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 0: Section End -->

<!-- Level 0-1: Section Beginning -->
<h2 id="level_0-1">Level 0 → 1: List and concatenate</h2>
<p>
    The password for the next level is stored in a file called readme located in the home directory. Use this password
    to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that
    level and continue the game.
</p>
<h3>Notes:</h3>
<p>
    ls : command is used to list files and directories <br />
    cat : command is generally used to read and output file contents on the terminal. It is a versatile command as it
    allows users to copy, concatenate, create, and append files <br />
    Format:
</p>

```bash
ls:
ls [options]

cat:
cat [options] [filename]
```

<h3>Solution:</h3>
<p>First thing I did is take a look at what is in my current directory, using ls to list all the files and directories
    in it. I notice that there is a read me and display its contents using cat</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183810363-a49d9a85-cc44-4d50-bd56-58880065200b.png"
        width="100%" height="100%" />
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>
        Username: bandit1 <br />
        Password:boJ9jbbUNNfktd78OOpsqOltutMc3MY1
    </p>
</details>
<h3>Resources</h3>
<p>
    cat command documentation, flags, examples, and uses:
    <a
        href="https://www.cyberciti.biz/faq/linux-unix-appleosx-bsd-cat-command-examples/">https://www.cyberciti.biz/faq/linux-unix-appleosx-bsd-cat-command-examples/</a>
    <br>
    ls command documentation, flags, examples, and uses:
    <a
        href="https://www.ibm.com/docs/zh/aix/7.1?topic=l-ls-command">https://www.ibm.com/docs/zh/aix/7.1?topic=l-ls-command</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 0-1: End -->

<!-- Level 1-2: Section Beginning -->
<h2 id="level_1-2">Level 1 → 2: Concatenate files with dash in name</h2>
<p>The password for the next level is stored in a file called - located in the home directory</p>
<h3>Notes:</h3>
<p>There are multiple ways to display contents of file named “-”:</p>

```bash
Delimiting:
cat ./[filename]

Redirection:
cat < [filename] 
```

<h3>Solution:</h3>
<p>First thing I did is take a look at what is in my current directory, using ls to list all the files and
    directories in it. I notice that there is a read me and display its contents using cat
</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183809716-3113a8cd-0ad8-4c4a-b781-1d3164058efb.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit2
        <br>Password:CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
    </p>
</details>
<h3>Resources</h3>
<p>Working with file named with a dash "-" :
    <a
        href="https://www.webservertalk.com/dashedfilename#:~:text=Open%20and%20Read%20Filename%20Starting%20with%20Dash&text=Try%20'cat%20%2D%2Dhelp'%20for,before%20the%20dash%20(%2D)%20file.&text=cat%20%3C%20%2Dfilename-,You%20should%20get%20the%20following,Hi%20How%20Are%20You%3F">https://www.webservertalk.com/dashed-filename</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 1-2: Section End -->

<!-- Level 2-3: Section Beginning -->
<h2 id="level_2-3">Level 2 → 3: Concatenate files with spaces in their names</h2>
<p>The password for the next level is stored in a file called spaces in this filename located in the home directory
</p>
<h3>Notes:</h3>
<p>Two ways to cat files with spaces in names or special characters:</p>

```bash
Enclose file name in ' ' or " " so it treats the file name as a single string:
cat "filename"
cat 'filename'

Use backslash(\) in front of a special character or space so that the terminal will treat the special character or
space as a normal character:
cat filename\ with\ spaces
```
<h3>Solution:</h3>
<p>I used each of the methods described above to get the flag.</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183816464-a8094911-0424-4433-9dce-d4219bc6b24f.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit3
        <br>Password:UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
    </p>
</details>
<h3>Resources</h3>
<p>Working with files with space in their names :
    <a
        href="https://www.putorius.net/filenames-that-contain-spaces-or.html">https://www.webservertalk.com/dashed-filename</a>
</p>
<!-- Level 2-3: Section End -->

<!-- Level 3-4: Section Beginning -->
<h2 id="level_3-4">Level 3 → 4 : List hidden files</h2>
<p>The password for the next level is stored in a hidden file in the inhere directory.</p>
<h3>Notes:</h3>
<p>Commands used and their formats:</p>

```bash
The -a flag lists all entries in the directory:
ls -a

cd is used to change the current working directory:
cd [file_path or filename if you are already in its directory]
```
<h3>Solution:</h3>
<p>First I moved to inhere using cd to change directories. Then I used ls to see what is in my current directory.
    There appeared to be nothing inside the inhere directory until I used the -a flag to show all entries inside the
    file. Then, I output the file contents for the password.
</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183817525-8ffd5d19-fc0a-4d77-8d31-70d04ebdb1c0.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit4
        <br>Password:pIwrPrtPN36QITSp3EQaw936yaFoFgAB
    </p>
</details>
<h3>Resources</h3>
<p>ls command documentation, flags, examples, and uses:
    <a
        href="https://www.putorius.net/filenames-that-contain-spaces-or.html">https://www.ibm.com/docs/zh/aix/7.1?topic=l-ls-command</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 3-4: Section End -->

<!-- Level 4-5: Section Beginning -->
<h2 id="level_4-5">Level 4 → 5 : Checking file content type</h2>
<p>The password for the next level is stored in the only human-readable file in the inhere directory.
    Tip: if your terminal is messed up, try the “reset” command.
</p>
<h3>Notes:</h3>
<p>Commands used and their formats:</p>

```bash
file format:
file [file_name]

To list file types for all the files in a directory:
file ./*
```
<h3>Solution:</h3>
<p>When I first navigate to the inhere directory and list its contents, there are seven files. To help narrow things
    down when it comes to finding readable files, I use the file command. Based on what the command tells me, only one
    file is in ASCII, which I know includes the alphabet, numbers, and special characters. ASCII is human readable, so this might be
    it. I check the file contents by using cat, and then the password is revealed.
</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183819060-1f9cc834-c2b5-4cfe-a927-92bb9e510364.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit5
        <br>Password:koReBOKuIDDepwhWk7jZC0RTdopnAYKh
    </p>
</details>
<h3>Resources</h3>
<p>file command information, flags, examples, and uses:
    <a href="https://linuxize.com/post/linux-file-command/">https://linuxize.com/post/linux-file-command/</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 4-5: Section End -->

<!-- Level 5-6: Section Beginning -->
<h2 id="level_5-6">Level 5 → 6 : Finding files using parameters</h2>
<p>The password for the next level is stored in a file somewhere under the inhere directory and has all of the
    following properties:</p>
<ul>
    <li>human-readable</li>
    <li>1033 bytes in size</li>
    <li>not executable</li>
</ul>
<h3>Notes:</h3>
<p>Commands used and their formats:
    <br>find: looks for a file based on parameters given in options
    <br>find flags used:
    <br>-readable : find readable files
    <br>-size : find file based on size, format is find -size [file_size][size_suffix]
    <br>-executable : find executable files
    <br>! : put in front of parameter to indicate that you do not want files with that parameter
    <br>To see more parameters and options for the file command, type man find
</p>
<h3>Solution:</h3>
<p>find -readable -size 1033c ! -executable</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183821578-640f5d13-4be6-4b40-afc1-b3e1f5036526.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit6
        <br>Password:DXjZPULLxYr17uwoI01bNLQbtFemEgo7
    </p>
</details>
<h3>Resources</h3>
<p>find command documentation, flags, examples, and uses:
    <a
        href="https://www.ibm.com/docs/en/i/7.4?topic=directories-find">https://www.ibm.com/docs/en/i/7.4?topic=directories-find</a>
    <br>find examples:
    <a
        href="https://www.tecmint.com/35-practical-examples-of-linux-find-command/">https://www.tecmint.com/35-practical-examples-of-linux-find-command/</a>
    <br>find non executable file
    <a
        href="https://stackoverflow.com/questions/70539901/how-can-i-find-all-non-executable-files-in-a-directory-in-linux">https://stackoverflow.com/questions/70539901/how-can-i-find-all-non-executable-files-in-a-directory-in-linux</a>
    <br>find -size suffixes
    <a
        href="https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size">https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 5-6: Section End -->

<!-- Level 6-7: Section Beginning -->
<h2 id="level_6-7">Level 6 → 7 : Finding files with user and group parameters</h2>
<p>The password for the next level is stored somewhere on the server and has all of the following properties:</p>
<ul>
    <li>owned by user bandit7</li>
    <li>owned by group bandit6</li>
    <li>33 bytes in size</li>
</ul>
<h3>Notes:</h3>
<p>Find command flags and formats:</p>

```bash
size flag:
find -size [file_size][size_suffix]

user flags:
find -user [username]

group flags:
find -group [group_name]
```
<h3>Solution:</h3>
<p>For this level we want to search the entire server. To indicate that we find to search the entire server,
    we use / so that find can search the entire server then we set the search parameters using -size
    [file_size][size_suffix],
    -user [username], and -group [group_name]. This helps narrow things down significantly. Notice how
    bandit7.password does not
    have a permission denied, so let’s try outputting the file at that location to see if it has the password.
</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183825278-56b8ed4c-cf4b-48ec-a322-2135ffc47cbb.png"
        width="100%" height="100%">
    <img src="https://user-images.githubusercontent.com/70291944/183825583-b929283b-9bf4-42f6-b44a-12494d99478d.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit7
        <br>Password:HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
    </p>
</details>
<h3>Resources</h3>
<p>find command documentation, flags, examples, and uses:
    <a
        href="https://www.ibm.com/docs/en/i/7.4?topic=directories-find">https://www.ibm.com/docs/en/i/7.4?topic=directories-find</a>
    <br>find examples:
    <a
        href="https://www.tecmint.com/35-practical-examples-of-linux-find-command/">https://www.tecmint.com/35-practical-examples-of-linux-find-command/</a>
    <br>Serverwide search:
    <a href="https://www.cyberciti.biz/faq/how-do-i-search-my-linuxunix-server-for-a-file/
">https://www.cyberciti.biz/faq/how-do-i-search-my-linuxunix-server-for-a-file/</a>
    <br>find -size suffixes
    <a
        href="https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size">https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 6-7: Section End -->

<!-- Level 7-8: Section Beginning -->
<h2 id="level_7-8">Level 7 → 8: Finding text within file</h2>
<p>The password for the next level is stored in the file data.txt next to the word millionth</p>
<h3>Notes:</h3>
<p>grep : used to find text or strings within a given file</p>

```bash
grep [option] [file]
```
<h3>Solution:</h3>
<p> I used grep “millionth” to search for the line the password is on.</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183827432-06789d77-b08d-4d22-8498-888d3aa9c5a1.png"
        width="100%" height="100%">
    <img src="https://user-images.githubusercontent.com/70291944/183827469-8ede01a2-dba0-43d3-8f3e-bfb530f7a29c.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit8
        <br>Password:cvX2JJa4CFALtqS87jk27qwqGhBM9plV
    </p>
</details>
<h3>Resources</h3>
<p>grep command documentation, flags, examples, and uses:
    <a href="https://www.ibm.com/docs/en/i/7.4?topic=data-grep">https://www.ibm.com/docs/en/i/7.4?topic=data-grep</a>
    <br>grep examples:
    <a
        href="https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/">https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 7-8: Section End -->

<!-- Level 8-9: Section Beginning -->
<h2 id="level_8-9">Level 8 → 9 : Finding unique lines</h2>
<p>The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
</p>
<h3>Notes:</h3>
<p>Uniq can be used to find duplicate lines or unique ones. Though does not detect duplicate lines if they are not
    adjacent to
    each other, so you may have to sort first for better results.
    <br>
    <br>| (pipe) : redirects, it sends the output of a command to another destination
</p>
<h3>Solution:</h3>
<p>I first sorted the data.txt so that uniq would work better if the duplicate lines are not adjacent to each other
    and then
    piped the output to uniq -u to find the unique line.
</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183829087-dc0d6b9f-748f-47c7-993b-9f6216150d7b.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit9
        <br>Password:UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
    </p>
</details>
<h3>Resources</h3>
<p>Uniq flags and examples:
    <a href="https://www.redhat.com/sysadmin/uniq-command-lists">https://www.redhat.com/sysadmin/uniq-command-lists</a>
    <br>Pipe :
    <a href="https://www.geeksforgeeks.org/piping-in-unix-or-linux/#:~:text=A%20pipe%20is%20a%20form,program%2Fprocess%20for%20further%20processing
">https://www.geeksforgeeks.org/piping-in-unix-or-linux/</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 8-9: Section End -->

<!-- Level 9-10: Section Beginning -->
<h2 id="level_9-10">Level 9 → 10: Searching for readable strings</h2>
<p>The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded
    by several ‘=’ characters.</p>
<h3>Notes:</h3>
<p>strings: retrieves any printable strings
    <br>
    <a href="#level_7-8">Look at notes and resources for 7 → 8 for info on grep</a>
</p>
<h3>Solution:</h3>
<p>I first outputted data.txt to get an idea of the file contents. Then, for searching, I outputted data.txt and had
    strings retrieve all the printable strings and then searched through all the printable strings for instances of
    =
    to locate the password.
</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183837809-2166c09c-6f26-4f4d-90ef-607521e9d1cf.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit10
        <br>Password:truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
    </p>
</details>
<h3>Resources</h3>
<p>String command, how to use, examples:
    <a
        href="https://www.howtogeek.com/427805/how-to-use-the-strings-command-on-linux">https://www.howtogeek.com/427805/how-to-use-the-strings-command-on-linux</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 9-10: Section End -->

<!-- Level 10-11: Section Beginning -->
<h2 id="level_10-11">Level 10 → 11: Decoding base64 inputs</h2>
<p>The password for the next level is stored in the file data.txt, which contains base64 encoded data</p>
<h3>Notes:</h3>
<p>What is base64 base64?: binary to a text encoding scheme that represents binary data in an ASCII string format
    <br>The base64 command: base64 encode/decode data and print to standard output
</p>
<h3>Solution:</h3>
<p>I used cat to output the contents of data.txt and piped it to base64 —decode to decode the data</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183838345-1fd81e83-a8c6-48b5-8489-fa157fa96a73.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit11
        <br>Password:IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
    </p>
</details>
<h3>Resources</h3>
<p>Base64 documentation:
    <a href="https://linux.die.net/man/1/base64">https://linux.die.net/man/1/base64</a>
    <br>What is base64:
    <a
        href="https://levelup.gitconnected.com/what-is-base64-encoding-4b5ed1eb58a4?gi=79c7ff3d9347">https://levelup.gitconnected.com/what-is-base64-encoding-4b5ed1eb58a4?gi=79c7ff3d9347</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 10-11: Section End -->

<!-- Level 11-12: Section Beginning -->
<h2 id="level_11-12">Level 11 → 12: Decrypting with tr</h2>
<p>The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z)
    letters have been rotated by 13 positions</p>
<h3>Notes:</h3>
<p>tr: translates, deletes, and squeezes characters from input and outputs the results</p>
<h3>Solution:</h3>
<p>
    Just from the description fo their being rotation by 13 positions, I can guess that the data is encrypted using
    ROT13, so I would use tr to translate that.
    <br>
    <br>I ouputted the file contents and redirected it to tr to translate from rot13 using the parameters described
    in intro to rot13
</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183964319-1531785a-b17a-4fcc-964b-60f68d62cc46.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit12
        <br>Password:5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
    </p>
</details>
<h3>Resources</h3>
<p>tr command:
    <a href="https://linuxize.com/post/linux-tr-command/">https://linuxize.com/post/linux-tr-command/</a>
    <br>Intro to rot13:
    <a
        href="https://medium.com/@piyush.kochhar1/rot13-a-missing-guide-c811427cfe6e">https://medium.com/@piyush.kochhar1/rot13-a-missing-guide-c811427cfe6e</a>
    <br>List to held decode ROT-3 to ROT-25:
    <a
        href="https://www.chmag.in/articles/momsguide/decoding-rot-using-the-echo-and-tr-commands-in-your-linux-terminal/">https://www.chmag.in/articles/momsguide/decoding-rot-using-the-echo-and-tr-commands-in-your-linux-terminal/</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 11-12: Section End -->

<!-- Level 12-13: Section Beginning -->
<h2 id="level_12-13">Level 12 → 13: Decompressing gzip, bzip2, tar</h2>
<p>
    The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been
    repeatedly compressed. For this level it may be useful to
    create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy
    the datafile using cp, and rename it using mv (read the manpages!)
</p>
<h3>Notes:</h3>
<p>For this game, we do not have permission to create files and edit files outside of the /tmp file. In order to
    work with the given text file, we will need to copy it into a directory we make in tmp. You can make a directory
    using mkdir and then copy a file from one place to another using cp. file can be used to find out in what way
    the file was compressed. From there you can look up the gzip, bzip, and tar commands’ decompress flags
    throughout the level. Keep in mind that you will need to rename the files each time so that they have the
    correct file extension for each compress type.
    <br>
    <br>Commands used:
<ul>
    <li>mkdir: makes a new directory</li>
    <li>cp: copies a file</li>
    <li>mv: can be used to move or rename file</li>
    <li>xxd</li>
    <li>tar</li>
    <li>bzip2</li>
    <li>bzip2</li>
</ul>
</p>
<h3>Solution:</h3>
<p>First I made a directory in tmp, so I can work on data.txt from there. This is needed because I do not have
    permission to create files in tmp and the home directory, but I would have permission to create files in the new
    directory.
    <br>
    <br>I copied data.txt into that directory using the format:
</p>
```bash
cp [source_file] [file_you_want_to_copy_contents_to_or_the_path_to_it]
```
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183966219-d05651f9-41a9-4bae-a848-5cfcef74a0bc.png"
        width="100%" height="100%">
</p>
<p>I then reverted the hexdump using xxd and its -r(reverse) flag which would output the reverted version in a file
    I named bandit</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183966755-94584cb7-3212-4402-9919-2db586d8ec3b.png"
        width="100%" height="100%">
</p>
<p>Then I used the file command to see the file contents and how it was compressed</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183971570-188ed1e4-4ae1-4a79-879a-d9293fb1c721.png"
        width="100%" height="100%">
</p>
<p>I see that it is compressed using gzip. Files compressed by gzip have the gz file extension. I added this
    extension by renaming the file using mv:</p>

```bash
mv format : mv [source file name] [new name]
```

<p>Then I unzipped the file using the gzip command and its decode flag(-d):</p>

```bash
gzip format: gzip [options] [file]
```

<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183976125-413e7c92-717d-4aad-b224-a989b05a341e.png"
        width="100%" height="100%">
</p>
<p>After the file is decompressed, I use the file command to see if it is still compressed.</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183976615-22f004d6-c49f-4831-bd59-2b40d38ad065.png"
        width="100%" height="100%">
</p>
<p>After the file is decompressed, I use the file command to see if it is still compressed. I can see that the file
    was compressed using bzip2. So, I would need to repeat the process I used to uzip the file when it was
    compressed using gzip, except there would be a few minor changes. I would need to change the file name extension
    to bz2 and I would unzip it using the bzip2 command and its -d(decode) flag. The bzip2 command format is about
    the same as the gzip command format</p>

```bash
bzip2 format:
bzip2 [options] [file]
```

<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183978826-455531d4-f239-47e2-947c-4aa1880fc304.png"
        width="100%" height="100%">
</p>
<p>Then, I checked the contents of bandit again to see if it is still compressed</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183978826-455531d4-f239-47e2-947c-4aa1880fc304.png"
        width="100%" height="100%">
</p>
<p>The file is still compressed using gzip. From here the process to decompress the data is repetitive. You would
    continue the process of checking if the file content is compressed, renaming the file, and then decompressing
    the files until you find data that is not compressed</p>
<p>At some point, you will find notice that the content type is tar, which is an archive file which can contain
    files.</p>

<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183981098-1a2a0ce6-a1e2-49bb-afb4-3da89aa90bb9.png"
        width="100%" height="100%">
</p>

<p> You will need to extract a file from bandit by renaming the file to have the tar extension and then extracting
    using tar -x. I used the -v flag for verbose and -f for file. </p>

```bash
tar format:
tar [options] [filename]

Note: For commands, you can combine the single character flags instead of typing them out individually
tar -x -v -f [filename]
is the same as
tar -xvf
```

<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183984976-27bc446b-35f2-4d2f-b0bf-beadb543f43f.png"
        width="100%" height="100%">
</p>
<p>The rest of this challenge is reptitive. From here you go back to checking if the file is compressed and renaming
    and decompressing the file if it is still decompressed. Repeat this until you finally get ASCII when you use
    file to check the file contents. From there, cat the file to see the credentials</p>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183986605-a02c0c83-6670-4df8-9424-579d3f68efc9.png"
        width="100%" height="100%">
</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit13
        <br>8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
    </p>
</details>
<h3>Resources</h3>
<p>xxd:
    <a
        href="https://www.tutorialspoint.com/unix_commands/xxd.htm">https://www.tutorialspoint.com/unix_commands/xxd.htm</a>
    <br>tar:
    <a
        href="https://linuxize.com/post/how-to-extract-unzip-tar-gz-file">https://linuxize.com/post/how-to-extract-unzip-tar-gz-file</a>
    <br>bz2:
    <a
        href="https://www.tecmint.com/linux-compress-decompress-bz2-files-using-bz">https://www.tecmint.com/linux-compress-decompress-bz2-files-using-bz</a>
    <br>gzip:
    <a href="https://linuxize.com/post/gzip-command-in-linux/">https://linuxize.com/post/gzip-command-in-linux/</a>
    <br>mv:
    <a
        href="https://www.geeksforgeeks.org/mv-command-linux-examples/">https://www.geeksforgeeks.org/mv-command-linux-examples/</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 12-13: Section End -->

<!-- Level 13-14: Section Beginning -->
<h2 id="level_13-14">Level 13 → 14: SSH login with SSH keys</h2>
<p>The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For
    this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next
    level. Note: localhost is a hostname that refers to the machine you are working on
</p>
<h3>Notes:</h3>
<p>An ssh key can be used instead of a password. It works similar to an id as the cryptographic keys are stored in a
    text file that cannot be read or edited by anyone else.
</p>

```bash
ssh authentication key login format:
ssh -i [authentication key] [user]@[host]
```

<h3>Solution:</h3>
<p align="center">
    <img src="https://user-images.githubusercontent.com/70291944/183989575-9abf49c9-4931-4a17-946c-043fb20572ad.png"
        width="100%" height="100%">
</p>
<p>Note: Save the password you find in bandit14</p>
<details>
    <summary><strong>Click here to reveal level credentials:</strong></summary>
    <p>Username: bandit14
        <br>Password:use the sshkey.private
        <br>Note: Save this password: 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
    </p>
</details>
<h3>Resources</h3>
<p>tr command:
    <a href="https://linuxize.com/post/linux-tr-command/">https://linuxize.com/post/linux-tr-command/</a>
    <br>Intro to rot13:
    <a
        href="https://medium.com/@piyush.kochhar1/rot13-a-missing-guide-c811427cfe6e">https://medium.com/@piyush.kochhar1/rot13-a-missing-guide-c811427cfe6e</a>
    <br>List to held decode ROT-3 to ROT-25:
    <a
        href="https://www.chmag.in/articles/momsguide/decoding-rot-using-the-echo-and-tr-commands-in-your-linux-terminal/">https://www.chmag.in/articles/momsguide/decoding-rot-using-the-echo-and-tr-commands-in-your-linux-terminal/</a>
</p>
<br>
<a href="#table">Go back to table of contents</a>
<!-- Level 11-12: Section End -->

<!-- Take user to top -->
<hr>
<a href="#top">Go back to the top</a>
