# Web stack debugging :page_with_curl: 0x0D-web_stack_debugging_0

## About this project:
In this project, I learned about debugging web stacks.
Being able to debug a webstack is essential for a Full-Stack Software Engineer, 
and it takes practice to be a master of it.
In this debugging series, broken/bugged webstacks was given to me in isolated containers, using the popular Docker.
The final goal is to come up with a Bash script that once executed, will bring the webstack to a working state. 
But before writing this Bash script, you should figure out what is going on and fix it manually.

## Task files description:

Be sure to read the Docker concept page
In this first debugging project, you will need to get Apache to run on the container and to return a page containing Hello Holberton when querying the root of it.

Example:
```
vagrant@vagrant:~$ docker run -p 8080:80 -d -it holbertonschool/265-0
47ca3994a4910bbc29d1d8925b1c70e1bdd799f5442040365a7cb9a0db218021
vagrant@vagrant:~$ docker ps
CONTAINER ID        IMAGE                   COMMAND             CREATED             STATUS              PORTS                  NAMES
47ca3994a491        holbertonschool/265-0   "/bin/bash"         3 seconds ago       Up 2 seconds        0.0.0.0:8080->80/tcp   vigilant_tesla
vagrant@vagrant:~$ curl 0:8080
curl: (52) Empty reply from server
vagrant@vagrant:~$
```

Here we can see that after starting my Docker container, I curl the port 8080 mapped to the Docker container port 80, it does not return a page but an error message. Note that you might also get the error message curl: (52) Empty reply from server.

```
vagrant@vagrant:~$ curl 0:8080
Hello Holberton
vagrant@vagrant:~$
```

After connecting to the container and fixing whatever needed to be fixed (here is your mission), you can see that curling port 80 return a page that contains Hello Holberton. Paste the command(s) you used to fix the issue in your answer file.

* [0-give_me_a_page](./0-give_me_a_page): A file containing the command used to fix the issue.