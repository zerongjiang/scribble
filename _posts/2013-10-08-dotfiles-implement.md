---
layout: post
status: publish
published: true
title: dotfiles implement
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
date: 2013-10-08 01:15:56
categories:
- Uncategorized
tags: []
comments: []
---

### clone the repo


```bash
$ git clone git://github.com/denzeljiang/dotfiles
$ git submodule init
$ git submodule update
```

---

### provision

```bash
cd dotfiles
ln -rs .config/awesome ~/.config/awesome
ln -rs .gitconfig ~/.gitconfig
ln -rs .vimrc ~/.vimrc
ln -rs .vim ~/.vim
ln -rs .screenrc ~/.screenrc
```

---

### Todo
Hopefully I need a script accept modules to be provisoned.

`./dotfiles.sh -m awesome,vim,sreen`

