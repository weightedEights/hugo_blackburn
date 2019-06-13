---
title: "Create A New Git Repo To Track Existing Files And Directories"
date: 2019-06-13T10:44:58-07:00
draft: false
tags: ["git", "github", ]
topics: []
description: ""
---

## Preamble

If you have existing files which you want to begin tracking in a git repository, there a few non-obvious hoops to jump through. This process assumes the repo will be created on Github, but should be easy to follow if that is not the case.

## Git Particulars, Initializing

Creating a new repo on Github is very straightforward. I recommend adding a license and a readme.md both for their utility and so the repo is non-empty.

#### Clone Existing Repo

This is the part which is easy to get tripped up on. When cloning a repo, the destination directory must be empty. So if there are existing files, they must all be moved to a temporary location. The flow will be like:

1. Move existing files to temporary directory, destination of repo now empty.
2. Clone repo into empty destination directory.

Once the repo has cloned, you should see the license and readme files (why its nice to initialize a non-empty repo to begin with).

#### Track Existing Files

Now you have a tracked directory, move everything back.

1. Move existing files back into destination.
2. Track, commit, and merge files.

That should do the trick.
