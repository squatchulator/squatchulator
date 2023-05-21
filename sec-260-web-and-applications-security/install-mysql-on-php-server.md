---
description: 4/17/2023
---

# Install MySQL on PHP Server

### On a server with PHP installed,

* Install MySQL: `yum install php-mysql`
* Ensure server has an IP and is connected
* Install MariaDB, a community-run fork of MySQL: `yum install mariadb-server mariadb`
* `systemctl start mariadb` and `systemctl enable mariadb.service`
* Run `mysql_secure_installation` to finish. Set a new password, and answer all with Y.
* Run `yum install php php-mysql`
* Restart Apache `systemctl restart httpd.service`
* Create a new file in the webroot directory `nano /var/www/html/info.php`
* Add the following: `<?php phpinfo(); ?>`
* Save and close, and navigate to `http://server-ip/info.php`
