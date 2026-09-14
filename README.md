# misc-config-scripts <!-- omit in toc -->


Miscellaneous Configuration Scripts

![Shells](https://img.shields.io/badge/shells-bash%20%7C%20zsh-blue.svg)
[![License](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![Version](https://img.shields.io/badge/version-0.9.0-blue.svg)](https://github.com/synesissoftware/misc-config-scripts/blob/master/CHANGES.md)
[![GitHub release](https://img.shields.io/github/v/release/synesissoftware/misc-config-scripts.svg)](https://github.com/synesissoftware/misc-config-scripts/releases/latest)
[![Last Commit](https://img.shields.io/github/last-commit/synesissoftware/misc-config-scripts)](https://github.com/synesissoftware/misc-config-scripts/commits/master)
[![CI](https://github.com/synesissoftware/misc-config-scripts/actions/workflows/ci.yml/badge.svg)](https://github.com/synesissoftware/misc-config-scripts/actions/workflows/ci.yml)


## Table of Contents <!-- omit in toc -->

- [Introduction](#introduction)
- [Ownership](#ownership)
- [Bash/Zsh run-scripts](#bashzsh-run-scripts)
- [Git configuration](#git-configuration)
- [Related projects](#related-projects)
- [Project Information](#project-information)


## Introduction

**misc-config-scripts** is a collection of **machine / shell environment** configuration resources intended to be **copied** into developer environments.

**Product surface:** **`.commonrc`** (**unix/.commonrc**) and **`.gitconfig`** (**git/.gitconfig**) only.

Language-specific **project** drop-ins (**`.editorconfig`**, **`.gitattributes`**, **`.gitignore`**, **`.vimrc`**, **`.vscode/settings.json`**) and helpers such as **`run_all_unit_tests.sh`** live in [**misc-dev-scripts**](https://github.com/synesissoftware/misc-dev-scripts) (`templates/` and `shell-scripts/`).

When updating a consumer, cite this repository’s **VERSION** in that project’s **CHANGES.md**.


## Ownership

**Phase 4:** self **`.vscode/settings.json`**, **`.gitignore`**, and **`.gitattributes`** are aligned with **misc-dev-scripts** `templates/` gold (shell / docs form for attributes); **`.editorconfig`** / **`.vimrc`** remain shell / docs self files.

| Kind | This repo | **misc-dev-scripts** |
| --- | --- | --- |
| **Self** (this repository’s own) **`.editorconfig`**, **`.gitattributes`**, **`.gitignore`**, **`.vimrc`**, **`.vscode/settings.json`** | ✅ | ✅ |
| **Templates:** **`.gitconfig`**, **`.commonrc`** | ✅ only | ❌ |
| **Templates:** language-specific **`run_all_unit_tests.sh`**, **`.editorconfig`**, **`.gitattributes`**, **`.gitignore`**, **`.vimrc`**, **`.vscode/settings.json`** | ❌ | ✅ only |


## Bash/Zsh run-scripts

* **.commonrc** (**unix/.commonrc**) is a basic **.bashrc** / **.zshrc** that:
  * works with both `bash` and `zsh`;
  * defines prompt (`PS1`) that includes elements user-name, host-id, directory, and git-branch (if any) with terse status counts (`+` staged green, `*` changed cyan, `?` unknown/untracked red; branch yellow);
  * locates and, if exists, preloads **/etc/bashrc**;
  * conditionally aliases:
    * `cb` to `pbcopy` (macOS) or `clip` (Windows);
    * `hist` to `history` (Bash) or `history 0` (Zsh);
    * `ldd` to `otool -L` (macOS);
    * `ll` to the most useful host-specific `ls` invocation; and
    * `vi` to `vim`;
  * loads environment variables from:
    * **$HOME/.common_environment_variables**; and
    * **$HOME/.bash_environment_variables** (Bash) or **$HOME/.zsh_environment_variables** (Zsh);
  * sets `GOPATH` when an appropriate directory is found;
  * supplements `PATH` with **$HOME/.bin**, **$HOME/bin**, and the Xcode developer-tools directory when present;
  * initialises `rbenv` when found;
  * sources functions from **$HOME/.bin/fn_*sh**;
  * configures history ignores (`HISTIGNORE` in Bash and `HISTORY_IGNORE` in Zsh); and
  * loads the first available **$HOME/.common_custom_rc**, **$HOME/.bash_custom_rc**, or **$HOME/.zsh_custom_rc**.


## Git configuration

* **.gitconfig** (**git/.gitconfig**) is a drop-in for **~/.gitconfig** with:
  * aliases:
    * `alias` — list all aliases;
    * `br` — list branches ordered by commit date;
    * `cb` — obtain the current branch;
    * `ch`, `co`, and `cp` — checkout, commit, and cherry-pick;
    * `dis`, `diss`, `diw`, and `diww` — staged and working-tree diffs with whitespace control;
    * `l`, `l1`, `l10`, `l20`, `l30`, `l40`, `l50`, `l60`, `la`, `lg`, `ln`, and `logline` — various forms of `log`;
    * `meff` and `msq` — fast-forward-only and squash merges;
    * `puff` — fast-forward-only pull;
    * `rev` — verbose remotes;
    * `sl` — detailed stash listing; and
    * `st` — status;
  * `master` as the default initial branch; and
  * `simple` pull behaviour.


## Related projects

A peer project providing development helpers and project drop-in templates is [**misc-dev-scripts**](https://github.com/synesissoftware/misc-dev-scripts) (**0.6.0+** `templates/` and `shell-scripts/`).


## Project Information

* **VERSION** — see [**VERSION**](./VERSION);
* **CHANGES** — see [**CHANGES.md**](./CHANGES.md);
* **NEWS** — see [**NEWS.md**](./NEWS.md);
* **TODO** — see [**TODO.md**](./TODO.md);
* **License** — BSD-3-Clause; see [**LICENSE**](./LICENSE).


<!-- ########################### end of file ########################### -->
