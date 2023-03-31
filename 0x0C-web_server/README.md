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

* [1-install_nginx_web_server](./1-install_nginx_web_server): Bash script
  that configures a new Ubuntu machine with Nginx.
  * Nginx listens on port 80.
  * When querying Nginx at its root `/` with a `curl` GET request,
  it returns a page containing the string `Hello World`.

* [2-setup_a_domain_name](./2-setup_a_domain_name): A text file containing
  the domain name set up for the server at .TECH DOMAIN

* [3-redirection](./3-redirection): Bash script that configures a new Ubuntu
  machine with Nginx.
  * Setup is identical to [1-install_nginx_web_server](./1-install_nginx_web_server)
  plus:
    * The location `/redirect_me` returns a `301 Moved Permanently` redirection
    to another page.

* [4-not_found_page_404](./4-not_found_page_404): Bash script that configures
  a new Ubuntu machine with Nginx.
  * Setup is identical to [1-install_nginx_web_server](./1-install_nginx_web_server)
  plus:
    * Features a custom 404 page containing the string `Ceci n'est pas une page`.

* [7-puppet_install_nginx_web_server.pp](./7-puppet_install_nginx_web_server.pp): Puppet manifest that configures a new Ubuntu machine with Nginx.
  * Nginx listens on port 80.
  * When querying Nginx at its root `/` with a `curl` GET request,
  it returns a page containing the string `Hello World`.
  * The redirection must be a “301 Moved Permanently”