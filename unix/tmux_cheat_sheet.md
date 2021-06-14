# tmux Cheat Sheet

Resources:
 - [tmuxcheatsheet.com](https://tmuxcheatsheet.com/)

## Reordering tmux windows

### Swap windows

1. Hit `Ctrl + b` and then `:` to go to the tmux command prompt
2. To swap windows 1 and 3: `swap-window -s 3 -t 1`

Source: https://superuser.com/a/343574/1143874

### Move a window one position

To the left: `swap-window -t -1`

To the right: `swap-window -t +1`

## Resizing tmux panes

Hit `Ctrl + b` and then `:` to go to the tmux command prompt

Use the `resize-pane` command. Examples:

```
:resize-pane -D (Resizes the current pane down)
:resize-pane -U (Resizes the current pane upward)
:resize-pane -L (Resizes the current pane left)
:resize-pane -R (Resizes the current pane right)
:resize-pane -D 10 (Resizes the current pane down by 10 cells)
:resize-pane -U 10 (Resizes the current pane upward by 10 cells)
:resize-pane -L 10 (Resizes the current pane left by 10 cells)
:resize-pane -R 10 (Resizes the current pane right by 10 cells)
```

Source: https://michaelsoolee.com/resize-tmux-panes

## Scrolling

`ctrl + b` and then `[`. Hit `ESC` to quit scroll mode.
