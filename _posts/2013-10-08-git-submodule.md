---
layout: post
status: publish
published: true
title: Git submodule workflow
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2013-10-08 01:48:25
categories:
- Uncategorized
tags: []
comments: []
---

### git submodule workflow

1. Add submodule repo.git

   `git submodule add repo.git ./path/to/submodule`

2. Update submodule

   `git submodule foreach git pull`

3. If submodule contain submodule

   `git submodule update --recursive`

3. Specify branch to update

   `git submodule foreach git pull origin master`

---

### clone repo contains submodule

```bash
$ git clone repo
$ git submodule init
#pull submodule and checkout the current version
$ git submodule update
```

One command trick:

`git clone --recursive repo`

