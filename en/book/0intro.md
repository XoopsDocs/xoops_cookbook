## What is XOOPS and what is CMS?

XOOPS is a free tool to manage the content of dynamic Websites. In less than three seconds we’ve sort of defined what this tool does, in what context and at what cost. Have we struck gold? Not really. On one hand, it’s almost certain you already knew this much; on the other, a quick search in the Web reveals that there are at least several hundred tools that offer to do the same job at the same price –and that’s counting only the ones also written in PHP! So there must be additional reasons to explain the appeal of XOOPS in the Internet community. A nice way of finding out implies putting XOOPS in its context, and that’s what this chapter is about. You might be a recent newcomer to the XOOPS world, or a seasoned expert already familiar with this powerful package; either way, you’ll probably find here a few things you didn’t know about, things that, not by accident, are asked once and again in the community forums. You’ll learn here:
* The basics of serving dynamic content to a hungry audience,
* The undocumented and almost forgotten history of XOOPS and some of its peers,
* The specifics about what XOOPS is, and
* Some of its most relevant features, including those that separate XOOPS from seemingly similar solutions.

So, get ready to embark on a short but profitable journey. At the end of this chapter you’ll have a very clear notion of what XOOPS is and what it can do, as a prelude to actually using it to build the website you’ve always wanted to have. Let’s move on.

### If content is king, speed is paramount

Once upon a time, in the early days of the Web, sites used to be slow, ugly and predictable (with the usual exceptions, of course). Each page of each site had been painstakingly written by some heroic designer that, almost with no tools, did whatever was necessary to attract attention. Those were the days of gray backgrounds, blinking lines and static sites, the days of the transparent pixel hack. In terms of the “dialogue” between users and Web sites, the process was linear and simple: the user typed an address (or rather an **URL**, a **Uniform Resource Locator**), and the browser used the Web link to, using the protocol **TCP/IP**, search in the not-yet-really-huge cyberspace for a machine identified by the typed address. That machine was running a program called a Web server, and this program read the details of the address, looked in the machine’s file system, retrieved a few files (an HTML file, perhaps a CSS file and sometimes a few image files), read them and served them, that is, it transmitted those files all the way back to the browser, so that it could interpret and integrate them, and finally display something in the screen. Pure magic!

![](../assets/XoopsIntro1.jpg)

*Figure 1. The flow of pages for a static site.*

Of course, this magic that today we might even consider simplistic, only works well for a limited number of pages, and then if they don’t change that often. But a limited size site which has pages set on stone belongs to the Stone Age, not to the Internet Age. There was little future then for this kind of sites, and there’s even less future for them now, save for a few reference corners in the bowels of the now-really-huge cyberspace. Now the Web has so much dynamic and free information available to so many people that the only way to prosper and be relevant is to keep the pace: you serve a lot of content, good content, live content that keeps changing at the same rhythm as the world. We might say, as the Red Queen in Through the Looking Glass, that “it takes all the running you can do to stay in one place. If you want to get somewhere else, you must run at least twice as fast as that!” This is the dynamic site era, and you know what? It’s here to stay!

In a dynamic site perhaps you’ll find a few static pages. Only they’re probably not physical files residing in the server’s disk, but cached files residing in the server’s memory, ready to be served lightning fast. And many, many pages don’t exist neither physically nor in the cache; they are built on demand, first-asked, first-served, after a browser asks the Web server for them. These are the dynamic pages we’re talking about.

Now, the mission of a Web server is not to build dynamic pages; the server exists solely to deliver HTML pages to all those greedy browsers yelling from every corner of the cyberspace. The server does not care if the pages it delivers come from the file system or are built on-the-fly. As long as they are correctly built, the server happily chugs along, distributing pages here and there as fast as it can. The mission of building those pages is in the hands of a different program, a completely different tool. We’re talking now of a **Content Management System**, or **CMS**.

![](../assets/XoopsIntro2.jpg)

*Figure 2. In a dynamic site, the CMS gives the Web server the requested pages. The CMS either retrieves cached pages (1) or builds the requested pages on-the-fly (2).*

