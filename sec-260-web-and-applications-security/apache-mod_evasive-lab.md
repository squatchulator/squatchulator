---
description: 3/20/2023
---

# Apache mod\_evasive Lab

### Install VBox Guest Additions on RedHat

* `yum -y install epel-release`
* `yum -y update`
* `yum install make gcc kernel-headers kernel-devel perl dkms bzip2`
* `export KERN_DIR=/usr/src/kernels/$(uname -r)`
* `mount -r /dev/cdrom /media`
* `cd /media/`
* `./VBoxLinuxAdditions.run`

### Install Apache mod\_evasive

* `sudo rpm -ivh http://download-ib01.fedoraproject.org/pub/epel/7/x86_64/Packages/m/mod_evasive-1.10.1-22.el7.x86_64.rpm OR yum install epel-release`
* (Verify the EPEL repo is running) `yum repolist`
* `sudo yum install mod_evasive -y` Verifying Apache mod\_evasive
* `ls -al /etc/httpd/conf.d/mod_evasive.conf`
  * Should look like `-rw-r--r-- 1 root root 3473 Jul 21 01:41 /etc/httpd/conf.d/mod_evasive.conf`
* `cat /etc/httpd/conf.d/mod_evasive.conf`
  * Should have line on the top containing: `LoadModule evasive20_module modules/mod_evasive24.so`
* `sudo httpd -M | grep evasive` should output: `evasive20_module (shared)`
* Restart httpd Testing Apache mod\_evasive
* `yum install -y perl`
* Run the test script at: `perl /usr/share/doc/mod_evasive-1.10.1/test.pl`
  * Will output `HTTP/1.1 403 Forbidden` if successful. This indicates access is denied by the web server. Logs accessible by `tail /var/log/messages`
    * Output should look similar to this: `Jul 29 00:11:18 servername mod_evasive[18290]: Blacklisting address 127.0.0.1: possible DoS attack.`
  * If the error is a 400, Apache may be expecting a host header. Change `/n/n` in the script to `/r/n/r/n` and it should work properly.
  * You can also update to HTTP/1.1 by adding host header to HTTP request in script: `HTTP/1.1\r\nHost:test.co\r\n\r` Customizing Apache mod\_evasive
* `nano /etc/httpd/conf.d/mod_evasive.conf`
  * `DOSPageCount` sets a threshold of how many times a client IP can load a single page during the `DOSPageInterval`
    * Default page count is 2
    * Changing `DOSPageInterval` from 1 second to X seconds means that reloading the page more than twice in X seconds will blacklist the IP. It will only block this IP for 10 seconds by default (`DOSBlockingPeriod`)
  * `DOSSiteCount`
    * Same as `DOSPageCount`, but for the entire web server rather than an single site on the web server. Managed likewise with `DOSSiteInterval`.
  * `DOSBlockingPeriod`
    * Specifies the length of time (in seconds) that mod\_evasive will block requests from a client IP address after it has been detected as exceeding the `DOSSiteCount` or `DOSPageCount` limits.
    * Restart httpd
