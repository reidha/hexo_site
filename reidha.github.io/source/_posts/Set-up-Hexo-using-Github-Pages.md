---
title: Set up Hexo using Github Pages
date: 2019-08-11 21:03:54
tags:
categories:
- Hexo
---

I will write down all steps you need to start a Hexo site in Github Pages.

## What is Hexo?
[Hexo official page](https://hexo.io/)
Hexo is a lightweight and simple blog framework.
You can make your original blog super easily by Hexo and Github Pages.
One important note: this is totally FREE :)

## Steps
### 1. Create a repository in Github
Go to Github and create a new repository for your site here.
Note that the repository name has to be **{YOUR_GITHUB_ID}.github.io**. (e.g. reidha.github.io)
{% asset_img repository.png %}

### 2. Install 
Install hexo by npm.
``` bash
$ npm install -g hexo-cli
```

### 3. Create a directory for your site
``` bash
$ hexo init {YOUR_GITHUB_ID}.github.io
$ cd {YOUR_GITHUB_ID}.github.io
$ npm install
```

### 4. Edit the basic information in the config file
The config file has many parameters, but for now let's edit some basic information.
``` bash
$ vim _config.yml
```

Update *Site* and *URL*. [Official documentation](https://hexo.io/docs/configuration) is the best reference.
``` bash
~~~~~ _config.yml ~~~~~
# Site
title: Product blog
subtitle:
description:
keywords:
author: {YOUR_NAME}
language: en
timezone: Asia/Bangkok

# URL
url: https://{YOUR_GITHUB_ID}.github.io
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:
```

### 5. Start a local server
You can check how your site looks like by starting a local server. This really helps you edit pages.
Type the commends below after opening another Terminal window. (I'm a Mac user.) This is because you cannot input anything in the Terminal window if you start the local server.
``` bash
$ cd path/to/{YOUR_GITHUB_ID}.github.io
$ hexo server
```
Now you can go to http://localhost:4000/. All changes are immediately reflected here.
If you edit *_config.yml*, you have to stop the local server by *Ctrl+C* and start it again.

### 6. Make a new post
`hexo new` will create a new md file. You can simply edit the file. Again, every time you modify the md file, changes can be checked in http://localhost:4000/.
``` bash
$ hexo new "New Post Name"
$ vim source/_post/New-Post-Name.md
```

### 7. Delete the initial post
When you create a use site, there is a default page named "hello world". If you don't need it, delete the md file.
``` bash
$ rm source/_posts/hello-world.md
```

### 8. Set up the deployer
This is the essential step to show your site using Github Pages.
``` bash
$ npm install hexo-deployer-git -S
$ vim _comfig.yml
```

``` bash
~~~~~ _config.yml ~~~~~
# Deployment
deploy:
  type: git
  repo: https://github.com/{YOUR_GITHUB_ID}/{YOUR_GITHUB_ID}.github.io.git
  branch: master
  message:
```

### 9. Deploy!
``` bash
$ hexo clean
$ hexo deploy
```

### 10. Visit your site
Everything is done! Please go to your Github page! (e.g. https://reidha.github.io)

## My environment
``` bash
$ npm -v
6.10.3
```
