---
title: "Hugo Blackburn"
date: 2019-05-24T19:55:03-07:00
draft: false
tags: ["hugo", "markdown", "windows"]
topics: []
description: "This very site"
---

## Preamble

This site is a work in progress, a project as such. It has been enough of an effort for me that documenting the details is worthwhile for me, maybe for someone else too.

A statically-generated site allows all of your content to be created and maintained locally and allows you to control display elements with finer granularity.

All of my work and personal computing is and has been on Windows OS machines, for various reasons. So, I need a static site generator which has Windows users in mind: enter Hugo. Unlike Jekyll, Hugo runs out of the box, doesn't need Ruby or other dependencies, and has simple command line parameters. In my personal work flow, I mix GUI and CLI; CLI to actually run commands and do work, GUI to see what I'm actually doing. Next enter, Atom.

The Atom IDE natively includes project tree view, Git/Github, and has a excellent CMD/CLI plugins. In the past I have used Pycharm and will still swear by it for large, intense projects. But, Atom is lighter weight and has very good support so far.

## Theme Selection, First Hugo Site

I'm no web dev, so finding a theme with the layout and visual elements I want was a top priority. The [Blackburn][blackburn] theme fit the bill and has also been updated within the last few months.

The Hugo theme and the site config are tightly integrated, so I created my new Hugo site in a directory with the same name as the theme. I have a few different themes as separate Hugo sites with the only /content directory being common among them. This topology has worked out better than having multiple themes in the /themes directory and switching in the config.toml. _As I have gotten more familiar with Hugo, it seems more likely that I was just doing Hugo incorrectly. I should edit this later_

Finally, I added a boilerplate post and project, just to have a non-empty site. Also created "about" and "contact" static pages as placeholders.

Running "hugo server -D" allows you to see how the final site will look once published. The "-D" switch will include content with the "draft: true" flag set.

The final step in creating a Hugo site is building the html with the "hugo" command, which builds into the /public directory. This is publishable on your server, GitHub pages, etc.

## Configuring Blackburn

The most typical usage of Hugo is the blog format, which is generally what I am after, and which the Blackburn theme excels with. But, I also want to have projects, which I envision being like a single-page blog, just with a narrowed subject focus.

#### Default Config

The first config change was in ./config.toml.

A quick aside, all file/directory names are reference from '.' which is the root created by a "hugo new site" command.

To include tags or other additional info as default, edit the ./themes/archetypes/default.md file as shown below..

{{< highlight md >}}
+++
title = "{{ replace .Name "-" " " | title }}"
date = "{{ .Date }}"
draft = true
tags = []
topics = []
description = ""
+++
{{< / highlight >}}

Remember both tags and topics entries are lists of strings and must include " " around each entry.

Also, a quick aside on a personal preference (and what turned out to be an exercise in learning how a theme is structured) is changing the "post" content reference to "posts" instead. This required edits in:

* ./themes/blackburn/layouts/index.html
* ./themes/blackburn/layouts/posts/*

References to "post" had to be changed to "posts", no big deal.

#### Add Projects

In ./config.toml are the basic info entries for title/author/etc and also for the structure of the menu/sidebar for the desktop/mobile rendering. This is where I added an entry for projects. Just copying the snippet for "Posts" and editing for projects, the entry looks like:

{{< highlight toml >}}
[[menu.main]]
  name = "Projects"
  pre = "<i class='fa fa-folder fa-fw'></i>"
  weight = 3
  identifier = "projects"
  url = "/projects/"
{{< / highlight >}}

Notice in the "pre" line the "fa-folder" option. This is the small icon in the menu, contrasted with "fa-list" or "fa-tags" for other links. Use what you like here.

Now the menu has a link to ./projects, but so far it goes no where. In the ./themes/blackburn/layouts directory is a subdirectory "/posts/" which tells hugo how to build posts content. We need to create a "projects" subdirectory to do the same. A simple copy-paste followed by editing references from "posts" to "projects" should be sufficient. 

#### Future Changes

The contact and about pages still need to be populated. Depending on how visible I want to make myself this may include links to project repos, etc.


[blackburn]: https://github.com/yoshiharuyamashita/blackburn
