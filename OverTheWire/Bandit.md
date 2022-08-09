
<h1>Bandit Writeup</h1>

Link to the site :
<a href="https://overthewire.org/wargames/bandit">https://overthewire.org/wargames/bandit</a>

<p><strong>Note:</strong> For most of the commands given in the Bandit hints, you can type in man [command_name] to
  read the documentation on its options and how to use it. Or there is always googling. :p </p><br>

<p align = "center">
<img src="https://user-images.githubusercontent.com/70291944/183759480-db061ce1-25a7-4054-a1b1-b0add1582407.png" width="100%" height="100%">
</p>

<!-- Table of Contents -->
<h2 id="TOC">Table of Contents</h2>
<ul>
  <li>
    <a href="#level0">Level 0: SSH login</a>
  </li>
  <li>
    <a href="#level0-1">Level 0 → 1: List and concatenate</a>
  </li>


<!-- Level 0 -->
<h2 id="level0">Level 0: SSH login</h2>
<p>The goal of this level is for you to log into the game using SSH. The host to which you need to connect is 
  bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the 
  Level 1 page to find out how to beat Level 1.<p>
  
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

<h3>Solution:</h3>
<p>To log into the game server, I log into ssh, using the format above. My user would be bandit0 and my host would be 
  bandit.labs.overthewire.org. Since a port is specified in the directions, I used the -p flag to specify the host port I want to log in to.
</p>
<p align = "center">
<img src="https://user-images.githubusercontent.com/70291944/183766584-5ecbb880-cc4b-4777-8fe8-def9991494a7.png" width="100%" height="100%">
</p>

<h3>Resources</h3>
<p>SSH command options and background info:
  <a href="https://www.ssh.com/academy/ssh/command">https://www.ssh.com/academy/ssh/command</a>
</p>
<p>More SSH info:
  <a href="https://www.ssh.com/academy/ssh/command">https://www.ssh.com/academy/ssh/command</a>
</p>

<!-- Level 0-1 -->
<h2 id="level0-1">Level 0 → 1: List and concatenate</h2>
<p>The password for the next level is stored in a file called readme located in the home directory. Use this password to
log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
</p>
  
<h3>Notes:</h3>
<p>ls : command is used to list files and directories
<br>cat : command is generally used to read and output file contents on the terminal. It is a versatile command as it allows users to copy,
concatenate, create, and append files
</p>

<h3>Solution:</h3>
<p>First thing I did is take a look at what is in my current directory, using ls to list all the files and directories in it. I notice that
 there is a read me and display its contents using cat
</p>
<p align = "center">
<img src="https://user-images.githubusercontent.com/70291944/183774429-d7323e8f-01d5-40a4-bce0-585d09d966b1.png" width="100%" height="100%">
</p>
<details>
  <summary><strong>Click here to reveal level credentials:<strong></summary>
  <p>Username: bandit1
    <br>Password:boJ9jbbUNNfktd78OOpsqOltutMc3MY1
  </p>
</details>

<h3>Resources</h3>
<p>cat command documentation, flags, examples, and uses:
  <a href="https://www.cyberciti.biz/faq/linux-unix-appleosx-bsd-cat-command-examples/">https://www.cyberciti.biz/faq/linux-unix-appleosx-bsd-cat-command-examples/</a>
</p>
<p>ls command documentation, flags, examples, and uses:
  <a href="https://www.ibm.com/docs/zh/aix/7.1?topic=l-ls-command">https://www.ibm.com/docs/zh/aix/7.1?topic=l-ls-command</a>
</p>
  
 <!-- Level 1-2 -->






