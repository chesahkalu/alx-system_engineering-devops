# Shell Processes and Signals :page_with_curl: 0x05-processes_and_signals

## About this project:
In this project i learnt and practiced:
- What is a PID
- What is a process
- How to find a process’ PID
- How to kill a process
- What is a signal
- What are the 2 signals that cannot be ignored

## Tasks files description:

  * [0-what-is-my-pid](./0-what-is-my-pid): Bash script that displays its own PID.

  * [1-list_your_processes](./1-list_your_processes): Bash script that displays a
  list of currently running processes.
  * Shows all processes for all users, including those not featuring a TTY.
  * Processes are displayed in a user-oriented hierarchy.

  * [2-show_your_bash_pid](./2-show_your_bash_pid): Bash script that displays lines
  containing the `bash` keyword based on the script defined in `1-list_your_processes`.
  that displays the PID along with the process name of processes who name contains the
  word `bash`.

  * [4-to_infinity_and_beyond](./4-to_infinity_and_beyond): Bash script that displays
  `To infinity and beyond` indefinitely with a `sleep 2` in between each iteration.

  * [5-kill_me_now](./5-kill_me_now): Bash script that kills the
  [4-to_infinity_and_beyond](./4-to_infinity_and_beyond) process using `kill`.

  * [6-kill_me_now_made_easy](./6-kill_me_now_made_easy): Bash script that kills the
  [4-to_infinity_and_beyond](./4-to_infinity_and_beyond) process using `pkill`.

  * [7-highlander](./7-highlander): Bash script that displays `To infinity and beyond`
  indefinitely with a `sleep 2` in between each iteration.
  * Displays `I am invincible!!!` upon receiving a `SIGTERM` signal.

  * [8-beheaded_process](./8-beheaded_process): Bash script that kills the process
  [7-highlander](./7-highlander).

  * [100-process_and_pid_file](./100-process_and_pid_file): Bash script that creates the file
  `/var/run/holbertonscript.pid` containing its PID and displays `To infinity and
  beyond` indefinitely.
  * Displays `I hate the kill command` upon receiving a `SIGTERM` signal.
  * Displays `Y U no love me?!` upon receiving a `SIGINT` signal.
  * Deletes the file `/var/run/holbertonscript.pid` and terminates itself
  upon receiving the `SIGQUIT` or `SIGTERM` signal.

  * [manage_my_process](./manage_my_process): Bash script that writes `I am alive!` to the file
  `/tmp/my_process` indefinitely.
    * Sleeps two seconds in between each write.
  * [101-manage_my_process](./101-manage_my_process): Bash script that manages the
  [manage_my_process](./manage_my_process) script.
  * When passed the argument `start`:
    * Starts [manage_my_process](./manage_my_process).
    * Creates a file containing its PID in `/var/run/my_process.pid`.
    * Displays `manage_my_process started`.
  * When passed the argument `stop`:
    * Stops [manage_my_process](./manage_my_process).
    * Deletes the file `/var/run/my_process.pid`.
    * Displays `manage_my_process stopped`.
  * When passed the argument `restart`:
    * Stops [manage_my_process](./manage_my_process).
    * Deletes the file `/var/run/my_process.pid`.
    * Starts `manage_my_process`.
    * Creates a file containing its PID in `/var/run/my_process.pid`.
    * Displays `manage_my_process started`.
  * Otherwise, displays `Usage: manage_my_process {start|stop|restart}`.

  * [102-zombie.c](./102-zombie.c): C program that creates five zombie processes.
  * For every zombie created, displays `Zombie process created, PID:
  <ZOMBIE_PID>`.
