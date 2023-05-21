---
description: 2/16/2023
---

# Configuring HTTPS in Apache

* `cp websrv.crt /etc/pki/tls/certs`
* `cp websrv.key /etc/pki/tls/private`
* `yum -y install mod_ssl`
* `nano /etc/httpd/conf.d/ssl.conf`
  * Change SSLCertificateFile to match `/etc/pki/tls/certs/websrv.crt`
  * Change SSLCertificateKeyFile to match `/etc/pki/tls/private/websrv.key`
* `firewall-cmd --permanent --add-port=443/tcp`
* `firewall-cmd --reload`
* `systemctl restart httpd`