Just as the Web server delivers pages to the browsers, the CMS delivers pages to the Web server. The pages may come from the system’s cache, in which case they are instantly passed to the Web server and then to the requesting browser, or they may be built when the request comes, built by a subsystem of the CMS that joins together page structures and page content to create complete pages.

Now, given the fact that both static and dynamic sites serve pages to the browser, what separates them? Well, content. Or, rather, the possibility of changing the content as often as you might want. In a static site, content is embedded in the pages, and to change the content you need to change the page. In a dynamic site, page structures tend to be more or less fixed, but page data can be changed at will, as often as needed, and this might mean constantly. Think about the news sites you visit every day: you probably go there because they give you the latest news. Part of a CMS’s mission is to provide adequate means to easily modify the pages’ content for the site. It’s also important that the pages can be updated by people with no technical skills whatsoever.

In fact, we can look at a CMS from another perspective and say that, as a system, it’s made up of three subsystems which execute these general functions:
* **Capturing** the content in an easy way,
* **Managing** the content so it’s available when needed,
* **Serving** the content whenever it’s asked for.

So a good definition of a CMS would be that it’s a system in charge of capturing, managing and serving the content in a dynamic Web site. A CMS is like a site’s librarian: she receives the new books, catalogues them so they can be easily found later, and provides them as needed. Of course, the day someone builds a CMS that smiles, that will be a day to remember!

From a user’s point of view, a CMS’s capturing function is usually done through a Web interface. This means that the content is captured using Web forms. The CMS takes the content from that Web form and stores it in a database for its later retrieval. The managing function is built in the CMS logic, and if the CMS is good, the content will be handled in an efficient, obvious and useful way. The serving function is done by a rendering subsystem that integrates structure, style and content to build pages that are then passed to the Web server for their journey back to the user’s browser.

There’s another way of looking at the process of serving pages. It’s what we could call *the component view*. We’ve already seen that in order to serve the requested pages, we need a **Web server** and a **CMS**. We might add that 
* both the Web server and the CMS, as code structures, need to run in an environment, so another component is the **operating system** (Windows, UNIX, Macintosh…);
* content has to be kept someplace, in such a way as to be easily recoverable, so another component is a **database system** (SQL, MySQL…); and
* the CMS needs to be written in a language the Web server understands, so the server and the CMS can exchange meaningful instructions. This means a final component is a **programming language** (ASP, PHP, Java…).

Two very common combinations of these components are called **WAMP** and **LAMP**, which mean, respectively, Windows-Apache-MySQL-PHP, and Linux-Apache-MySQL-PHP. Another common combination uses Windows as the operating system, IIS (Internet Information Server) as the Web Server, MS SQL as the database and ASP as the scripting language.

Let’s keep in mind that this description of how information moves between the user and the site is valid whether we’re talking about a commercial CMS or a free CMS. There will always be differences in the details, but the general principles are the same. And the results are also often the same: while some free tools are great at managing content, some are only worth a glance or a cursory exploration. And while some commercial tools are worth their price, there are many that cost way too much for whatever power they give their users.

### How XOOPS came to be

