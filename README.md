# Luis Puerto Díaz (Junior) site

[![Netlify Status](https://api.netlify.com/api/v1/badges/64a22e3e-188f-43cc-b0f0-97b6ce218880/deploy-status)](https://app.netlify.com/sites/serene-euclid-a30478/deploys)
[![Jekyll](https://img.shields.io/badge/jekyll-4.0.0-blue.svg?logo=jekyll)][Jekyll]
[![GitHub](https://img.shields.io/github/license/luispuerto/jr.luispuerto.net?label=code%20license&logo=open-source-initiative&color=#3DA639)][LICENSE]
[![License: copy;](https://img.shields.io/badge/&copy;content%20license-CopyRight-lightgrey)][LICENSE4CONTENT]

This is a site to celebrate our son and share our experience as parents with the rest of the world. It also tries to be a gift to him in the future when he'll start to understand a little bit. 

<!-- MarkdownTOC -->

- [Getting Starter](#getting-starter)
    - [Prerequisites](#prerequisites)
- [Built With](#built-with)
    - [Noteworthy Jekyll Plugins & Gems :gem:](#noteworthy-jekyll-plugins--gems-gem)
    - [Other:](#other)
- [Edit and configuring the theme](#edit-and-configuring-the-theme)
    - [Site & SEO Settings](#site--seo-settings)
    - [Profile Settings](#profile-settings)
        - [Default Profile](#default-profile)
        - [Additional profiles](#additional-profiles)
    - [Build Settings](#build-settings)
    - [Outputting](#outputting)
- [How to...](#how-to)
    - [Create a post?](#create-a-post)
    - [Add a responsive video](#add-a-responsive-video)
        - [YouTube](#youtube)
        - [Vimeo](#vimeo)
        - [Google Drive](#google-drive)
- [Issues](#issues)
- [Contributing](#contributing)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Acknowledgments](#acknowledgments)

<!-- /MarkdownTOC -->

## Getting Starter 

You can get a copy of this repo running the following in your terminal: 

```shell
$ git clone https://github.com/luispuerto/jr.luispuerto.net.git
```

### Prerequisites

The only prerequisite to run this blog locally is to have Jekyll on your machine. It's recommended to have also [Bundler][]. 

```shell
$ gem install jekyll bundler
```

Of course to be able to run Jekyll you need to have several other things on your system, like Ruby :gem:. Please check the [Jekyll docs][JekyllDocs] for more info about prerequisites. 

All ruby gems dependencies are saved in the [`Gemfile`][]. Run `bundle install` after cloning the repo to install them. 

## Built With

This site is build using the following software and services. 

- [Jekyll][] - The static website generator used to build this site. 
- [Bundler][] - Bundler manages an application's dependencies through its entire life, across many machines, systematically and repeatably. 
- [Trophy][trophy-template] - The starting point for this site, but right now it has suffered some modifications. 
- [Netlify][] - Where we're building and hosting this site. 

### Noteworthy Jekyll Plugins & Gems :gem:

Since the site is not published in GitHub pages, we have more freedom using Jekyll plugins and we can have more granular control about what is running on the build. These are the most important gems I'm using, but you can check the complete list on my [Gemfile][].

- [jemoji][] - The World without emojies is much more boring :man_shrugging:.

### Other:

I use the additional services, snippets and JavaScript in this site. 

- [Font Awesome][FontAwesome] - Vector icons and social logos.
- [Jekyl Codex][JekylCodex] - I've used some snippets of code from this site for some solutions. Like for example open in a new window when you click in a link to a outside page. 

## Edit and configuring the theme 

The theme is pretty simple, so there is no so much to configure. All configurations are on `_config.yml`, but if more editing is required digging through the code will be required. The `head.html` file is in the `_includes` folder and the Sass variables are found in the `_base.scss` file in the `_sass` folder.

Some descriptions for the `_config.yml` file. 

### Site & SEO Settings 

```yaml
title:
email:
description:
url:
baseurl: ""
google_analytics: UA—XXXXXXXX-X
twitter_username: 
default_img: 
```

- `title` - Title of blog
- `email` - Your email for the contact card and the footer
- `description` - Description of blog (recommended to not go over 160 characters)
- `url` - URL of main website
- `baseurl` - Path of blog if adding this on to another website
- `google_analytics` - Option field to replace with correct Google Analytics code
- `twitter_username` - Twitter username
- `default_img` - Image that will appear when posting links on social networks

### Profile Settings

There is a main profile or default profile, which correspond to the main author or the owner of the site, but you can configure additional authors, for collaborators and regular authors. 

#### Default Profile

```yaml
name: 
profile_img:
about:
social:
  github:
copyright: 
```

- `name` - Full name for SEO purposes
- `profile_img` - Image for the profile card (size to 2000x1200px)
- `about` - Short description that will be in the profile card
- `social` - List of social networks for icons in the contact card and the footer ([Font Awesome](http://fontawesome.io/) is used, so only match the name of the icon, but do not include `fa-`)
- `copyright` - Name or initials under the site is copyrighted. 

#### Additional profiles

```yaml
authors: 
      
  username:
    name: 
    profile_img: 
    about:
    email: 
    social:
      twitter: 
      linkedin:
      github:
      user-circle: # This is a good icon for the author site or about page
```


- `username` - The username of the author that it's going to be use on post to mark the author of the post. 
- `name` - Full name for SEO purposes
- `profile_img` - Image for the profile card (size to 2000x1200px)
- `about` - Short description that will be in the profile card
- `email` - contact email of the author
- `social` - List of social networks for icons in the contact card and the footer ([Font Awesome](http://fontawesome.io/) is used, so only match the name of the icon, but do not include `fa-`)

### Build Settings

```yaml
markdown: kramdown
highlighter: rouge
incremental: false
future: false
plugins:
  - jekyll-paginate
  - jekyll-sitemap
  - octopress-autoprefixer
compress_html:
  clippings: all
  comments: all
  startings: [html, head, body]
include: 
  - _pages
exclude:
  - _screenshots
  - .DS_Store
  - Gemfile
  - Gemfile.lock
  - LICENSE.txt
  - README.md
```

- `markdown` - Markdown parser used in the site. 
- `highlighter` - The code highlighter used in the site. 
- `incremental` - If we are using incremental build. 
- `future` - If we are using future posts.
- `plugins` - Plugins used to build the site. 
- `compress_html` - What we are going to compress. 
- `include` - Folders that are included in `_site`.
- `exclude` - Folders that are excluded from `_site`.


### Outputting

```yaml 
paginate: 5
paginate_path: "/blog/page-:num"
permalink: /:year/:month/:day/:title/
```

- `paginate` - Number of blog posts per page
- `paginate_path` - URL structure of paginated pages
- `permalink` - URL structure of blog posts
- `timezone` - 

## How to...

### Create a post?

Post live in `_posts` folders and they have this yaml from matter structure: 

```yaml
---
layout: post
title: ""
author: username
date: 
categories:
description: 
image: 
image-fp:
---
```

This is the YAML front matter block for blog posts.

- `layout` - This field will always be post
- `title` - The title of the blog post
- `date` - The date that will appear on the blog post
- `categories` - Optional field that can be entered as an array or a list. The categories shouldn't have blank spaces. If you wan to have categories with more than one word, use a hyphen `-`. 
- `description` - Optional field for SEO (recommended to not go over 160 characters)
- `image` - The blog theme was designed for 2000x1200px images (optimize your images because this is a picture heavy theme)
- `image-fp` - Optional field for card layouts for image optimization and page speed (designed for 500x300px images)

### Add a responsive video

You can embed a video from YouTube, Vimeo, or Google Drive that responsively sizes to fit the width of its parent. To help with GDPR compliance, the include is using the privacy enhanced version of YouTube and Vimeo providers out of the box. This feature was copied from [Minimal Mistakes theme][mmistakes-theme], and they got the inspiration from <http://embedresponsively.com>. 

| Parameter  | Required     | Description                                                |
| ---------- | ------------ | ---------------------------------------------------------- |
| `id`       | **Required** | ID of the video                                            |
| `provider` | **Required** | Hosting provider of the video: `youtube`, vimeo`, or `google-drive` |

#### YouTube

To embed the following YouTube video at url `https://www.youtube.com/watch?v=XsxDH4HcOWA` (long version) or `https://youtu.be/XsxDH4HcOWA` (short version) into a post or page's main content you'd use:

```liquid
{% include video id="XsxDH4HcOWA" provider="youtube" %}
```

**Tip:** if you'd like to start the video at a particular timestamp, you can append `?start=110` (for instance) to the video `id` in order to have the video start at 1:50.
{: .notice--info }

#### Vimeo

To embed the following Vimeo video at url `https://vimeo.com/212731897` into a post or page's main content you'd use:

```liquid
{% include video id="212731897" provider="vimeo" %}
```

{% include video id="212731897" provider="vimeo" %}

#### Google Drive

To embed the following Google Drive video at url `https://drive.google.com/file/d/1u41lIbMLbV53PvMbyYc9HzvBug5lNWaO/preview` into a post or page's main content you'd use:

```liquid
{% include video id="1u41lIbMLbV53PvMbyYc9HzvBug5lNWaO" provider="google-drive" %}
```

{% include video id="1u41lIbMLbV53PvMbyYc9HzvBug5lNWaO" provider="google-drive" %}

## Issues

Please submit any issues [here](https://github.com/luispuerto/jr.luisspuerto.net/issues).

## Contributing

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v1.4%20adopted-ff69b4.svg)](code-of-conduct.md)

Please read [CONTRIBUTING.md][] for details about how to contribute and the process of submitting a pull request to this repo. Note that we have subscribe to the Contributor Covenant as our code of conduct while participating in this community. Please read [CODE_OF_CONDUCT.md][] if you don't know about it. 

We are more than happy to accept contributions to the code and even more to the content —like for example if you encounter a typo or something like that or you are a native English speaker and something you're reading isn't quite right. Even more if you think there is a mistake somewhere.

Please contribute.  

## Versioning

We don't use any kind of versioning system —and we don't know if it's appropriate for a project like a blog— and in general. If we used a versioning system we'll use [SemVer][]. You can check the available versions taking a look to the [tags on this repository][repo-tags]. 

## Authors

- **Thomas Vaeth** - _Template creator_ - [@thomasvaeth][]
- **Olalla Diaz** - _Author_ - [@oldiya][]
- **Luis Puerto** - _Author & maintainer of this fork_ - [@luispuerto][]

See also the list of [contributors][] who participated on this project either on my side or in [thomasvaeth's ones][trophy-contri]. 

## License

Following the original original author of the template, we've continued to license the code of this site as [MIT][]. On the other hand, the content of the site is under the copyright of Luis Puerto Díaz, the owner of the site. You can check the [LICENSE][] and [LICENSE4CONTENT][] files for more details. 

This site contains also other pieces of software and plugins of which you can check the license in [LICENSE4VENDORS][] file. 

## Acknowledgments

We would like to specially acknowledge Thomas Vaeth work creating this template which is awesome.  




[Jekyll]: https://jekyllrb.com
[LICENSE]: LICENSE
[LICENSE4CONTENT]: LICENSE4CONTENT.txt
[Bundler]: https://bundler.io
[JekyllDocs]: https://jekyllrb.com/docs/
[`Gemfile`]: Gemfile
[trophy-template]: http://thomasvaeth.com/trophy/
[Netlify]: https://netlify.com
[Gemfile]: Gemfile
[jemoji]: https://github.com/jekyll/jemoji
[FontAwesome]: http://fontawesome.io/
[JekylCodex]: https://jekyllcodex.org
[mmistakes-theme]: https://github.com/mmistakes/minimal-mistakes/
[CONTRIBUTING.md]: CONTRIBUTING.md
[CODE_OF_CONDUCT.md]: CODE_OF_CONDUCT.md
[SemVer]: http://semver.org/
[repo-tags]: https://github.com/luispuerto/jr.luispuerto.net/tags
[@thomasvaeth]: https://github.com/thomasvaeth
[@luispuerto]: https://github.com/luispuerto
[@oldiya]: https://github.com/oldiya
[contributors]: https://github.com/luispuerto/jr.luispuerto.net/graphs/contributors
[LICENSE4VENDORS]: LICENSE4VENDORS.md
[luispuerto.net]: https://luispuerto.net
[trophy-contri]: https://github.com/thomasvaeth/trophy-jekyll/graphs/contributors