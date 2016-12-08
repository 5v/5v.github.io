---
layout: post
title: "Remove powerline characters in vim-airline"
date: 2015-08-15 18:09:00 +01:00
categories: linux windows
tags: vim
---
I can never remember how to remove *all* of the powerline characters with
[vim-airline][], so here it is for next time I forget.

```vim
let g:airline_left_sep=""
let g:airline_right_sep=""
let g:airline_left_alt_sep=""
let g:airline_right_alt_sep=""
let g:airline_powerline_fonts=0
```

[vim-airline]: https://github.com/bling/vim-airline
