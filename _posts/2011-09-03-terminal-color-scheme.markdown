---
layout: post
status: publish
published: true
title: terminal color scheme
author: admin
author_login: admin
author_email: denzeljiang@gmail.com
wordpress_id: 54
wordpress_url: http://note.jzr.me/?p=54
date: 2011-09-03 07:20:38.000000000 -04:00
categories:
- Uncategorized
tags: []
comments: []
---

```bash
!Colors
*foreground: #696969
*background: #fffef6
*color0: #363636
*color8: #424242
*color1: #C37561
*color9:  #D19485
*color2: #A0A57E
*color10: #7f8264
*color3: #b58b62
*color11: #DEBC9C
*color4: #1d2b41
*color12: #98A1B9
*color5: #AB716D
*color13: #b4d2c8
*color6: #98B9B1
*color14: #769293
*color7: #9ba0a7
*color15: #6e7383
```

```bash
!XTerm Color Theme
XTerm*background:       #121212
XTerm*foreground:       #DDDDDD

!black
XTerm*color0:         #353535
XTerm*color8:         #666666
!red
XTerm*color1:           #7b3303
XTerm*color9:           #804015
!green
XTerm*color2:         #556B2F
XTerm*color10:        #4e6d19
!brown/yellow
XTerm*color3:           #a67b07
XTerm*color11:          #a67b07
!blue
XTerm*color4:           #427288
XTerm*color12:          #6b94a7
!magenta
XTerm*color5:           #705b46
XTerm*color13:          #664a30
!cyan
XTerm*color6:         #A7A15E
XTerm*color14:        #F0E68C
!white
XTerm*color7:         #DDDDDD
XTerm*color15:        #bcbcbc
```

这个试一下是最喜欢的，其他太暗了，不过适合长时间看，这个比较明亮！

```bash
*background: #353333
*foreground: #ffffff

*color0: #464444
*color1: #EF3460
*color2: #BDEF34
*color3: #EFC334
*color4: #34BDEF
*color5: #B300FF
*color6: #3DD8FF
*color7: #FFFFFF

*color8: #8a8888
*color9: #F25A7D
*color10: #DCF692
*color11: #F6DF92
*color12: #92AAF6
*color13: #DF92F6
*color14: #5AF2CE
*color15: #FFFFFF
```

```bash
*background: #121212
*foreground: #cdcdcd
!black
*color0:   #222222
*color8:   #454545
!red                                                                              
*color1:   #9E5641
*color9:   #CC896D
!green                                                                            
*color2:   #6C7E55
*color10:  #C4DF90
!yellow                                                                           
*color3:   #CAAF2B
*color11:  #FFE080
! cyan                                                                             
*color4:   #4c8ea1
*color12:  #6bc1d0
! magenta                                                                          
*color5:   #956D9D
*color13:  #C18FCB
! blue                                                                             
*color6:   #7FB8D8
*color14:  #B8DDEA
! white                                                                            
*color7:   #808080
*color15:  #cdcdcd
```

```bash
!! Makes URLs Openable via FireFox
URxvt.perl-ext-common:  default,matcher
URxvt.urlLauncher:      /usr/bin/firefox
URxvt.matcher.button:   1 

!! Fonts
URxvt*font:             xft:ProggyTinyTTSZ:pixelsize=16
URxvt*boldFont:         xft:ProggyTinyTTSZ:pixelsize=16
URxvt*italicFont:       xft:ProggyTinyTTSZ:pixelsize=16
URxvt*bolditalicFont:   xft:ProggyTinyTTSZ:pixelsize=16

!! Transparency
URxvt.foreground:	      #FFFFFF
URxvt.transparent:      true
URxvt.shading:          16
URxvt.tintColor:        #FFFFFF
URxvt.depth:            32
URxvt.background:       rgba:0d00/0d00/0d00/eeee


!! Encoding & Window
URxvt*scrollBar:        false
URxvt*utf8:             2

!! XFT Setting
Xft.dpi:        82
Xft.antialias:  true
Xft.rgba:       rgb
Xft.hinting:    true
Xft.hintstyle:  hintslight

!! Themes
! trapd00r colorscheme

!*color0: rgb:00/00/00
!*color1: rgb:4C/8C/38
!*color2: rgb:5F/A1/23
!*color2: rgb:27/CA/25
!*color3: rgb:A4/00/8A
!*color4: rgb:5f/7b/8a
!*color5: rgb:1D/90/B6
!*color6: rgb:68/68/68
!*color7: rgb:ff/ff/ff
!*color8: rgb:3C/3C/3C
!*color9: rgb:D6/93/00
!*color10: rgb:95/c7/49
!*color11: rgb:BB/00/5e
!*color12 rgb:6b/7b/8a
!*color13: rgb:BB/7D/00
!*color14: rgb:36/7F/C5
!*color15: rgb:ff/ff/ff

!Theme Two
*background: rgb:00/00/00
*foreground: rgb:7f/7f/7f
*color0:     rgb:00/00/00
*color1:     rgb:9e/18/28
*color2:     rgb:ae/ce/92
*color3:     rgb:96/8a/38
*color4:     rgb:41/41/71
*color5:     rgb:96/3c/59
*color6:     rgb:41/81/79
*color7:     rgb:be/be/be
*color8:     rgb:66/66/66
*color9:     rgb:cf/61/71
*color10:    rgb:c5/f7/79
*color11:    rgb:ff/f7/96
*color12:    rgb:41/86/be
*color13:    rgb:cf/9e/be
*color14:    rgb:71/be/be
*color15:    rgb:ff/ff/ff
```