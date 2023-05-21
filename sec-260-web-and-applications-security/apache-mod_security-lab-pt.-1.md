---
description: 3/20/2023
---

# Apache mod\_security Lab (pt. 1)

### Techniques used by Core Rules:

* HTTP Protection – detects violations of the HTTP protocol and a locally defined usage policy
* Real-time Blacklist Lookups – utilizes 3rd Party IP Reputation
* Web-based Malware Detection – identifies malicious web content by check against the Google Safe Browsing API.
* HTTP Denial of Service Protections – defends against HTTP Flooding and Slow HTTP DoS Attacks.
* Common Web Attacks Protection – detects common web application attacks
* Automation Detection – Detects bots, crawlers, scanners and other recognizable malicious activity
* Integration with AV Scanning for File Uploads – detects malicious files uploaded through the web application.
* Tracking Sensitive Data – Tracks Credit Card usage and blocks leakages.
* Trojan Protection – Detects access to Trojans horses.
* Identification of Application Defects – alerts on application misconfigurations.
* Error Detection and Hiding – Disguises error messages sent by the server.

### Download and Installation

* Install Apache and add `index.html` to `/var/www/html` (disable testing page as well, you can rename `/etc/httpd/conf.d`)
* `yum install mod_security -y`
* `ll /etc/httpd/conf.d/mod_security.conf`
* `httpd -M | grep security`
  * Should say `security2_module (shared)`
* Restart Apache and verify:
  * `tail /etc/httpd/logs/error_log` Reviewing Configuration and Log Files
* `cat /etc/httpd/conf.d/mod_security.conf`
  * Verify `activated_rules` was created with `cd /etc/httpd/modsecurity.d` and `ll`
  * Also verify that log file is in `/var/log/httpd/modsec_audit.log` Core Ruleset Configuration
* Get custom rulesets from official repo with `yum -y install mod_security_crs`
  * Verify rules are loaded in `/etc/httpd/modsecurity.d/activated_rules`
* Disable `SecRule REQUEST_HEADERS:Host"^[\d.:+$"...` in `/etc/httpd/modsecurity.d/activated_rules/modsecurity_crs_21_protocol_anomalies.conf`
* Restart web server & Apache
