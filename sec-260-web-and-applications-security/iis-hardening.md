---
description: 3/30/2023
---

# IIS Hardening

### SSL Setup

* Click on web server and go to Server Certificates
* Select Create Self-Signed Certificate if no signed certificate to use
* Navigate to sites -> your website, right click, and select Bindings
* Add, set type to https, use your IP, and set a hostname if you like.
* Restart server

### Request Filtering

* Navigate to your site and click Request Filtering
* Add/Block certain file extensions, HTTP headers, header contents, or query strings.

### User Authentication (Basic Authentication)

* Navigate to Authentication
* Disable Anonymous Authentication MIME Type Filtering
