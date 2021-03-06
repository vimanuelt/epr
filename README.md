# `$ epr.py`

![Screenshot](https://raw.githubusercontent.com/wustho/epr/master/screenshot.png)

CLI Epub reader written in Python 3.7 with features:

- remember last read file (just run `epr.py` without any argument)
- remember last reading state for each file (per file saved state written to `$HOME/.epr`)
- adjustable text area width
- support EPUB3 (tested on some, still no media supports though)
- added secondary vim-like key bindings

NOTE for developers: Please no Pull Requests until probably **July 2019**, I already have something in mind for this proj that I'd like to work on it first and I feel bad closing PR without merging it. But I always appreciate the supports, from the deepest of my heart.

Inspired by: https://github.com/aerkalov/ebooklib & https://github.com/rupa/epub

## Limitations

- [x] ~~saving state doesn't work with a file that has `[]` in its name, e.g. `[EPUB]some_title.epub`. As workaround, just rename and remove `[]` from its name.~~
- [ ] doesn't support images
- [x] ~~doesn't support epub3~~
- minimum width: 22 cols
- resizing terminal will reset to beginning of current chapter
- saved state (reading position & width, but not reading chapter) will reset 
  if current terminal size is incompatible with latest reading state

## Dependencies

- ~~`html2text`~~
- `curses`

Started from `v1.2.0`, `epr.py` no longer requires `html2text` library. But if you have trouble with it, you probably need to go use older version provided in release page.

## Usage

To read an EPUBFILE:


```shell
$ epr.py EPUBFILE
```

To read last read epub:

```shell
$ epr.py
```

Key bindings:
```
    Help            : ?
    Quit            : q
    Scroll down     : ARROW DOWN    j
    Scroll up       : ARROW UP      k
    Page down       : PGDN          J   SPC
    Page up         : PGUP          K
    Next chapter    : ARROW RIGHT   l
    Prev chapter    : ARROW LEFT    h
    Beginning of ch : HOME          g
    End of ch       : END           G
    Shrink          : -
    Enlarge         : =
    TOC             : t
    Metadata        : m
```
