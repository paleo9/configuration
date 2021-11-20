# configuration file ( rc file / dotfile) management with rcm

https://github.com/thoughtbot/rcm

Moves config files from the home directory into a new directory. The config files in the home directory are replaced by soft links to the corresponding files in the new directory.

## mkrc

mkrc — bless files into a dotfile managed by rcm

This program adds files to your dotfiles directory then installs it back into your home directory. It can install files under a tag or different source directory.

## rcup

rcup — update and install dotfiles managed by rcm

This is a program to update and install personal dotfiles. These dotfiles are managed in a separate directory. Use rcup to install files from your dotfiles directories or from host- or tag-specific directories within.

## rcdn

rcdn — remove dotfiles as managed by rcm

This program will remove all the rc files that the rcm(7) suite knows about. This can be further controlled with the -t and -d flags.

The files that are removed are symlinks. However, the COPY_ALWAYS setting in rcrc(5) modifies this.  If a rc file is not a symlink but an ancestor directory is, that directory is removed. If a rc file is not a symlink but is listed in COPY_ALWAYS the file is removed.


The rcdn program will run hooks before and after removing files, if these hooks exist. Hooks are executable programs inside the dotfiles directory, with the following names: hooks/pre-down and hooks/post-down.  These hooks are run each time rcdn is run and therefore must be idempotent.

Hooks will be executed one at a time, sorted alphabetically. For instance, hooks/pre-down/animals will run before hooks/pre-down/aquariums, and hooks/pre-down/4-eyes will run before hooks/post-down/2-u-nothing-compares.

## rcmd

lsrc — show dotfiles files managed by rcm

This program lists all configuration files, both the sources in the dotfiles directories and the destinations in your home directory.  See rcup(1), the DIRECTORY LAYOUT section, for details on the directory layout.
