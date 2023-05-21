---
description: 3/6/2023
---

# Basic Apache Hardening

### Remove Server Version Banner:

* `cd /etc/httpd/conf`
* `nano httpd.conf` and append the following directive:
  * `ServerTokens Prod`
  * `ServerSignature Off`
* Restart apache

### Disable Directory Browser Listing:

* `mkdir /var/www/html/test`
  * Add two text files containing the words `hi` and `hello`
* Try visiting server IP at: `http://192.168.1.1/test/` and directory listing should be there
* `cd /etc/httpd/conf` and `nano httpd.conf`
* Search for `/var/www/html` directive and change `Options` to None
* Restart apache, and directory listing should be blocked.

### Disable Trace HTTP Request

* Install telnet with `yum -y install telnet`
* `cd /etc/httpd/conf` and `nano httpd.conf`
  * Append the following directive: `TraceEnable off`
* Make a trace request:
  * `telnet localhost 80`
  * `TRACE / HTTP/1.1`
  * `Host: test`
* Restart Apache; telnet requests should be blocked.
