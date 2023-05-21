---
description: 3/2/2023
---

# Virtual Hosts in Apache

### Set up Apache for Virtual Hosts

* Standard Apache setup
* Create `vhosts` webroot:
  * `mkdir /var/www/vhosts`
* Create `/test/html` directory in vhosts webroot as well
  * To test, make a `index.html` file with some text in it.
* `nano /etc/httpd/conf.d/test.conf`
  * Add the following:
  * `<VirtualHost *:80>`
    * `DocumentRoot "/var/www/vhosts/test/html`
    * `ServerName test.com`
    * `ServerAlias www.test.com`
    * `<Directory /var/www/vhosts/test/html>`
      * `AllowOverride All`
      * `Options Indexes FollowSymLinks`
      * `Require all granted`
    * `</Directory>`
  * `</VirtualHost>`
* Restart apache

### Set up Second Virtual Host:

* Repeat steps above using different name instead of 'test'.

### Connect to Different Sites:

* Update DNS names in local hosts file:
  * Windows: `C:\Windows\System32\drivers\etc\hosts`
  * Linux: `/etc/hosts`
    * Append the following, replacing with server's IP and site names:
      * `192.168.1.1 test`
      * `192.168.1.1 test2`
