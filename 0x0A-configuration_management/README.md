# Configuration management :page_with_curl: 0x0A-configuration_management

## About this project:
In this project i learnt and practiced:
- configuration management with puppet.
- Writing puppet manifest files to create a file, install a
  package, and execute a command.

## Task files description:

* [0-create_a_file.pp](./0-create_a_file.pp): Puppet manifest file that
  creates a file `holberton` in the `/tmp` directory.
    * File permissions: `0744`.
    * File group: `www-data`.
    * File owner: `www-data`.
    * File content: `I love Puppet`.

* [1-install_a_package.pp](./1-install_a_package.pp): Puppet manifest file
  that install puppet-lint version 2.1.1.

* [2-execute_a_command.pp](./2-execute_a_command.pp): Puppet manifest file
  that kills the process `killmenow`. 
