# Changelog

## In master (unreleased)

- Avoid having the readline grow and shrink as much, which is annoying since it
requires the eyes to move up and down. Now the readline will only grow during
one read() invocation, and will keep the same fixed size regardless of the
amount of items in the completion list.

- Added howl.clipboard, new module for handling multiple clipboard items.

- Added a new configuration variable, `line_padding`, which allows for setting
extra padding for lines (issue #14)

- Removed fuzzy matching. It was noisy, and added little value.

- Added case boundary matching (e.g. 'cc' now match against 'CreditCard' and
'camelCase').

- Improved buffer-grep and buffer-structure commands:
  * They are about an order of magnitude faster for large files (issue #7)
  * The now provide live previews by automatically showing the currently
selected line in the buffer with the search highlighting (issue #15)

- `open` command: Completing a directory with `/` now changes directory
automatically (issue #5).

- Better structure view for Python mode (issue #12)

### VI bundle

- Fix pasting of line block yanks (i.e. <y><y>/<Y>/<d><d>)
- Fix count handling for yank
- Fix <y><y> to yank current line correctly
- Support '<' and '>' in visual mode
- New bindings: 'H', 'L', 'M'

### Command name changes

In order to streamline the naming of commands, the below commands have been
renamed:

* toggle-fullscreen -> window-toggle-fullscreen
* toggle-maximized -> window-toggle-maximized

* reflow-paragraph -> editor-reflow-paragraph

* search-forward -> buffer-search-forward
* repeat-search -> buffer-repeat-search
* replace -> buffer-replace
* replace-pattern -> buffer-replace-pattern
* reload-buffer -> buffer-reload
* force-mode -> buffer-mode

* mode-set -> set-for-mode
* buffer-set -> set-for-buffer

* new-view-above -> view-new-above
* new-view-below -> view-new-below
* new-view-left-of -> view-new-left-of
* new-view-right-of -> view-new-right-of

In addition, the following alias has been deprecated:

* fill-paragraph (alias for editor-reflow-paragraph)

The old command names are still present and working, but are deprecated and will
be removed in a future release.

### Bugs fixed

- Completion popup now closes upon entering a non-character (issue #9)

- Brace matching of braces before the cursor are now highlighted correctly
(issue #16)

- Buffer grep fixed for buffers with empty lines

- Byte code compilation no longers requires a $DISPLAY

- Overly long lines in the readline caused horizontal scrolling (issue #8)

- `buffer-replace` command failed to handle empty replacement strings

- Boundary matching was not working correctly in all cases

- Pasting in the readline did not update completions (issue #6)

## 0.1.1 (2014-03-15)

- Fix incompatibility with older Gtk versions.

## 0.1 (2014-03-15)

First public release.