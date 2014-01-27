---
layout: post
status: publish
published: true
title: 'svg standard for open venue map '
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 298
wordpress_url: http://note.jzr.me/?p=298
date: 2012-10-12 09:09:00.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---
```xml
<?xml version="1.0" standalone="no"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg xmlns="http://www.w3.org/2000/svg"  version="1.1" height="600" width="460">

	<style type="text/css">
	</style>

	<g id="viewport">

	</g>
</svg>
```

viewport is the id for manipulation of the svg

69.114.6.16
zencoding

```
svg#venuen-slug-name[xmlns="http://www.w3.org/2000/svg" version="1.1" height width]>style+g#viewport>(g>path*1+text*1)+(g#v1-s$.section*2>path+text+g#v1-s.row*3>path+text+path#v1-s-r-s$.seat*3)
```