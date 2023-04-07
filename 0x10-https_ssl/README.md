# HTTPS SSL :page_with_curl: 0x10-https_ssl
## About this project:
In this project i learnt and practiced:
- What is HTTPS SSL 2 main roles
- What is the purpose encrypting traffic
- What SSL termination means
* [1-world_wide_web](./1-world_wide_web): Bash script that displays
  information about subdomains on my configured servers.
  * Usage: `./1-world_wide_web <domain> <subdomain>`
  * Output: `The subdomain [SUB_DOMAIN] is a [RECORD_TYPE] record and points to [DESTINATION]`
  * If no `subdomain` parameter is passed, displays information about the
  subdomains `www`, `lb-01`, `web-01` and `web-02`, in that order.