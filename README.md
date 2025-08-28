# misc-config-scripts <!-- omit in toc -->

Miscellaneous Configuration Scripts


## Table of Contents <!-- omit in toc -->

- [Bash/Zsh Run-scripts](#bashzsh-run-scripts)
- [Git configuration files](#git-configuration-files)


## Bash/Zsh Run-scripts

* [.commonrc](./unix/.commonrc) - a basic .bashrc / .zshrc, which includes the following features:
  * works with both **bash** and **zsh**;
  * defines prompt (`PS1`) that includes elements user-name, host-id, directory, and git-branch (if any);
  * locates and, if exists, preloads **/etc/bashrc**;
  * conditionally aliases:
    * `cb` to `pbcopy` (macOS) if identified, or `clip` (Windows) if identified;
    * `hist` to `history` if bash, or `history 0` if zsh.
    * `ldd` to `otool -L` (macOS);
    * `ll` to most useful incantation of `ls` (operating-system specific);
    * `vi` to `vim`;
  * conditionally locate and, if exist, loads environment variables from:
    * **"$HOME/.common_environment_variables"**; and
    * **"$HOME/.bash_environment_variables"** (Bash); or
    * **"$HOME/.zsh_environment_variables"** (Zsh);
  * sets `GOPATH` environment variable if directory identified;
  * supplements `PATH` environment variable with the following, for each that exist:
    * **"$HOME/.bin"**;
    * **"$HOME/bin"**;
    * **"/Applications/Xcode.app/Contents/Developer/usr/bin"**;
  * initialises **rbenv**, if it is found;
  * sources all functions in any files in **"$HOME/.bin/fn_*sh"**;
  * setting a bunch of history ignores (`HISTIGNORE` in Bash; `HISTORY_IGNORE` in Zsh);
  * conditionally locate and, if exist, loads the first of:
    * **"$HOME/.common_custom_rc"**;
    * **"$HOME/.bash_custom_rc"**;
    * **"$HOME/.zsh_custom_rc"**;


## Git configuration files

* [.gitconfig](git/.gitconfig) - a drop-in for **~/.gitconfig** with the following aspects:
  * aliases:
    * **alias** - lists all aliases;
    * **br** - **branch**, ordered by commit date;
    * **cb** - obtain name of current branch;
    * **ch** - **checkout**;
    * **co** - **commit**;
    * **cp** - **cherry-pick**;
    * **dis** - diff of index, ignore space;
    * **diss** - diff of index, ignore all space;
    * **diw** - diff of working, ignore space;
    * **diww** - diff of working, ignore all space;
    * **l**, **l1**, **l10**, **l20**, **l30**, **l40**, **l50**, **l60**, **la**, **lg**, **ln**, **logline** - various forms of **log**;
    * **meff** - **merge** but fast-forward only;
    * **msq** - **merge** with squash and no-commit;
    * **puff** - **pull** but fast-forward only;
    * **rev** - **remote** verbose;
    * **sl** - list stash with lots of useful details;
    * **st** - **status**;
  * default branch **master**;
  * pull behaviour **simple**;



<!-- ########################### end of file ########################### -->

