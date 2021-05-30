# Vim Cheat Sheet

## Get Help

`:help` - open the help docs. `Ctrl+w - o` to open help docs in full screen.

`:helpgrep <term>` - find help for a specific term. Use `:cnext` and `:cprevious` to cycle through matches.



## Configurations

`set cindent` - Enable "C style" indenting. Example: when you type `if (flag) {` and hit enter, the next line will be indented. When you type the closing `}` of the block, unindenting will happen.

`set shiftwidth=N` - use N spaces for each step of indent when using `cindent`.

`set tabstop=N` - number of white spaces for a single tab.

`set expandtab` - replace tab character with spaces.

`syntax on` - enable syntax highlighting.

`set splitbelow` - open split pane below open pane

`set splitright` - open split pane to the right of open pane

To check for configured value, use `?`, e.g. `:set tabstop?`.

## View whitespace characters

Add to `.vimrc`:

```
set listchars=eol:$,tab:>·,trail:~,extends:>,precedes:<,space:·
```

Show the special characters using `:set list` and hide them using `:set nolist`

## Indenting Commands

`==` - Correct indentation of the current line.

`gg=G` - Re-indent the entire file.

`>>` - Increase indentation of current line.

`<<` - Decrease indentation of the current line.


## Searching

After searching, an empty search pattern will repeat the last search. This works with /, :s and :g.

Source: https://vim.fandom.com/wiki/Searching

## Change current working directory

In Vim: `:cd`

In NERDTree: Focus on node in NERDTree tab that needs to be set as cwd and type characters `cd`

## NERDTree

Open selected node in a new tab: place cursor on the folder and press `t`.

## Buffers

- Open buffer in split
  - Horizontal split: `:sb N`
  - Vertical split: `vert sb N`

## Highlighting

- Highlight all occurences of word under cursor (`*`)
- Highlight all occurences of words that contain word under cursor (`g*`)
- Hide all highlights - `:noh`
