# LOAD BALANCER :page_with_curl: 0x0F-load_balancer

## About this project:

- In this project, I learned about load balancers and how to configure them in a web stack
- Setting up a second `web-02` web server cluster identical to `web-01`. 
- Setting up a third `lb-01` webserver and configuring a load balancer to distribute traffic between the two web servers using  Haproxy round-robin algorithm.

## Task files description:

 * [0-custom_http_response_header](./0-custom_http_response-header): Bash
  script that installs and configures Nginx on a server with a custom HTTP
  response header.
    * The name of the HTTP header is `X-Served-By`.
    * The value of the HTTP header is the hostname of the server.
    * Other server configurations identical to previous server configurations in project 0x0C-web_server.

* [1-install_load_balancer](./1-install_load_balancer): Bash script that
  installs and configures HAproxy version 1.5 on a server.
    * Enables management via the init script.
    * Requests are distributed using a round-robin algorithm.

* [100-puppet_custom_http_response_header.pp](./100-puppet_custom_http_response_header.pp): Just like the first task, Puppet manifest
   that configures a brand new server :
    * The name of the HTTP header is `X-Served-By`.
    * The value of the HTTP header is the hostname of the server.