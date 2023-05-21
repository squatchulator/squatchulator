---
description: 2/16/2023
---

# Certificate Authority in Apache

### Create the Certificate Authority

* `mkdir /etc/pki/CA`
* `yum install openssl`
* `touch index.txt` (CA uses this to keep track of certificates)
* `echo 1000 > serial` (used to assign serial numbers to certificates) Create CA's Private Key
* `openssl genrsa -des3 -out private/cakey.pem 2048` Create Certificate
* `openssl req -new -x509 -days 365 -key private/cakey.pem -out cacert.pem`

### Creating Certificate Request & Send from Web Server:

* `openssl req -newkey rsa:2048 -keyout websrv.key -out websrv.csr`
* `scp websrv.csr user@192.168.1.1:/` (Replace with remote IP)

### Sign the Certificate on the Certificate Authority

* `openssl ca -out websrv.crt -infiles websrv.csr`
* Check that the .crt is signed and looks right with `ls -l` and `cat`
* `scp websrv.crt user@192.168.1.1:/` (Replace with remote IP)
