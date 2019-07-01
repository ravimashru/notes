# `grep` vs `egrep` vs `fgrep`

`egrep` is equivalent to `grep -E` [1]. It interprets the pattern as an "extended regular expression". In extended mode, some backslashes to escape certain characters are removed [2]:

Pattern with `grep` | Pattern with `egrep`
------ | ------
`abc\{3\}` | `abc{3}`
`a\(e\)+g` | `a(e)g`

It looks like a good idea to always use `egrep` or `grep -e` first, since the regular expressions I've alredy used (for example in JavaScript) are extended regular expressions and not basic regular expressions.


`fgrep` is equivalent to `grep -F` [1]. It interprets the pattern as a list of fixed strings, separated by new lines, any of which is to be matched.

For example, if you have a file `users.txt` with a list of users (one user on each line) and want to search the group file to see if any of the users are in it, you would use:

```
$ grep -F -f users.txt /etc/group
```


Sources:

[1] https://unix.stackexchange.com/questions/17949/what-is-the-difference-between-grep-egrep-and-fgrep

[2] https://en.wikibooks.org/wiki/Regular_Expressions/POSIX-Extended_Regular_Expressions