# Template for a student web site and blog


## Usage


## Structure

Here are the main files of the template

```bash
File structure
├── _draft	               # To store your drafts, they won't be published on your site
├── _includes	               # html includes
├── _layouts                   # html layouts (see below for details)
├── _posts                     # Blog posts
├── assets
|  ├── js	               # javascript files,
|  ├── css                 # stylesheets (edit styles.css)
|  ├── fonts		       # Font-Awesome, and other fonts
|  └── img		       	   # Images used for the site
├── pages
|   ├── 404.md		       # To be displayed when a url is wrong
|   ├── about.md           # About your site (edit this first)
|   ├── search.html	       # Search page
|   └── search.json        # Specify the search target (page, post, collection)
├── _config.yml                # configurationfor the site
└── index.html                 # home page (actually the blog page)
```

## Configure

Open `_config.yml` in a text editor to change most of the blog's settings.

If a variable in this document is marked as "optional", disable the feature by removing all text from the variable.


### Site configuration
Configure Jekyll as your own blog or with a subpath in in `_config.yml`:

Jekyll website *without* a subpath (such as a GitHub Pages website for a given username):

```yml
  baseurl: ""
  url: "https://username.github.io"
```

```yml
  baseurl: "/sub-directory"
  url: "https://username.github.io/"
```

Please configure this before using the student blog.

### Meta and Branding

Meta variables hold basic information about your Jekyll site which will be used throughout the site and as meta properties for search engines, browsers, and the site's RSS feed.

Change these variables in `_config.yml`:

```yml
  theme_settings:
    title: My Student Blog                 # Name of website
    avatar: assets/img/triangle.png       # Path of avatar image, to be displayed in the site header
    description: My blog posts            # Short description, primarily used by search engines
```

### Customizing text

#### Footer and Header's text

Customize your site header/footer with these variables in `_config.yml`:

```yml
  theme_settings:
    header_text: Welcome to my Jekyll blog
    header_feature_image: assets/img/sample3.png
    footer_text: Copyright 2017
```

#### Localisation string

Change localization string variables in `_config.yml`.

English text used in the theme has been grouped  so you can quickly translate the theme or change labels to suit your needs.

```yml
  theme_settings:
     str_follow_on: "Follow on"
     str_rss_follow: "Follow RSS feed"
     str_email: "Email"
     str_next_post: "Next post"
     str_previous_post: "Previous post"
     str_next_page: "Next"
     str_previous_page: "Prev"
     str_continue_reading: "Continue reading"
     str_javascript_required_disqus: "Please enable JavaScript to view comments."
```


### Other features

Jekyll works with [liquid](https://shopify.github.io/liquid/) tags usually represented by:

```
{{ liquid.tag | filter }}
```

These are useful to render your jekyll files.
You can learn more about them on [shopify's doc](https://help.shopify.com/themes/liquid/basics)

### Footer's icons

Display the site's icon from [Font Awesome](https://fortawesome.github.io/Font-Awesome/) in the footer.
All icon variables should be your username enclosed in quotes (e.g. "username") in `_config.yml`,
except for the following variables:

```yml
  theme_settings:
     rss: true    # Make sure you created a feed.xml with feed.xml layout
     email_address: type@example.com
     linkedin: https://www.linkedin.com/in/my name
```

### Comments (via Disqus)

Optionally, if you have a [Disqus](https://disqus.com/) account, you can show a
comments section below each post.

To enable Disqus comments, add your [Disqus shortname](https://help.disqus.com/customer/portal/articles/466208)
to your project's `_config.yml` file:

```yml
  theme_settings:
     disqus_shortname: my_disqus_shortname
```

### Google Analytics

To enable Google Analytics, add your [tracking ID](https://support.google.com/analytics/answer/1032385)
to `_config.yml` like so:

```yml
  theme_settings:
     google_analytics: UA-NNNNNNNN-N
```

### Post excerpt

The [excerpt](https://jekyllrb.com/docs/posts/#post-excerpts) are the first lines of an article that is display on the blog page.
The length of the excerpt has a default of around `250` characters and can be manually set in the post using:

```yml
---
layout: post
title: Sample Page
excerpt_separator: <!--more-->
---

some text in the excerpt
<!--more-->
... rest of the text not shown in the excerpt ...
```

The html is stripped out of the excerpt so it only displays text.

## Layout
Please refer to the [Jekyll docs for writing posts](https://jekyllrb.com/docs/posts/).
Non-standard features are documented below.

### Layout: Post

This are the basic features you can use with the  `post` layout.

```yml
---
layout: post
title: Hello World       			# Title of the page
hide_title: true         			# Hide the title
image: "assets/img/sample.png" 	 	# Add a feature-image to the post
caption: Oxford from the parks   	# A caption used for this image
tags: [holiday, Oxford, life]       # tags allow you to group the posts
published: false                    # change to true to make the post live
---
```



### Layout: Page

The page layout have a bit more features explained here.

```yml
---
layout: page
title: "About"
subtitle: "This is a subtitle"
feature-img: "assets/img/sample.png"
permalink: /about.html               # Set a permalink your your page
hide: true                           # Prevent the page title to appear in the navbar
icon: "fa-search"                    # Will Display only the fontawesome icon (here: fa-search) and not the title
tags: [sample, markdown, html]
---
```

The hide only hides your page from the navigation bar, it is however still generated and can be access through its link.
Use the `_draft` folder to keep files from being generated on your site or put `published: false` in the metadata.

### Layout: Default

This layout includes the head, navigation bar and footer around your content. All pages will use this layout unless you create a different one.

## Feature pages

All feature pages besides the "home" one are stored in the `pages` folder,
they will appear in the navigation bar unless you set `Hide: true` in the front matter.

Here are the documentation for the other feature pages that can be added through `_config.yml`.

### Home

This page is  used as the home page of the template (in the `index.html`). It displays the list of article in `_posts`.
You can use this layout in another page (adding a title to it will make it appear in the navigation bar).

### Search

The search feature is based on [Simple-Jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search) there is a `search.json` file that will create a list of all of the site posts, pages and portfolios.

Then there's a `search.js` displaying the formatted results entered in the `search.html` page.

The search page can be hidden with the `hide` option. You can remove the icon by removing `icon`:

```yml
---
layout: search
title: Search
icon: "search"
---
```

### Tags

Tags should be placed between `[]` in your post metadata. Separate each tag with a comma.
Tags are recommended for posts and portfolio items.

For example:

```yml
---
layout: post
title: Markdown and HTML
tags: [sample, markdown, html]
---
```

> Tags are case sensitive `Tag_nAme` ≠ `tag_name`

All the tags will be listed in `tags.html` with a link toward the pages or posts.
The Tag page can be hidden with the `hide` option. You can remove the icon by removing `icon` (like for the search page).



