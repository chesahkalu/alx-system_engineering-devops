# Web stack debugging :page_with_curl: 0x12-web_stack_debugging_2

## About this project :bulb:

In this project, I learned about web stack debugging.

## Tasks files description: :books:

* [0-iamsomeonelese](./0-iamsomeonelese): Bash script that runs the command
  `whoami` under the user passed as argument to find out if the user is the root user
  * Usage: `./0-iamsomeonelese <user>`
  The user root is, on Linux, the “superuser”. It can do anything it wants, that’s a good and bad thing. A good practice is that one should never be logged in the root user, as if you fat finger a command and for example run rm -rf /, there is no comeback. That’s why it is preferable to run as a privileged user, meaning that the user also has the ability to perform tasks that the root user can do, just need to use a specific command that you need to discover.

