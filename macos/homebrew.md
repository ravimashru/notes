# Homebrew

`brew` - core command for Homebrew. Typically deals with command line software.
`brew cask` - extension to brew that allows management of GUI applications.

`formulae` - package definition files for brew.
`cask` - package definition files for brew cask.
(casks and formulae are written in a Ruby-based DSL that describe how to install something)

`Cellar` - where Homebrew install things on your system and then adds symlinks from standard locations to it.

`tap` - source of formulae. Default is `homebrew/core`. You can add more, and even your own by creating a github repo called `homebrew-<something>`, putting your formula file in it, and then using `brew tap <username>/<something>`.

