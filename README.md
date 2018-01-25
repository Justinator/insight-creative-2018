# 🌎 Insight Website - 2018 Edition
## Table of Contents
1. [System Preperation](#-system-preparation)
2. [Local Installation](#-local-installation)
3. [File Structure](#-file-structure)
    1. [Pages](#pages)
    2. [Work](#work)
    3. [Blog](#blog)
    4. [Images](#images)
    5. [Data](#data)
    6. [Play](#play)
    7. [Site](#site)
    8. [Styles](#styles)
4. [Usage](#%EF%B8%8F-usage)
    1. [Resizing Images](#1-resizing-images)
    2. [Optimizing Images](#2-optimizing-images)
    3. [Live Editing](#3-live-editing)
    4. [Compression](#4-compress-script-files-deprecated-since-the-site-is-built-live-off-github-this-step-should-no-longer-be-required)
    5. [Push to GitHub](#5-push-to-github)
    6. [Check Netlify](#6-check-netlify)
5. [Adding a Blog Post](#%EF%B8%8F-adding-a-blog-post)
    1. [Images](#%EF%B8%8F-images)
6. [Adding a Project](#%EF%B8%8F-adding-a-project)
    1. [Images](#%EF%B8%8F-images-1)
    2. [Image Styling](#%EF%B8%8F-image-styling)
7. [Employees](#-employees)
8. [Play](#-play)
    1. [Quotes](#quotes)
    2. [Good Read](#good-read)
    3. [Design](#design)

## 💻 System Preparation

To use this starter project, you'll need the following things installed on your machine.

1. [Jekyll](http://jekyllrb.com/) - `$ gem install jekyll` (Built on version 3.3.1)
2. [NodeJS](http://nodejs.org) - use the installer. (Version at time of initial build 9.3.0)
3. [GulpJS](https://github.com/gulpjs/gulp) - `$ npm install -g gulp` (mac users may need sudo)
4. [GraphicsMagick](http://www.graphicsmagick.org/download.html) - this is needed to run gulp-resize
*Note: the version of ruby installed during the writing of this documentation is `ruby 2.2.6p396`*

## 💾 Local Installation

1. Clone this repo, or download it into a directory of your choice.
2. From the shell or teriminal, inside the directory,  run `bundle install`.

```shell
bundle install
``` 

3. Run `bundle update` to update your bundles.

```shell
bundle update
```

4. Run `npm install`. This will install all of the dependencies.


```shell
npm install
```


## 📁 File Structure

Before running any commands, lets understand the file directories.

### Pages
Each individual page will be located inside the folder with its corresponding name.

### Work
Projects can be found inside the **work/_posts** directory. They get sorted by date, so the first project is set to 2000-01-01 with each newer project being a day newer. So the newest projects will have the most recent date. DO NOT use the current date as the date for the project, simply follow the pattern that is already created. *Note: If two projects have the same date they will be shown in alphabetical order, meaning the project closer to A will be shown further down than the latter*

### Blog
All blog posts are located inside the **blog/_posts** directory. For these, use the date of the day you would like the blog to get posted.

### Images
All of the original images are located inside **unsized-img**, the reason for this is because there is a command that we run which will automatically resize images for different screen sizes and then place those images inside the **img** directory. So keep all of your original clean images inside the **unsized-img** directory. Typically these images should be around 2400px in width. They'll be optimized later so don't worry too much about that!

### Data
Both the employee list and the services list can both be found under the **_data** directory.
### Play
All play posts are located inside the **play/_posts** directory.

### Site
The **_site** directory is the compiled directory with all of the final files. The contents of this folder is what will be uploaded to the actual website.

### Styles
Do not make style changes in the **css** directory. The styles for the website are all in the **_scss** directory. Each individual page has had its own style sheet setup for styles unique to that page, and then there are sheets setup for general styling like the footer or typography. The **_variables.scss** sheet has site wide variables that can be used in your scss sheets.

## 🏃‍♂️ Usage

### 1. Resizing Images

**Make sure any images you need are inside the *unsized-img* folder** and then run `gulp resize`. This will resize all the images and place them into the **img** folder. This may take a few minutes, so wait until it completes before doing anything else.

```shell
gulp resize
```

### 2. Optimizing Images

Run `gulp min` which will optimize all of the images in the **img** folder. Once again, this will take a while.

```shell
gulp min
```

### 3. Live Editing

You can now run `gulp` which will automatically run jekyll, open your site in the browser with auto-refresh, and watch for any file changes. When you are done making all of your changes, hit ctrl+c to cancel running gulp. (If you add any new images, you will need to rerun steps one and two)

```shell
gulp
```

### 4. Compress Script Files (Deprecated: since the site is built live off github this step should no longer be required.)

Once all of your changes are made, run `gulp compress` to minify the javascript files.

```shell
gulp compress
```

### 5. Push to GitHub

Push changes to GitHub. **Note: When you push to github it instantiates a new build on [Netlify](https://app.netlify.com/).**
### 6. Check Netlify

When you push a new commit to github Netlify will automatically start running a new build of the site and then push that version live when it is complete. You can make sure the build worked by [logging in](https://app.netlify.com/) and going to the **Deploys** page for Insight 2018. You can also rollback to previous versions or stop auto publishing new builds. For more information on how to use Netlify refer to their [documentation](https://www.netlify.com/docs/).


## ✏️ Adding a Blog Post

A blog post will have the following information at the top of the development file:

```html
layout: blog
title: Media Buying 101 - What On Earth Does a Media Buyer Do?
author: Molly Setzer
description: "Molly Setzer, Senior Media Buyer at Insight Creative, explains the role of a media buyer, how they can support your company's marketing efforts and how they help you get the most out of your marketing budget."
text-color: 'fff'
back-color: 'b31139'
cover-image: th-molly-vlog-media-buying.jpg
tag: blog
```

**Title:** The title of the blog post, duh!

**Author:** The name of the author, make sure this is spelt right so it can pull their information from the staff file.

**Description:** Sets up the meta description tag.

**Text-color:** This will set the color of the text for when the blog appears on the blog page, or at the bottom of another blog post.
 In most cases, it will be fff which is white. DO NOT use the # in these.

**Back-color:** This will be the background color for when the blog appears on the blog page, or at the bottom of another blog post. Typically, you want to use a color that either coincides with the blog post's imagery or theme.

**Cover-image:** Sets the featured image for the blog post.

*The layout and tag will both always remain blog*

### 🖼️ Images

Each image should be named the same as the blog and then numbered sequentially and placed in the **unsized-img** directory followed by the **blog** directory.

When adding an image, do not use the markdown image treatment, instead, add an image using html srcset like below. Set the src as the original image name, then set up a srcset image with the image size following the name like below. All images get resized for screen sizes of 400px, 600px, 900px, 1200px, 1800px and 2400px wide. *Note: when writing srcset, start with the largest image as Safari only looks at the first image.*

Images should also have this line of code in their tag, which will give them an animation when scrolling: `data-aos="fade-up"`

```html
<img data-aos="fade-up" src="/img/culture/header-1.jpg" alt="We Rock"
srcset="/img/culture/header-1-2400.jpg 2400w,
        /img/culture/header-1-1800.jpg 1800w,
        /img/culture/header-1-1200.jpg 1200w,
        /img/culture/header-1-900.jpg 900w,
        /img/culture/header-1-600.jpg 600w,
        /img/culture/header-1-400.jpg 400w"/>
```

## ✏️ Adding a project

A project will have the following information at the top of the development file:

```html
layout: project
title: Logo Design
client: Bake My Day
description: Logo design created for local Green Bay bakery.
cover-image: bake-my-day/bake-my-day-logo-1
cover-text-color: fff
back-color1: c3dc93
back-color2: f282d4
tags:
- Identity
- Branding
- Print
```

**Title:** The title of the project, duh!

**Client:** The client the work was done for.

**Description:** One ore two short sentences introducing the project. This is the text that is directly under the cover image for the project and above the body text.

**Cover-image:** Sets the featured image for the blog post.

**Cover-text-color:** The header text color for the project. This displays over the thumbnails that link to the project and over the cover image. Try to keep this white as often as possible.

**Back-color1:** The first color in the background gradient for the project. The background gradient is shown over the cover image and when you hover over the thumbnails linking to the project. Try to keep the gradient colors relevant to the project.

**Back-color2:** Second color in the background gradient.

**Tags:** The list of categories the project falls under. List any that are relevant to the project, these include:
- Audio
- Campaigns
- Case Study
- Identity
- Media Buying
- Packaging
- Photography
- Print
- Public Relations
- Social Media
- Video
- Web Digital

*The layout will always remain project*

### 🖼️ Images

The images for a project should go in the **unsized-img** directory, followed by the **projects** folder, and then inside a directory with the exact same name as the project. Each image should be named the same as the project and then given a name relative to what its showing. Look at previous projects for example.

When adding an image, do not use the markdown image treatment, instead, add an image using html srcset like below. Set the src as the original image name, then set up a srcset image with the image size following the name like below. All images get resized for screen sizes of 400px, 600px, 900px, 1200px, 1800px and 2400px wide.

#### Scroll Animation

Images should also have this line of code in their tag, which will give them an animation when scrolling: `data-aos="fade-up"`. If there is more than one image in a single row on the page, add `data-aos-delay="200"` starting at 200 for the second image and if theirs a third image `data-aos-delay="400"`. This will offset their animations so they don't all fade in at the same time.

#### Lightbox

If you want the image to pop up in light box when clicked, add `data-featherlight="path/to/image"`. These need to be within a `<div class="images">` element in order to work.

```html
<img data-aos="fade-up" data-featherlight="/img/projects/vans-lumber-photography/vans-photography5.jpg" src="/img/projects/vans-lumber-photography/vans-photography5.jpg"
alt="Vans Photography"
srcset="/img/projects/vans-lumber-photography/vans-photography5-2400.jpg 2400w,
/img/projects/vans-lumber-photography/vans-photography5-1800.jpg 1800w,
/img/projects/vans-lumber-photography/vans-photography5-1200.jpg 1200w,
/img/projects/vans-lumber-photography/vans-photography5-900.jpg 900w,
/img/projects/vans-lumber-photography/vans-photography5-600.jpg 600w,
/img/projects/vans-lumber-photography/vans-photography5-400.jpg 400w" />
```

### 🖌️ Image Styling

There are a few special ways setup to showcase the images in a project.

#### Full Width Standard Image

Simply wrap the image inside two blank div tags (this is done because otherwise markup places it inside paragraph tags, which limits the width of the image to the width of the paragraph)

```html
<div>
  <img data-aos="fade-up" src="/img/projects/vans-lumber-case-study/vans-lumber-case-study-binder.jpg"
  alt="Vans Lumber Binder"
  srcset="/img/projects/vans-lumber-case-study/vans-lumber-case-study-binder-2400.jpg 2400w,
  /img/projects/vans-lumber-case-study/vans-lumber-case-study-binder-1800.jpg 1800w,
  /img/projects/vans-lumber-case-study/vans-lumber-case-study-binder-1200.jpg 1200w,
  /img/projects/vans-lumber-case-study/vans-lumber-case-study-binder-900.jpg 900w,
  /img/projects/vans-lumber-case-study/vans-lumber-case-study-binder-600.jpg 600w,
  /img/projects/vans-lumber-case-study/vans-lumber-case-study-binder-400.jpg 400w" />
</div>
```

#### Object Fit Pollyfill

There is a special class you need to apply to images that use the object-fit property. These are images that you display in the grid setup on a project, and any other designated object-fit images. Simply apply the `fix` class to them  and the ofi.min.js will setup a polyfill for browsers that don't natively support object-fit.

#### Grid Setup

This setup makes the images display in rows cropped to the same height. There are four classes setup for this style that let the image be display either full column, half column, two-thirds column, or one-third column. Also, if the image isn't going to be full column, it needs to have the class first if its the first image in the row or last if its the last image in the row.

```html
<div class="images">

  <img class="half fix first" data-aos="fade-up" data-featherlight="/img/projects/vans-lumber-photography/vans-photography5.jpg" src="/img/projects/vans-lumber-photography/vans-photography5.jpg"
  alt="Vans Photography"
  srcset="/img/projects/vans-lumber-photography/vans-photography5-2400.jpg 2400w,
  /img/projects/vans-lumber-photography/vans-photography5-1800.jpg 1800w,
  /img/projects/vans-lumber-photography/vans-photography5-1200.jpg 1200w,
  /img/projects/vans-lumber-photography/vans-photography5-900.jpg 900w,
  /img/projects/vans-lumber-photography/vans-photography5-600.jpg 600w,
  /img/projects/vans-lumber-photography/vans-photography5-400.jpg 400w" />

  <img class="half fix last" data-aos="fade-up" data-aos-delay="200" data-featherlight="/img/projects/vans-lumber-photography/vans-photography6.jpg" src="/img/projects/vans-lumber-photography/vans-photography6.jpg"
  alt="Vans Photography"
  srcset="/img/projects/vans-lumber-photography/vans-photography6-2400.jpg 2400w,
  /img/projects/vans-lumber-photography/vans-photography6-1800.jpg 1800w,
  /img/projects/vans-lumber-photography/vans-photography6-1200.jpg 1200w,
  /img/projects/vans-lumber-photography/vans-photography6-900.jpg 900w,
  /img/projects/vans-lumber-photography/vans-photography6-600.jpg 600w,
  /img/projects/vans-lumber-photography/vans-photography6-400.jpg 400w" />

  <img class="one-third fix first" data-aos="fade-up" data-featherlight="/img/projects/vans-lumber-photography/vans-photography7.jpg" src="/img/projects/vans-lumber-photography/vans-photography7.jpg"
  alt="Vans Photography"
  srcset="/img/projects/vans-lumber-photography/vans-photography7-2400.jpg 2400w,
  /img/projects/vans-lumber-photography/vans-photography7-1800.jpg 1800w,
  /img/projects/vans-lumber-photography/vans-photography7-1200.jpg 1200w,
  /img/projects/vans-lumber-photography/vans-photography7-900.jpg 900w,
  /img/projects/vans-lumber-photography/vans-photography7-600.jpg 600w,
  /img/projects/vans-lumber-photography/vans-photography7-400.jpg 400w" />

  <img class="one-third fix" data-aos="fade-up" data-aos-delay="200" data-featherlight="/img/projects/vans-lumber-photography/vans-photography8.jpg" src="/img/projects/vans-lumber-photography/vans-photography8.jpg"
  alt="Vans Photography"
  srcset="/img/projects/vans-lumber-photography/vans-photography8-2400.jpg 2400w,
  /img/projects/vans-lumber-photography/vans-photography8-1800.jpg 1800w,
  /img/projects/vans-lumber-photography/vans-photography8-1200.jpg 1200w,
  /img/projects/vans-lumber-photography/vans-photography8-900.jpg 900w,
  /img/projects/vans-lumber-photography/vans-photography8-600.jpg 600w,
  /img/projects/vans-lumber-photography/vans-photography8-400.jpg 400w" />

  <img class="one-third fix last" data-aos="fade-up" data-aos-delay="400" data-featherlight="/img/projects/vans-lumber-photography/vans-photography9.jpg" src="/img/projects/vans-lumber-photography/vans-photography9.jpg"
  alt="Vans Photography"
  srcset="/img/projects/vans-lumber-photography/vans-photography9-2400.jpg 2400w,
  /img/projects/vans-lumber-photography/vans-photography9-1800.jpg 1800w,
  /img/projects/vans-lumber-photography/vans-photography9-1200.jpg 1200w,
  /img/projects/vans-lumber-photography/vans-photography9-900.jpg 900w,
  /img/projects/vans-lumber-photography/vans-photography9-600.jpg 600w,
  /img/projects/vans-lumber-photography/vans-photography9-400.jpg 400w" />


  <img class="full fix" data-aos="fade-up" data-featherlight="/img/projects/vans-lumber-photography/vans-photography10.jpg" src="/img/projects/vans-lumber-photography/vans-photography10.jpg"
  alt="Vans Photography"
  srcset="/img/projects/vans-lumber-photography/vans-photography10-2400.jpg 2400w,
  /img/projects/vans-lumber-photography/vans-photography10-1800.jpg 1800w,
  /img/projects/vans-lumber-photography/vans-photography10-1200.jpg 1200w,
  /img/projects/vans-lumber-photography/vans-photography10-900.jpg 900w,
  /img/projects/vans-lumber-photography/vans-photography10-600.jpg 600w,
  /img/projects/vans-lumber-photography/vans-photography10-400.jpg 400w" />

</div>
```

#### Long Vertical Image (typically website)

When you have a very tall image that will need some scrolling and you don't want it to be cropped, place it in a `<div class="fill-back">` element. This will place the image in a padded element with a light gray background. It helps it stick out from the rest of the page and look cleaner rather than just having it on the plain white background.

```html
<div class="images">
  <div class="fill-back">
    <img data-aos="fade-up"
    alt="SAS Forks Website" src="/img/projects/sas-forks-website/sas-forks-website-2.jpg"
    srcset="/img/projects/sas-forks-website/sas-forks-website-2-2400.jpg 2400w,
    /img/projects/sas-forks-website/sas-forks-website-2-1800.jpg 1800w,
    /img/projects/sas-forks-website/sas-forks-website-2-1200.jpg 1200w,
    /img/projects/sas-forks-website/sas-forks-website-2-900.jpg 900w,
    /img/projects/sas-forks-website/sas-forks-website-2-600.jpg 600w,
    /img/projects/sas-forks-website/sas-forks-website-2-400.jpg 400w" />
  </div>
</div>

```

## 👯 Employees

The list of employees and their information and styling can be found under the *_data* directory in the *staff.yml* file.

```
- name: Jim von Hoff
  job_title: President
  bio: "As founder of the agency, Jim has overseen the growth and success of Insight since 1988. His client-centered approach and thorough study of clients and their industries set the stage for Insight’s long relationships with a diverse list of established clients including retail, consumer and business-to-business. A UW-Green Bay graduate, Jim’s desire to offer comprehensive marketing communications capabilities makes him—and Insight—unique in our area."
  color: red
  image1: /img/employees/tyler/tyler-1.png
  image2: /img/employees/tyler/tyler-2.png
  image3: /img/employees/tyler/tyler-3.png
```

**Name:** Employee name

**Job_title:** The position of the employee

**Bio:** The employees bio

**Color:** The color theme to use for that employees display. These are defined in the *_culture.scss* style sheet.

**image1:** The default and first image that shows for that employee. This is followed by the second and third when hovering.

## 🎮 Play

There are three types of types of posts to be made under the play section. Each post can be one of three sizes:

- full
- one-third
- two-thirds

### Quotes

A quote post will look like below:

```
---
layout: play-design
title: Henry Ford Quote
quote: "All men who have achieved great things have been great dreamers."
person: "Orison Swett Marden"
size: one-third
type: quote
---

```

**Title:** Give the quote a title, this won't be shown.

**Quote:** The actual quote itself, put in quotes.

**Person:** The person who is given credit for saying the quote.

**Size:** This is the size of the post. (full, one-third, two-thirds)

**Type:** The type of post, in this case its a quote.

### Good Read

A good read will look like below:

```
---
layout: play-design
title: Print Isn't Dead
site: "adweek.com"
link: "http://www.adweek.com/creativity/print-isnt-dead-these-7-great-ads-showed-the-medium-at-its-best-in-2017/?utm_campaign=nl_3&utm_source=sailthru&utm_medium=email&utm_term=AWK_NewDaily&s_id=59d3f478b84a9998068b4c71"
size: two-thirds
type: article
---
```

**Title:** Give the article a title, this WILL be shown.

**Site:** The name of the website the article came from.

**Link:** URL of the article

**Size:** This is the size of the post. (full, one-third, two-thirds)

**Type:** The type of post, in this case its an article.

### Design

A design post will look like below:

```
---
layout: play-design
title: Design with Passion
cover-image: design-with-passion/design-with-passion
size: full
type: design
---

<video controls controlsList="nodownload" preload="none" poster="/img/play/design-with-passion/design-with-passion.jpg">
  <source src="/video/play/design-with-passion/design-with-passion-720-web.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

```

**Title:** Give the design post a title, this WILL be shown.

**Cover-image:** The thumbnail to show on the play page. (This goes in the img/play/ folder with a folder setup for that post)

**Size:** This is the size of the post. (full, one-third, two-thirds)

**Type:** The type of post, in this case its a design.

-----

🎉 That should take care of the majority of things that you may have to change/add on a daily basis. If you are trying to make a bigger change to the site, you may have to do some digging into the code and documentation for [Jekyll](https://jekyllrb.com/) and [Gulp](https://gulpjs.com/) to get a better understanding of how things work and are built. Also of note, the transitioning animation in place is thanks to a library called [barba.js](http://barbajs.org/) which is a wonderful little library.
