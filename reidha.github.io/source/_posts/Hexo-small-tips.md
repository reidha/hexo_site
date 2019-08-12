---
title: Hexo small tips
date: 2019-08-12 22:37:14
tags:
- Hexo
categories:
- Hexo
---

## Tags and Categories
When you create new posts, the top of md files looks like this.
``` bash
title: Hexo small tips
date: 2019-08-12 22:37:14
tags:
```

You can simply add tags and categories.
``` bash
title: Hexo small tips
date: 2019-08-12 22:37:14
tags:
- Foo
- Bar
categories:
- Foo
- Bar
```

## RSS Feed
When you started a Hexo site, did you notice that this icon didn't work?
{% asset_img RSS-icon.png RSS %}

*atom.xml* is not found.
{% asset_img atom-before.png %}

This is a very simple solution.

### 1. Install `hexo-generator-feed`
``` bash
$ npm install hexo-generator-feed -S
```

### 2. Edit *_config.yml*
``` bash
~~~~~ _config.yml ~~~~~
feed:
  type: atom
  path: atom.xml
  limit: 20
```

Now you can check *atom.xml* is generated after restarting the server.
{% asset_img atom-after.png %}

