# Web stack debugging :page_with_curl: 0x17-web_stack_debugging_3

## About :monocle_face:
- Using strace, find out why Apache is returning a 500 error. Once you find the issue, fix it and then automate it using Puppet (instead of using Bash as you were previously doing).

- Hint:
strace can attach to a current running process
You can use tmux to run strace in one window and curl in another one

-Requirements:
Your 0-strace_is_your_friend.pp file must contain Puppet code
You can use whatever Puppet resource type you want for you fix

## Task files description:

  * [0-strace_is_your_friend.pp](./0-strace_is_your_friend.pp): Puppet manifest
  that fixes a typo error causing a WordPress application being served by an Apache
  web server to fail.
  * Usage: `puppet apply 0-strace_is_your_friend.pp`
