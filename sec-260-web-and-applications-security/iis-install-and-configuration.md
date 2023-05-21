---
description: 3/23/2023
---

# IIS Install and Configuration

### Install IIS on Windows Server

* In Server Manager, select Dashboard and Add Roles and Features
* Make sure Role-Based or Feature Based Installation is selected
* Select your server from the server pool
* On the Select Server Roles page select Web Server (IIS) (Select Include Management Tool)
* On Select Role Services page, add security options as necessary
* Visit your IP in a browser to check if it installed correctly

### Add a Website to IIS

* Open IIS Manager and right click the Sites node under the dropdown in the Connections pane
* Click Add Website, and enter a friendly name in the Site Name box
* In the Physical Path box, navigate to `C:\inetpub` and make a new folder for your site
* Accept defaults for the server to run on port 80 and make sure Start Website Immediately is checked
  * Accept warning for duplicate binding, we are disabling the default homepage anyway
* Click default webpage and click stop, and start your new webpage.

### Configure Anonymous Authentication

* Go to the home view of IIS and click Authentication
* Select Anonymous Authentication and click Edit in the Actions pane
* In Edit Anonymous Authentication Credentials, select Application Pool Identity

### Set "Default Document"

* Open Notepad as admin and write some text to a file
* Save file to `C:\inetpub\your-site.html`
* Go to IIS manager and go to Default Document, and add the filename for your new document.
* Restart server and site should display your text.
