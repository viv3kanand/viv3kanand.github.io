---
layout: post
title: How to start blogging for newbies
date: 2020-04-02 05:16 +0530
author: Vivekanand
tag: 
location: Delhi, IN
---
I wasn't been able to write anything since a loooong time after my first blog. I wish to say I was occupied with a lot of work so I couldn't find much time. But that'll be so unfair to say. Becasue I was so damn lazy to write a blog. However, I was halfway writing an Exome Sequencing workflow (wetlab) which I lost under some circumstances. I don't want to go into details. I will write it again anyway.

But why now? Since the COVID-19 outbreak, we were all told not to got to lab and work from home until it is over. And god knows for how long. A recent study on simulating social distancing in India and how it affect the pandemic using [PyRoss](https://github.com/rajeshrinet/pyross) had shown that isolation period should be extended for even longer periods. Well, it is easier for us since we just need a laptop and an internet connection. It's been almost two weeks we're in home quarantine. But this isolation period is kicking me psychologically and emotionally, which I realized just yesterday. How I am seeing this is, I'm sort of refreshing my habits and which is why I have mood swings. So I should either set up some regulations to myself about creating a new habit under these current circumstances. So I choose bloging as one of them.

I really had no idea what to write when I started this post to be honest. However, it took some time for me to setup everything and getting started. So, I will go with a quick review on how to get started with a blog on github pages powered by [jekyll](https://jekyllrb.com/).

### Basic setup

At first, we need a base to work upon on your [github](https://www.github.com/). You can either set it up scratch or if you're as lazy as me, you can fork a theme and customize it. There are some initial setup for making the blog accessible online, which you'll find from [github pages website](https://pages.github.com/). Well, if you're are a beginner you can follow my way.

Find a blog theme powered by jekyll. For example I found this [beautiful-jekyll theme](https://github.com/daattali/beautiful-jekyll) from googling. Just follow the exact same steps on the documents. There you will `Fork` and do some setup to make your test blog accessible online. In case if you're wondering, by clicking `Fork` you're literally copying the whole content to your own github repository. And go to settings, and change `Repository name` field with `your-user-name.github.io`. And you should pretty much access your own blog through [https://your-user-name.github.io](). You can start editing the style and headers in the `_config.yml` file. That's all about it. Now you have a working blog ready which is absolutely free.

### Repository structure
With that being said, I will explain a little bit about the structure of the directories and files. Here's a list of some of the most important ones. And I will explain what some of those directories do. Some of them are not pretty useful if you're a newbie. However, if your'e looking for advanced information [this](https://jekyllrb.com/docs/structure/) might help.

```
.
├── _config.yml
├── _data
│   └── members.yml
├── _drafts
│   ├── draft1.md
│   └── drafts2.md
├── _includes
│   ├── footer.html
│   └── header.html
├── _layouts
│   ├── default.html
│   └── post.html
├── _posts
│   ├── 2007-10-29-First-post.md
│   └── 2009-04-26-Second-post.md
├── _sass
│   ├── _base.scss
│   └── _layout.scss
├── _site
├── .jekyll-metadata
└── index.html
```

Here, I will explain some of the locations you'd need to know. Obviously you must be now familiar with `_config.yml`. But, still you need to know two folders, `_posts` and `_drafts`.

`_posts` is the place where your blog posts will be saved in `markdown` format. [Markdown cheatsheet](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)
`_drafts` is the folder where your unpublished posts will be.

I will talk more about them in the coming session.

### Clone repository locally

Once you have it all set on github you can download the whole data locally using the `clone` function.

~~~bash
#Move to the folder where the repository should be downloaded
cd /home/Documents/

#clone your repository to the folder
git clone https://github.com/username/username.github.io
~~~
This should create a new folder based on the name of the name of the repository. 

~~~bash
#Move inside your repository
cd username.github.io

#Check if everything is in sync with the github page and the downloaded repository
git pull origin master
~~~

### Additional dependancy installation

Now We will need some software dependancies pre-installed to see the blog locally and to make the blogging a bit easier.

1. We need `Ruby` to be installed so that we can further install `jekyll bundler` which comes with a variety of options.
~~~bash
sudo apt-get install ruby-full build-essential zlib1g-dev
~~~

2. Now add ruby to the current user path. So that it will not make installations in the `root`
~~~bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
~~~

3. Finally, install Jekyll
~~~bash
gem install jekyll bundler
gem install jekyll-compose
~~~

### Getting acquainted with Jekyll

There are a lot of things we can do using Jekyll. In fact one of the awesome feature is that you can see your blog by simply calling the following in the `terminal`. Remember, we have to be in the folder where we downloaded the repository from.
~~~bash
jekyll serve
~~~

Well, there are a lot more. I will brieftly go through the most important ones (for newbies ;))

1. __Create a new page__
~~~bash
jekyll page "new-page"
~~~
will create a new markdown file in the current directory. If you have an `about` page that could be placed there.

2. __Create a new draft post__
~~~bash
jekyll draft "draft1"
~~~
This will create a markdown file in `_drafts/draft1.md`. You can then start writing your blog in that file using your favorite text editor. This page will not be posted as your blog. So you won't even see this change in the local blog page. However, you will be able to do it by runninmg the `jekyl serve` by,
~~~bash
jekyll serve --draft
~~~

3. __Create a new post__
~~~bash
jekyll post "post1"
~~~
This will create a markdown file with the current date and time in `_posts/year-month-date-post1.md`. And you will be able to see this post in the local blog. Which means this is going to be one of the blog post when you upload this online.

   Well then you must be wondering how to make the drafts visible in posts. That is the `publish` option for. But you might want to rename your draft file before publishing, right?

   ~~~bash
   rename _drafts/draft1.md "My-first-blog-post"
   ~~~
   And publish the post to copy that into `_posts` folder with proper formating
   ~~~bash
   jekyll publish _drafts/My-first-blog-post.md
   ~~~

   There is a lot more you can do. Have a look [here](https://github.com/jekyll/jekyll-compose) if you're interested.

### Time to get real

Let's now assume that you have wrote your first blog. Let's dump it into internet and call yourself a blogger. There are many ways you can do it. The most efficient way is to use `git`. There are even third party softwares with does this. But for now let's stick with old school.

Now when we know that there is nothing needs to be done, there are three steps. Stage, Commit and Push.
~~~bash
git add *
git commit -m "commit-message"
git push origin master
~~~

And done! You must be able to see your blog with the first blog post online!!!

Happy blogging <3