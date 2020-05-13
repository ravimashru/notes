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


## Indenting Commands

`==` - indent the current line.

`gg=G` - Re-indent the entire file.

