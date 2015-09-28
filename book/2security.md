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


## Security Checkpoint

First, we need to be very clear of all the areas that need to be secured:
- the server OS, 
- the web server, 
- the database, 
- PHP, 
- XOOPS (the code), 
- your files and folders, 
- the modules you install and the 
- usernames and passwords on your site.

For every aspect, make sure you are using the latest version that has been patched and 'hardened' for the best security.

**Server OS (operating system)**

Unless you are planning on hosting your site on your own server, you won't have much to say about this. When you find a host, make sure you understand what your host provides and if you will be on a shared server or a dedicated server.

With your hosting account, you will be given some kind of access to manage your account. Be very cautious with your account information! The administrator username will probably be determined by your host, but you can and should set a secure password for this account. Use a combination of letters (uppercase AND lowercase), numbers and symbols to create your password. Please do not use any word or combine words to create your password, either.

Some accounts let also create passwords for administering the databases, allowing FTP access to the site and the email password for the main account. Be sure you have strong passwords for all those types of access to your account.

While you are looking around the access settings for your site, look at the FTP configuration - you definitely need to disable anonymous access. If you do not, anyone can FTP to your server and gain access to your files and folders.

**Web Server**

The most common web server is Apache and it too needs to be secured. Unless you have a dedicated server, you will need to work with your provider for any changes to the configuration of the server. One thing to check with them is the use of mod_security for Apache (see, even Apache has an add-on for security!) 

As an additional precaution, look in your host's control panel to see if you can disable directory listings and make sure it is active. This will prevent the web server from displaying a list of files in a folder if a default page cannot be found.

Most hosting providers will allow you to create a custom set of rules for your site. To put those in place, you create a text file and save it as .htaccess - no filename, just the extension. There is a limit to what you can control this way, but you can certainly improve your security and performance with .htaccess files.

**MySQL and the database**

The biggest part of securing your database is user security. MqSQL has a default administrator of 'root' and also an 'anonymous' user. Be sure your 'root' user has a password, and a strong one, at that. Remove the 'anonymous' user completely! I also recommend creating another user for use on your XOOPS site, giving it only enough permissions to access and use your XOOPS database. Be creative with the username and use a strong password (uppercase, lowercase, numbers and symbols)

If you have control over your database name, be creative, not obvious.

**PHP**

PHP is a programming language, designed to control many operations in your web environment. Knowing that, PHP can expose a lot of vulnerabilities if not properly configured and used.

Again, given your hosting situation, you may have different options, depending on how PHP was installed on your host and which version is installed. The basic, most critical, components of PHP that need attention are register_globals, safe_mode, and allow_url_fopen. The XoopsInfo module will provide you will the status of each of those settings. Green is good, red needs attention!

Some of these can be set using the same .htaccess file for configuring Apache, some will require adding a php.ini file, others will require having your host make the change for you.

**XOOPS**

XOOPS developers always paid a lot of attention to security. They have been responsive to any vulnerabilities discovered and released fixes quickly. XOOPS was, and is still, one of the most secure CMS options available. But, you must be using the latest release on your site! And, you must install the latest version of Protector.

Now, there are some things you can do to make your site vulnerable - pick an administrator username and password that are easy to guess and your site will be compromised. You can have the greatest security system in the world for your home, but if you don't lock the door it is only a matter of time before you are broken into.

There is a [good article](http://xoops-tips.tedliu.ca/modules/news/article.php?storyid=9) about protecting the administrator Admin login by restricting access to specific IP addresses.

**Other things to do:**

Be sure files and folders have the correct permissions (in the [XOOPS FAQs](http://www.xoops.org/modules/smartfaq/faq.php?faqid=82))

Make sure there is an index.html in every folder (also in the XOOPS FAQs)

**Modules**

Just like the core, make sure you are using the latest versions of the modules. The module, XoopsInfo, helps you keep track of this, too. (See why I had you install it?)

**User Security**

If you allow people all over your site and don't limit some activities to trusted people, you will end up with problems later. During our installation steps, we recommend you create another group for the management of the site, separate from the administrator group. Be selective which people are allowed to manage and moderate on your site. Also, be careful about allowing anonymous posts without approval. Don't let anyone create a user called 'user' with a password 'user', stuff like that makes it easy for malicious visitors to mess with you.