In fact, the road that leads to XOOPS began with a search for a tool to manage a lot of content for a Linux online magazine. As told by the developer Francisco Burzi, in August 1998 he created a news site called Linux Preview. It was initially managed by a Perl script he wrote: **NUKE**, but success forced him to look for a more powerful option. Burzi discovered **Slash** (http://sourceforge.net/projects/slashcode/), a script that uses Perl, Apache and MySQL. Slash was a nice piece of software, but it needed a real Perl guru to manage changes; it also required a powerful machine to run. Burzi was no Perl expert, and he had no money to spend on a super machine. So he kept looking. At last he stumbled across **ThatWare**, dubbed as “a Slash lookalike”. ThatWare essentially did the same that Slash, but instead of Perl used PHP, one of the most popular scripting languages used to control what happens in the server side of the Web. 

“The PHP-Nuke project was born… in hopes of delivering an easy to use, easy to install and easy to maintain CMS that didn’t have enormous systems requirements”, wrote later Eric Caldwell (boobtub). “All that’s needed to run PHP-Nuke is Apache, MySQL and PHP. These simple systems requirements are one of the distinctions that make PHP-Nuke a hit. It has low systems requirements and was written in a server side scripting language (PHP) that’s easy to learn, cross platform and is building critical developer mass”.

So Burzi learned PHP, recoded ThatWare and thus was born **PHP-Nuke**, whose first release is dated June 2000. A couple of months later, that is, two years after the creation of Linux Preview, Burzi sold the site to Linux Alianza, a Mexican company that ran many Linux sites and promoted its use in Latin American business environments. This deal, as well as a nice sponsorship paid by MandrakeSoft, gave Burzi funds and time to continue the development of PHP-Nuke.

A common tradition among open source developers is to port code. This means that if you see something interesting developed for another product, you take a look at the code, play with it a while and make it work for your platform, so you don’t have to reinvent the wheel. After some small communities grew around PHP-Nuke, the team led by Burzi created a project called **NukeAddons**. The mission of the project was to port as many valuable modules to PHP-Nuke and to create a module repository that would make PHP-Nuke even more popular.

### Forks and more forks

After a while, problems erupted among the developers. Nothing new in the open source world, sadly, but Burzi’s style tended to shoo collaborators off. John Cox, aka niceguyeddie, and a bunch of PHP-Nuke developers, packed their stuff and went away to create first **PostNuke** (http://www.postnuke.com) and later **Xaraya** (http://www.xaraya.com). 
Another group of developers, headed by Heinrich Steenberg, aka KodeWulf, and Heinz Hombergs, merged PHP-Nuke 4.4.1 with some of the modules gathered by NukeAddons, and created a fork distribution they called **myPHPNuke** (MPN). That team included several persons that would become later the founding fathers of XOOPS: wanderer, webmaster of several Taiwan sites and a translator to Chinese; Goghs Cheng (goghs), another Chinese developer; Sergio Kohl (w4az004), an Argentinian tester, and no less than Kazumi Ono (onokazu), then a module developer.

![](../assets/XoopsIntro3.jpg)

*Figure 3. This graphic depicts in a general way the path from PHP-Nuke to XOOPS.*

Although the MPN code was supposed to include a core framework and a bunch of modules, the truth was a bit different: modules were barely modular, so the developers decided to start a parallel project. “The reason we had to make it another project”, commented onokazu, “was that the core was rewritten considerably to support the plug-n-play feature of modules. The original MPN was also calling some parts as modules, but they were in fact tightly integrated to the core”. So was born **myPHPNuke SE** (MPN-SE), where SE stands for Second Edition.

The first MPN-SE team had only four members: wanderer, goghs, onokazu and the theme builder Jan Inge Pettersen, aka Xend. Things moved quickly in the group. First, three German developers joined the team: Heinz Hombergs (one of the original MPN creators), Stefan Kaletta and Alexander Weber. But shortly afterward, when more problems grew within the team because of property feelings (and disputes) about the name myPHPNuke, the three Germans left the project and eventually created their own CMS, **openPHPNuke** (http://www.openphpnuke.com). Kazumi Ono commented this name was an idea of his own, which suggests the members of these teams had a lot of cross-breeding and communication.
One of the MPN developers, seduced by the tenets of object-oriented programming, started some exercises towards the development of yet another fork which would be called myOOPS. The last four letters were taken from a MPN module written by goghs and used to manage the database options of a MNP site. “OOPS” was an acronym that meant Object-Oriented Portal System. The project page in Sourceforge.net lists five developers; it also says they never released any files.

### XOOPS is born

By that time, a company called RuffDogs.com was managing, so to speak, the three projects: MPN, MPN-SE and the never-born myOOPS. Development continued with some interesting twists. For instance, the original PHP-Nuke used to hold all the language strings in a single, enormous file. Each language file used to weigh from 65 to 90 kb. The MPN-SE team modularized the language files so that instead of having a mammoth file there were many smaller ones; a tactic that meant an easier edition. This was quickly adopted back in the “father”: version 5.5 of PHP-Nuke, released on February 2002, included the files modularization.

All in all, the MPN-SE team didn’t release files either. Kazumi Ono followed the trend and also left, taking with him several developers, who worked for months before releasing anything. On December 12, 2001, Xoops.org was launched, hosted on mywebaddons.com. A few weeks later, on the New Year’s Day of 2002, XOOPS RC1 was released to the public. The original XOOPS was based on PHP-Nuke 4.4.1 and myPHPNuke 1.8.5, although some 70-80 percent of the code was rewritten, as onokazu wrote on the release announcement.

By the end of May 2002, the team had released three point versions, and XOOPS moved to a server in Japan. Three months later, an important milestone was reached: the official site http://www.xoops.org was upgraded to use the Smarty templating system (http://smarty.net). Onokazu wrote that “with Smarty, designers can have total control over application presentation by just modifying template files, and module developers would only need to concentrate on application logic and passing variables to those template files”. By this time, however, things had changed a lot also inside the team. More to the point, most of the original team had left, for reasons similar to the ones that left Burzi alone with PHP-Nuke: the main developer’s personal style.

One of the most troubling departures was the defection of a French developer, Half-Dead, who opposed the adoption of the templating system, and so went his own way… to create still another fork, this one called then e-XOOPS. This was his argument: “While XOOPS has decided to rewrite its core (v2) to make massive usage of classes, object-oriented style coding, and the Smarty templating system, e-Xoops has decided to keep the v1 core and improve upon it, by making it stabler, faster, and even simpler to modify than it was before. Like this even non-hardcore PHP coders can easily jump in and start making modifications”. A bitter dispute ensued, mainly due to the fact that Half-Dead released his fork, ahem, without the original credits, something very unusual in the open source world. So a flame war ensued, and in the end, Half-Dead restored the XOOPS credits and continued his development, almost alone. With him also left Farsus, a respected theme designer that eventually took e-XOOPS in his hands, and since June 2004 runs the new version of the script, now under the name RunCMS (http://www.runcms.org/).

### The two XOOPS lines

As to XOOPS, the last months of 2002 were filled with announces. First onokazu published a roadmap that he revised a month later, basically defining the main features XOOPS would have in the immediate future. Then Eric Caldwell (boobtub) announced an important step: XOOPS development would follow two separate paths. What up to then was the RC3.x series got changed to version 1.3.x, and what up to then was the RC4.x series was to become the 2.0.x series. So what the developers actually did was to create an internal fork. Those users that for some reason didn’t want to migrate to the use of Smarty as a templating engine stayed faithful to the 1.3.x line, while those willing to follow the changes switched to the 2.0.x line.

The 1.3.x line went ahead with the release of version 1.3.6 on December 6, 2002, followed by several patches up to version 1.3.10, released on April 2003. Development along this line has now stopped, and the XOOPS team will only provide bugfixes and security patches. Work on line 2.0.x continued, and on April 2003 version 2.0 final was released. Point versions have been released up to the present version, 2.0.7.

But more important things happened during the second half of 2003. First, John Neil (Catzwolf) proposed the creation of a module development team. A site was built for this purpose, and many interesting discussions began to take place there. Then Michelle Alexandria (malexandria), XOOPS’ original PR person, proposed to do the same with a theme development team. The third initiative, launched by Herko Coomans (herko) in September 2003, created what is known as the Core Team, in fact a noisy and somewhat irregular array of eight work teams: Core development, Module development, Theme design, Quality control, Support, Documentation, Community Relations and Product Development. These teams are still consolidating their roadmaps and their mid-term plans, but some have already settled and produced interesting work for the XOOPS community.
On October 2003, a physical change took place: all XOOPS sites moved to a server in the United States, loaned to the XOOPS community by EPC Online.

Another still more important event happened during 2003. Onokazu, XOOPS lead developer, decided to step back from the leading role he played to devote more time both to day-to-day work and to support the XOOPS Japanese community. He’s still quite active, and whenever he can, he surveys the forums, makes comments or suggestions and provides guidance, counseling, and occasionally criticism (but of course!) to keep things moving. So has XOOPS development stopped? Quite the contrary. Two roads are presently being actively followed. On the first one, Skalpa Keo (skalpa) has been leading the development of XOOPS 2.1 and XOOPS 2.2, which will consolidate the code and prepare the way for XOOPS 3. On the second road, Jochen Buennagel (bunny) has been preparing what promises to be a completely rebuilt XOOPS. At the time of this writing, XOOPS 2.1 is approaching, and hundreds of eager xoopsers await eagerly its arrival. And now XOOPS developers are learning to be cautious; after all, what they build will have possible impacts on a community that has over 20 thousand registered members, many of them very vocal and demanding. As usual.

### The nature of the beast

So what is this product that we’ve been talking about? As stated in the first paragraph, it’s a free content manager. But now we can be a bit more precise. Let’s see. XOOPS is an integrated set of scripts written in PHP that, when installed properly in a Web environment, allows an administrator to create and maintain a flexible, powerful and versatile dynamic Web site. XOOPS is properly installed when it has access to a Web server that understands PHP, and when it can resort to a database to save there the site’s content.

**XOOPS**, pronounced “**zups**”, means **eXtensible Object Oriented Portal System**. We can also create a definition out of this terms. To begin with, this is a system. XOOPS is not a bunch of scripts loosely tied together, but rather a coordinate structure built on a few principles. These are the principles of object-oriented programming, that, without getting deeply technical, mean that XOOPS code is written not around processes, but around objects, objects that have attributes, can be copied or extended, and that, for those of us that are more users than programmers, just mean that it’s easier to build something in XOOPS than in other CMS solutions. Last, the extensible adjective only means that XOOPS, far from being a complete solution for content management, can be seen as an intelligent framework that can be (and is being) grown with the addition of modules. XOOPS capabilities are thus unlimited in scope, and we’ll learn a lot about this power as we progress along the chapters of this book .That’s a promise.

Now, at this point the best way of describing what is XOOPS consists of going through an attribute list. We’ll see a dozen characteristics that together give a good first impression of XOOPS.

### Easy installation

Have you ever tried to install a complex CMS? No? Try it, if for no other reason than being able to compare the experience of setting a XOOPS site versus setting an ACME-CMS site. Once the environment is adequately set, installing XOOPS is a breeze. All you have to do is to invoke the installation wizard, to feed it a few morsels of knowledge (we’ll go deep into this in the following chapter, of course), and in a few minutes you’ll have a XOOPS site installed and ready to go.

### Database-driven

There are still some CMS solutions that, moaning about the terrible problems caused by databases, prefer to save data in physical files. This has its own problems, it’s not terribly efficient and in the end means you’re need to be extra cautious with your site. XOOPS uses a relational database to store not only the content of your site, but also hundreds of configuration options that give your site its specific nature, its flavor, its look and feel. Theoretically, XOOPS might use any database, but the real, honest truth is that only MySQL (http://www.mysql.com), a free, powerful, flexible database, is officially supported.

### Modular structure

XOOPS is built as a “core” framework that does the basic management job for your site. This core supports the addition of functional modules that do the actual content management. As of today, the XOOPS package still includes a basic catalogue of “official” modules, but plans are on the way to separate core development from module development, and to put in place a qualifying process to endorse well-written modules. Anyway, for the moment there’s dozens of modules available for everything from showing the weather to displaying random quotes, from listing news stories to downloads or links or articles. XOOPS modules are very easily installed and uninstalled, as pertains to true modules, and anyone can create thus in a matter of minutes a very specific, unique combination of modules for a particular site.

### Very flexible, themable interface

The layout of a XOOPS site can be easily modified in two broad senses: first, the positions of blocks can be easily modified in the available columns; second, the look and feel of the whole structure can be completely changed with a click of the mouse by using a different theme. A site’s administrator can configure a site to look very different, even with the same content. It’s really very easy to move blocks around, to activate/deactivate modules, to switch among themes. It’s even possible to define a site to look different for every kind of visitor. And you can choose among dozens of themes, create your own, adapt a theme built by someone else and even let your users choose among several themes.

### Smarty template engine

Part of XOOPS flexibility when it comes to look and feel is born from the use of Smarty, defined as a templating engine. What this means for a designer is that it’s quite easy to create an interface of your own and to transform it into a XOOPS theme. Have you ever tried building themes for other solutions? Some of them still have a complex mixture of PHP and HTML in their themes, and, even worse, have themes split in several files so you open a table in a file and close it in another. Try to follow that logic! In XOOPS, a designer works with a complete HTML page, and after she’s satisfied with how it looks and behaves, she can add a few Smarty tags to include dynamic content. In one of this book’s chapters you’ll build a theme of your own and learn how to use Smarty variables.

### Group based permissions

XOOPS is made to build communities, and in a community you have rules to define who’s in and who’s not. XOOPS includes a member registration system, which let’s you optionally set up parts of your site so only registered members can access them. Those members are included in groups, and XOOPS is built so that you can define the privileges assigned to each group in a very granular matter. For each group you have in your site (the default groups are Webmasters, Registered users and Anonymous users, but you can define as many groups as you want), you can for instance define if the group’s members:
* can see a particular block
* can access a particular module
* have access to a particular function (reading, posting, etc.)
 
### User personalization

Since users are always part of groups, does this mean that they’re all alike? Not at all! Each user has her own personality within your site, beginning with the fact that she can set up a password that not even you, as site manager, can know. This means a user’s information within the site is only accessible to the user, provided she remembers her password. A site’s users can also edit a lot of information contained in their user profiles, and if the site’s manager allows it, they can also select their themes, upload their avatars and more.

### Flexible user management

But if the users have control over their profiles, the site’s administrator has also control over nice tools to manage the user base. It’s possible, for example, to search among users by employing different criteria. It’s also possible to mail users, to send them private messages, and in extreme cases, even to ban obnoxious users.

### Great search function

XOOPS includes a site-wide search engine that is quite efficient and that provides search results in an orderly fashion: it sorts them by module so it’s very easy to know is a search result appears in a news story, an event, a downloadable file, etc. You can even configure a bit the search parameters.
### Nice image manager
XOOPS includes a tool to manage the images used throughout the site. Although many dream with a more powerful image manager, the truth is that the present one is more than adequate to handle the regular operation of a Web site. You can create image categories, upload images one at a time, configure the heights and widths of the uploadable images, and later you can access the image repository using one of the tools available for the construction of forms. 

### Multi-byte language support

Not surprisingly, since the original lead developer is Japanese, XOOPS fully supports multi-byte languages, including Japanese, Simplified and Traditional Chinese, Korean, etc. Also, the language seen in the user interface can be easily changed by installing language “packs”. Each language pack is just a set of files that contain language equivalences. This means that the creation of a different language pack is easy enough: you just copy a language folder, open a text file and translate the text strings it contains.

### World-wide support

XOOPS was created, is being developed and is maintained by an interesting team of many hard-working volunteers that log in the XOOPS community from all over the world. The XOOPS community has more than a dozen official support sites around the globe, which give support to non-English speaking users. And due to its growing popularity, it’s very likely you’ll find some veteran XOOPS user that speaks your language or lives in your time zone any day. And the friendliness of the XOOPS community is almost legendary; just browse around any of the forums to see it in action. One of the Appendixes includes a list of some available communities where you can look for help in case you need it.

### Distributed development process

Yet another distinctive feature of XOOPS is the fact that its development is not concentrated in a single person, but rather in a team. For some, this is a weakness, yet it might be the best chance to take XOOPS into very solid, very high levels of quality among the open source content management solutions.

### Vibrant (and demanding) community

Last, but certainly not least, one of XOOPS’ most important assets is its community. Its more than 20 thousand members chat in the forums about every thing imaginable. You can find there comments, complaints, gossip, hacks, suggestions, a few fights but always a strong pulse, the indication of a healthy, vibrant community demanding that XOOPS moves ahead. 

**In December 2015 XOOPS will celebrate its 14 Anniversary. **