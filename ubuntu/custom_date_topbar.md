# Custom Date in Top Bar

The [Clock Override](https://github.com/stuartlangridge/gnome-shell-clock-override) GNOME Shell Extension can be used to change the format of the date displayed in the top bar.

The [GLib Reference Manual](https://developer.gnome.org/glib/stable/glib-GDateTime.html#g-date-time-format) contains the format specifiers that can be used to build the date format.

I have used the following format:
```
%A, %e %B %Y - %l:%M %p
```

The displayed string is:
```
Sunday, 16 June 2019 - 8:25 PM
```
