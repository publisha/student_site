---
layout: page
title: How to Build Your Web Site
subtitle: Writing with Markdown
permalink: /howto/
published: true
hide: true
tags: [Help, Markdown]
---

Here are are the steps to take 

## Software tools needed

* Get Atom (atom.io)
	* Once this has downloaded copy the application into  your own `Applications` folder
		* Note: You may need to create an `Applications` folder inside your `Home` folder.
		* image in here?
* Get Git Desktop
	* Once again this will download a file into your downloads folder. Copy this to  your own `Applications` folder

### Add some packages to Atom
 
 Open Atom (you can turn off the welcome window and welcome guide tab and no need to send usage data). Locate the `Packages` menu and move down to  the settings view. Select Install packages/Themes. In the Search text box, type markdown and locate the package called tool-bar-markdown-writer (__check this__)— maybe markdown-writer.
 
 Get the toolbar package first:
 
 
* Tool-bar
* markdown-writer
* toolbar-markdown-writer

settings for toolbar ... file extensions


## Setup [^1]Github

### Create a free account on Github.com

You do not need to use your Brookes credentials nor your Brookes email address because this web site and account is yours forever should you wish to continue using it after your course.
>Naming the account (**your username**) is important (although you can change later) because this will become part of your website URL. For example, if you name the account `MyLoveofBooks`then the web site will become `MyLovofBooks.github.io`. Not all names will be available and yours may be rejected if it is already taken.

Please remember your username and password or keep somewhere safe.

Once you are logged in to Github, go to the following URL:

https://github.com/publisha/student_site/

> Add picture here of Template link

Use the template link to receive the repository in your own github account.

> You should now have a copy of the template web site on github

Although it is always possible to edit the files directly on the github site, there is a much better way!

### Getting a local copy

To edit and add content you will need to work on the site on a local copy. To do this, you should go to the github page for your repository and find the `Clone or download` button.  Select `Clone` and your copy of Github Desktop should then open.

Choose a local space or even Creative Cloud (don’t use google drive)

Once the clone has finished you can now open in Atom. 

> Image of the site in Atom

### Configuring your site

Before you make your web site live and post new articles, you need to edit the configuration file with your own details. The file you must edit is:

`_config.yml`

The file itself has comments so it should be self explanatory but here are the important changes that you must make:

### Site configuration
Configure as your own website in `_config.yml`:

```yml
  baseurl: ""
  url: "https://username.github.io"
```

Change _username_ to the name you chose for your site.

Please configure this before using the student blog.

### Meta and Branding

Meta variables hold basic information about your Jekyll site which will be used throughout the site and as meta properties for search engines, browsers, and the site's RSS feed.

Change these variables in `_config.yml`:

```yml
title: My Student Blog                 # Name of website
avatar: assets/img/triangle.png        # Path of avatar image, to be displayed in the site header (you can create a logo do make an image of yourself)
description: My blog posts             # Short description, primarily used by search engines
```

### Customizing text

#### Footer and Header's text

Customize your site header/footer with these variables in `_config.yml`:

```yml
    header_text: Welcome to my Student blog
    header_feature_image: assets/img/sample3.png
    footer_text: Copyright 2019
```

## Adding and Editing Content

There are 2 types of pages in your site:

### Posts

You can post articles or blog posts and these will be dated so that they appear in date order, on the home page; the latest at the top. Each post has it’s own page but the extract will appear on the home page. The number of post extracts that appear on the home page can be configured in the `_config.yml` file (the default is 5 posts with a link to the previous 5 etc.)

The posts themselves are files that will automatically be generated inside the `_posts`folder.

### Pages

You can create other pages for special (non-dated) contents and, as long as you save them inside the `pages` folder, they will automatically generate a menu item at the top right of your site.

Apart from the **About** page described below, you can also create any page that you like to add to your site and, thus, a menu item. Examples could be a CV, or a Project page, or even a gallery of your photos.

#### The About page

This is the one page ready for you to edit. This page needs to be edited to contain information about yourself or what you want this site to do!

Editing this page will be a good way for you to get used to the way to edit and create pages using `Markdown`.

If you want to create another page, you can duplicate the *About* page so that you can see what the structure needs to be.

### Markdown

Markdown is a way to write for a web site that uses simple structure and markup that will then be converted to HTML. It is useful to understand how `Markdown` works, but actually, when we use **Atom** with the added package, the elements can be selected from a toolbar. 

> Picture of Atom here

Here are some examples of what the Markdown syntax means.

```Markdown
## Heading level 2
### Heading level 3

This is **bold** text.

This is *italic* text

````

### yml metadata

At the top of each page or post there will always need to be some metadata to control certain aspects of the page when it is converted to `HTML` and then included in your site.

This metadata is enclosed within the 2 groups of hyphens.

```
–––
metadata goes here
–––
```

Some of this metadata is generated automatically when you create a new post (the date for example). You will also need to edit this metadata to confirm that the post is ready to be published; change from `published:false` to `published:true`.

#### Feature images

We will describe how you can add images to your posts and pages later, but all content can also have a `feature image` and this image will appear at the top of the page. You will need to place this image into your `images` folder and then provide the link to it in your metadata.

> **Tip** you can drag images into the images folder (make sure that they do _not_ have spaces in the file name) and then `right-click` over the image and copy the path. Then paste this path into the metadata for `image: pathtoimage`.

[^1]: What is Github?

You can read about it here: https://www.howtogeek.com/180167/htg-explains-what-is-github-and-what-do-geeks-use-it-for/
