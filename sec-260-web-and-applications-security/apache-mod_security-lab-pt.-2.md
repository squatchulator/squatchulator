---
description: 3/20/2023
---

# Apache mod\_security Lab (pt. 2)

### Common Attack Type Protection

### XSS Attack:

* Open browser and request a URL with your server IP like: `http://192.168.1.1/??<script>XSS_Attack</script>`
* Check `/var/log/httpd/modsec_audit.log`. mod\_security should block this request since it contains the `<script>` tag.

### Directory Traversal Attack:

* Open browser and request a URL with your server IP like: `http://192.168.1.1/?../../boot`
* Check `/var/log/httpd/modsec_audit.log`. mod\_security should block this request since it contains directory traversal.

### Telnet Web Client:

* `telnet localhost 80`
  * `GET / HTTP/1.1`
  * `Host: sitename.com`
