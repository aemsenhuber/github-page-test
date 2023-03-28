---
title: miscellaneous
date: 2023-03-28
---

miscellaneous
---

Useful generic commands are:

To have the list of all the cpus load

```htop```

For a less graphical overview which combines Multicore programs into one CPU usage number (100% per fully used logical core), use

```top -c```

This can also be used to give a (mostly) accurate overview of swap usage by pressing “f” to enter the options menu and then selecting (space) and sorting by (“s”) SWAP.

To timeout a program after e.g. 60 seconds

```timeout 60 ./executable```

EMACS
---

Some good emacs modifications (add at the end of ~/.emacs file)

```
;;window header with file name
(setq frame-title-format "%b")
```

```
;;mark trailing spaces and tabs in red
(setq-default show-trailing-whitespace t)
```

```
;;set font size
(set-face-attribute 'default nil :height 120)
```

```
;; dark background, light font color
(add-to-list 'default-frame-alist '(foreground-color . "#E0DFDB"))
(add-to-list 'default-frame-alist '(background-color . "#2e3436"))
```
