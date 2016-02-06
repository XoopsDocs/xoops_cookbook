# Day 3: Extend Functionality with Modules

Content is King and it is up to you to provide it. Module selection can be a bit overwhelming to some, but there are some good rules to follow as you start. Where I recommend you start is by identifying the types of content you want on your site and determine how often it will be updated.

The simplest web sites are pretty **static** - a few pages about you and your site, maybe some contact information and a few photos. You may even have an old site you have decided to move to XOOPS and you want an easier way to update the pages once in a while. Every site will have some of this type of content and there are a few options for this. Since we have not rushed into anything in this series, I am not about to break with tradition - start simple and with the content that won't require a lot of maintenance, then move on to more labor-intensive content.

As you examine the content you will be adding to your site, think about the ongoing effort needed to maintain it. If you start with a module that is very interactive and you get swamped with it, the other stuff just won't get done. Best to get some of the other things done first.

Also look at how one section might feed another - if, for example, you plan on having a lot of photos and select an album module, you will want to use your photos in other areas of your site pretty easily.

When evaluating modules, read this FAQ - it offers some great advice about selecting modules that are still being actively developed and supported, something important to the future of your content.

**Static (and Borrowed) Content**
- Wiki
- HTML Content Wrapper
- News Aggregator
- Contact Form(s)

**Some Activity Required**
- Articles
- Downloads
- Links
- Albums
- Audio/Video files

**More Activity Required**
- News
- RSS Feeds (of your content)
- Calendar
- FAQs

**Lots of Activity (and Maintenance)**
- Forums
- Chat
- Blogs

This is not an exhaustive list of content types, but these are the most common. You could have a site with all these modules and more, but you can also have sites with as few as 2 modules.

In the FAQ about selecting modules, you are advised to find modules that are by active XOOPS members, still show signs of further development and work with the current version of Xoops. 


One thing to be aware of, and this is for any module that uses WYSIWYG editors - most current browsers block some scripts by default. So, you will find that trying to paste something from the clipboard will only work with keyboard commands, not mouse actions. You may think the editor is not working, but it is actually the browser that is preventing the function from working at all. Firefox has an extension to enable clipboard functions - it is well worth installing.


From an administrative standpoint, uninstall any modules you elected not to keep and delete the folders from your web folder. Update the DB backup module and backup your database again.

###Images/Pictures

Including images in your pages moves you from the text-based pages of the early Internet to the image-laden pages of the World Wide Web. There are lots of considerations you need to address from an administrator's vantage point and from a user's standpoint. Do the images add to the message? Do they slow down your web page? Do they match the content? Do you have copyright issues to worry about? What about privacy issues? What about storage space and bandwidth on your server?

The simplest use of images on your site will be to enhance and complement the brilliant writing on your site. XOOPS core has a built-in ImageManager in the Administration menu. Log in as the administrator for your site, click on the Administration Menu, then click on the System Admin icon, then click on the Image Manager link (or hover over it and click on the Images link). The system ImageManager allows you to create categories for your images, set limits on dimensions and file sizes for the images, and also set permissions on which groups can use the images and which groups can upload images. When you create a category, you can also set to add the images to the database or to save them as files - I find saving them as files works very well.

Create your first category - 'General' is a good name - and set the preferences for that category. You will need to give this some thought as you go forward so you can easily find the image you want to use. Once you have created your first category, upload a few images to it so you have some to work with. Part of your job will to create some 'how-to' pages with instructions, so start collecting some screenshots of various parts of your site to use. Another tip for online images - save them with a resolution of 72dpi (dots per inch) before uploading them. That will make the files smaller, load faster, and most displays can't render any better resolution with any appreciable improvement in quality. Higher resolutions are for printing, not viewing.

All this is pretty straightforward. Now comes a bit of the tricky part. Unless you are a seasoned veteran of the standard XOOPS editor and can visualize how your page will look without the images and other formatting, you have probably chosen to use one of the WYSIWYG editors. None of the WYSIWYG editors use the built-in XOOPS Imagemanager without some modifications. The other editors make use of their own image managers, which makes those images unavailable to the other editors.

You also have the option to provide a URL for an image in all the editors, so that image does not necessarily need to reside on your server - it just needs to be accessible from the Internet. Be cautious of this option because you have no control over that image. The image may get deleted, moved, or replaced with a different image (and have the same name and location as the image you link to).

If you also plan to have a gallery of images, use that criteria when selecting which gallery module to use - but that is another discussion. Remember - That depends!

Things to keep in mind as best practices when using images on your web site:
* Your images should have 'alt' tags
* Your images should also specify 'height' and 'width' - and it should match the actual dimensions. Don't use these tags to resize your images on the page.
* Images can also have 'title' tags, this is used differently by each browser and depends on whether the image is also a link
* Don't use images in place of text
*Make the filenames of the images meaningful - better for the search engines and easier to sort out when you are looking at a list of files

There's a lot of stuff about images, without any images!
