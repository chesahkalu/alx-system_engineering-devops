# Shell, init files, variables and expansions :page_with_curl: 0x03-shell_variables_expansions
## About this project:
In this project i learnt and practiced Shell init files, variables and expansions,
#### General
- What happens when you type `$ ls -l *.txt`
#### Shell Initialization Files
- What are the `/etc/profile` file and the `/etc/profile.d` directory
- What is the ~/.bashrc file
#### Variables
- What is the difference between a local and a global variable
- What is a reserved variable
- How to create, update and delete shell variables
- What are the roles of the following reserved variables: HOME, PATH, PS1
- What are special parameters
- What is the special parameter `$?`?
#### Expansions
- What is expansion and how to use them
- What is the difference between single and double quotes and how to use them properly
- How to do command substitution with `$()` and backticks
#### Shell Arithmetic
- How to perform arithmetic operations with the shell
#### The alias Command
- How to create an alias
- How to list aliases
- How to temporarily disable an alias
#### Others
- How to execute commands from a file in the current shell
## Tasks file descriptions;
  * [0-alias](./0-alias): Bash script that creates an alias named `ls` with value `rm *`.

  * [1-hello_you](./1-hello_you): Bash script that prints `hello user`, where user is the
  current Linux user.

  * [2-path](./2-path): Bash script that adds `/action` to the `PATH`.

  * [3-paths](./3-paths): Bash script that counts the number of directories in the `PATH`.

  * [4-global_variables](./4-global_variables): Bash script that lists environment variables.

  * [5-local_variables](./5-local_variables): Bash script that lists all local variables,
  environment variables and functions.

  * [6-create_local_variable](./6-create_local_variable): Bash script that creates
  a new local variable named `BETTY` with value `Holberton`.

  * [7-create_global_variable](./7-create_global_variable): Bash script that
  creates a new global variable named `HOLBERTON` with value `Betty`.

  * [8-true_knowledge](./8-true_knowledge): Bash script that prints the result of the
  addition of 128 with the value stored in the environment variable
  `TRUEKNOWLEDGE`, followed by a new line.

  * [9-divide_and_rule](./9-divide_and_rule): Bash script that prints the result
  of `POWER` divided by `DIVIDE`. `POWER` and `DIVIDE` are environment variables.

  * [10-love_exponent_breath](./10-love_exponent_breath): Bash script that displays the
  result of `BREATH` to the power of `LOVE`. `BREATH` and `LOVE` are environment variables.

  * [11-binary_to_decimal](./11-binary_to_decimal): Bash script that converts a number
  in base 2 stored in the environment variable `BINARY` to base 10.

  * [12-combinations](./12-combinations): Bash script that prints all possible combinations
  of two letters, except `oo`, as follows:
    * Letters are lower cases, from `a` to `z`.
    * One combination per line.
    * Alpha-ordered.

  * [13-print_float](./13-print_float): Bash script that prints a number stored in the
  environment variable `NUM` with two decimal places.

  * [100-decimal_to_hexadecimal](./100-decimal_to_hexadecimal): Bash script
  that converts a number in base 10 stored in the environment variable `DECIMAL` to base 16.
  
  * [101-rot13](./101-rot13): Bash script that encodes and decodes text using the rot13
  encryption.

  * [102-odd](./102-odd): Bash script that prints every other line from the input,
  starting with the first line.

  * [103-water_and_stir](./103-water_and_stir): Bash script that adds the two numbers
  stored in the environment variables `WATER` and `STIR` and prints the result.
  * `WATER` is in base `water`, `STIR` is in base `stir`, and the result is
  in base `behlnort`.
