# Web server :page_with_curl: 0x0C-web_server

## About this project:

In this project i learnt and practiced:

- What is the main role of a web server
- What is a child process
- Why web servers usually have a parent process and child processes
- What are the main HTTP requests
- How to use `scp` and `Fabric` to transfer files to my server.
- Configure a web server using `Nginx` and `Puppet`.

* [0-transfer_file](./0-transfer_file): Bash script that transfers a file
  from client to a server.
  * Accepts four arguments:
    * The path of the file to be transferred.
    * The IP of the server to transfer the file to.
    * The username that `scp` connects with.
    * The path of the SSH privtae key that `scp` uses.
  * Display Usage: 0-transfer_file PATH_TO_FILE IP USERNAME PATH_TO_SSH_KEY if less than 3 parameters passed
  * `scp` transfers the file to the user home directory `~/`.
