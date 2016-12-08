+++
title = "Use SLIME REPL for lisp in Emacs"
date = "2016-04-20T06:34:00+01:00"
tag = "emacs"
+++
To keep a (somewhat) sane Emacs configuration, I use
[`use-package`][use-package]. When starting to learn Common Lisp, I naturally
added SLIME to my tool box. Whilst following various Lisp tutorials, I realised
my REPL wasn't quite the same as other users had - this is because I was using
the basic `*inferior-lisp*` `comint` buffer. Although I was correctly setting
the `slime-contribs` variable in my `init.el`, I wasn't actually using its
contents when SLIME was loading. Having found [this][slime-repl-no-start] I
worked out that all I was missing was `(slime-setup)`, so my `use-package` block
for SLIME became:

```lisp
(use-package slime
  :ensure t
  :config
  (setq inferior-lisp-program "sbcl")
  (setq slime-contribs '(slime-fancy))
  (slime-setup))
```

Now, using `M-x slime` fires up the fancy SLIME REPL, instead of the basic
`comint` *inferior lisp* shell.

[use-package]: https://github.com/jwiegley/use-package
[slime-repl-no-start]: https://github.com/slime/slime/issues/258
