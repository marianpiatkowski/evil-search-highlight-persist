# Emacs Evil-Search-Highlight-Persist Minor Mode

This is a fork of the [original](https://github.com/juanjux/evil-search-highlight-persist)
unmaintained, evil-search-highlight-persist.

This Emacs extension will make `isearch` and `evil-ex-search-incremental` (the "slash search") to
highlight the search term (given as a regexp) in all the buffer and persistently until you make
another search or clear the highlights with the `search-highlight-persist-remove-all` command
(default binding to `C-x SPC`). This is how Vim search works by default when you enable
`hlsearch`. This extension requires the `highlight` extension.

![IMAGE](http://i.imgur.com/mwANxIA.png)

## Usage

To enable:

```cl
(require 'highlight)
(require 'evil-search-highlight-persist)
(global-evil-search-highlight-persist t)
```

To only highlight strings with length greater than or equal to 3

```cl
(setq evil-search-highlight-string-min-len 3)
```

To change the default highlight face:

```cl
(set-face-background 'evil-ex-lazy-highlight "gold")
(set-face-foreground 'evil-ex-lazy-highlight "black")
```

To enable highlighting (and un-highlighting) across *all* windows, similar to what Vim does:

```cl
(setq evil-search-highlight-persist-all-windows t)
```

## Alternatives

This behavior is built-in to Evil if one if using the evil-search module:

```cl
(setq evil-search-module 'evil-search)
```

However, this is not available when using isearch, which I beleive provides a superior searching
experience. This package also provides the benefit of being able to highlight all current windows,
similar to what Vim does.

In my opinion, this package would be made obsolete if evil-search was tweaked to behave
[more like isearch](https://github.com/emacs-evil/evil/issues/813), and once evil supports
[highlighting across all windows](https://github.com/emacs-evil/evil/issues/805).
