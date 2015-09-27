# Day 2: Security

While many general Web tutorials talk about Security as one of the last subjects, for us it is the most important topic after the Installation! 

Before you do anything else, you have to make sure that your Website is secure!

We would like to point you again to the [**XOOPS Installation process**](https://www.gitbook.com/book/xoops/xoops-installation-guide/), where in [**Appendix 5**](https://xoops.gitbooks.io/xoops-installation-guide/content/book/appendix5.html), you will learn how to make your Website more secure.

The most important task for you is to **install Protector module**! 

#### XOOPS Protector
The XOOPS Protector Module protects from DOS, SQL injection, and a number of other related attacks. This is a must-install module. As of XOOPS 2.3.x, it's included in the Core installation files, but you will want to get the latest and keep it updated.

##### Features
This module can help protect you XOOPS Website from the following vulnerabilities
* DoS
* Bad Crawlers (like bots collecting e-mails...)
* SQL Injection
* XSS (not all though)
* System globals pollution
* Session hi-jacking
* Null-bytes
* Directory Traversal
* Some kind of CSRF (fatal in XOOPS <= 2.0.9.2)
* Brute Force
* Camouflaged Image File Uploading (== IE Content-Type XSS)
* Executable File Uploading Attack
* XMLRPC's eval() and SQL Injection Attacks
* SPAMs for comment, trackback etc.

**Installation**

***Fresh Install***

Install the module per standard XOOPS module installation using the administration console.

**Upgrade**

There may be some files in the TRUST_PATH files that you may want to keep. Do a diff to make sure before you upgrade and lose defined filters and such. And/or backup a copy of the files as usual. Otherwise, copy the files to the modules and trusted path and then update the module in the administrator. This pertains to any upgrade from version 3.0 to current. Upgrades from version 2.0 to current requires some changes to the mainfile inserts as the file organization changed.

**Configuration**

Set the preferences as desired. Check out the Security Advisory in the administration section of the module. Make changes as appropriate (this may have undesired effects on modules). If you use phpsuexec or suphp, you won't be able to implement the .htaccess solution suggested by this module. Most well-performing sites now use one or the other of these.

**Recovery**

Banned IPs are kept in TRUST_PATH/modules/protector/configs/badipsXXXX. If you get locked out, edit/delete this as appropriate.
