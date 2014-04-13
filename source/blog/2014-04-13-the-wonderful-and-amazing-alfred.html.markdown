---
title: The Wonderful and Amazing Alfred
date: 2014-04-13 18:03 UTC
tags:
---

One of the first days of gSchool, our instructor Mike Gehard (@msgehard) had Dash, a documentation browser, open to documentation of a Ruby class with a few quick jabs at the keyboard. "What was that?", was the question. "That is Alfred", was the reply.

Since that day, I have added and created a number of Alfred workflows that I use daily while at gSchool. The workflows are able to use a variety of languages including Ruby! How awesome is that! While I use others for personal needs, I am going to showcase the five workflows I use daily at gSchool. While there is a free version of [Alfred](http://www.alfredapp.com/), none of these will work without the "Powerpack" addon, i.e., the paid version.

### The 5 Workflows

1. [Dash](http://kapeli.com/) - (activated within Dash)
2. Ruby Gems - [Download in BlueVajra gitHub](https://github.com/BlueVajra/ruby_gem_workflow)
3. [Evernote](http://www.evernote.com) - [Download in Alfred Forums](http://www.alfredforum.com/topic/840-evernote-80-search-create-append-preview-set-reminders-all-within-alfred/page-18)
4. Github / Gists - [Will Farrell's GitHub](https://github.com/willfarrell/alfred-github-workflow)
5. Pivotal Tracker - [Download on GitHub](https://github.com/kevnull/pivotal-tracker-alfred-workflow)
6. in my next blogpost, we will walk through making a simple timer workflow!

For Alfred commands, I have `Opt + space` set up to launch the Alfred command bar, but you can also set up hot-keys for other Alfred actions

### Dash
[Dash](http://kapeli.com/) (activated within Dash)

![Alfred Dash](alfred_dash.png)

You have to purchase Dash to use this workflow, but as a beginning student, it is pretty amazing. Simply type the following in the Alfred command bar:

`dash ruby:hash`

and immediately, Dash pops up with the appropriate docset and subset. You have to have the appropriate Dash docset loaded, but you can see Dash documentation for that.

### Ruby Gems
[Download in BlueVajra gitHub](https://github.com/BlueVajra/ruby_gem_workflow)

![Alfred Dash](alfred_rubygem.png)

This was the first workflow I created. While I found another ruby-gem workflow, it didn't have the one feature I wanted, so I created it with a little [ruby-gems.org](http://www.ruby-gems.org) api help! For the first few weeks at gSchool, we have been spinning up quite a few new apps, and for each of those, we have been using Gemfiles. For those that are not Rubyists, these Gemfiles list various dependancies and the versions of those dependancies our program may have. This workflow has 3 options:

- `gem s rails` - this will search ruby-gems.org for the query
- `gem g sinatra` - this will go to the actual gem page on ruby-gems.org (if it exists)
- `gem c sequel` - this returns `gem 'sequel', '~> 4.9.0'` to the clipboard, so you can paste it in your gemfile. ཡག་པོ་དུགས།་ (That is Tibetan for "How Wonderful!" pronounced "yag po doo")



### Evernote
[Alfred Forums](http://www.alfredforum.com/topic/840-evernote-80-search-create-append-preview-set-reminders-all-within-alfred/page-18)

![Alfred Dash](alfred_evernote.png)

This is my newest Alfred workflow, so I have not used it as much as others, but it is proving to be pretty amazing. We have multiple short and long lectures, talks and workflows we are dealing with on a daily basis, and I have been using Evernote to keep track of it all. I track lecture notes, sql commands, blog ideas and web snippits.

This is a powerhouse workflow. See the [Alfred Forums](http://www.alfredforum.com/topic/840-evernote-80-search-create-append-preview-set-reminders-all-within-alfred/page-18) for more information. I have been using two main functions:

- `enn Title here #tag1 #tag2` - creates a new evernote. If you hold down `ctrl` when you press enter, the new note will be created and be opened. If not, whatever is in the clipboard will be pasted into the body text.
- `ens <query here>` or `ens #<tag here>`

If you use Evernote, these two alone are amazing.

### Github and Gists
[Download on GitHub](https://github.com/willfarrell/alfred-github-workflow)

![Alfred Dash](alfred_github.png)

This is a great workflow from Will Farrell, who has written a number of other workflows that I have yet to check out. It works with your GitHub account allowing search access to your repos and gists. I use gist quite a bit for storing sample files, scripts and workflows.

Checkout the GitHub page for all the commands. You will have to setup the user and password first, but after than you can use the following commands.

- `git my <query>` - this lists your personal repos. By adding a query, it will search through your repos
- `git search <query>` - this will search through GitHub
- `gist <query>` - this searches through your own gists.
- `gist create` - this will create a new gist by opening a blank gist in a browser.

### Pivotal Tracker
[Download on GitHub](https://github.com/kevnull/pivotal-tracker-alfred-workflow)

![Alfred Dash](alfred_tracker.png)

This is a simple workflow that could use a big upgrade. But I still use it. It can only link to one account, and you have to code that into the script. That being said, at gSchool, we each have our own personal Trackers, as well as project trackers. I linked my personal tracker which I use as a to-do list. Every day I look at it and see what I ahve to do, or need to finish. I often use it quickly when something comes up in class that I need to study more or research.

- `pt <title>` - this creates a new feature story in backlog with a title
- `pt c <title>` - this creates a new chore story in backlog with a title

### Overview

Hopefully this will shed some light on some useful ways to use Alfred while studying code... or even professionally writing it! I know I will add more over time, but I also don't want to add too many at once, I will never get into the habit of using them. I find it takes about a week for each of these to get into my regular daily workflow.

If you find any that you think I may find helpful, let me know! Next week I will walk you through creating a simple pomodoro or timer app you can use in Alfred!


#### Other Workflows of Note
Will Farrell, the writer of the GitHub workflow has written and collected a number of others, check them out on [GitHub](https://github.com/willfarrell/alfred-workflows/blob/master/README.md)
