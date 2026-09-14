# misc-config-scripts <!-- omit in toc -->


Miscellaneous Configuration Scripts

![Shells](https://img.shields.io/badge/shells-bash%20%7C%20zsh-blue.svg)
[![License](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![Version](https://img.shields.io/badge/version-0.8.2-blue.svg)](https://github.com/synesissoftware/misc-config-scripts/blob/master/CHANGES.md)
[![GitHub release](https://img.shields.io/github/v/release/synesissoftware/misc-config-scripts.svg)](https://github.com/synesissoftware/misc-config-scripts/releases/latest)
[![Last Commit](https://img.shields.io/github/last-commit/synesissoftware/misc-config-scripts)](https://github.com/synesissoftware/misc-config-scripts/commits/master)
[![CI](https://github.com/synesissoftware/misc-config-scripts/actions/workflows/ci.yml/badge.svg)](https://github.com/synesissoftware/misc-config-scripts/actions/workflows/ci.yml)


## Table of Contents <!-- omit in toc -->

- [Introduction](#introduction)
- [Ownership and migration (Phase 0)](#ownership-and-migration-phase-0)
- [Bash/Zsh run-scripts](#bashzsh-run-scripts)
- [Git configuration](#git-configuration)
- [VS Code settings (legacy catalog)](#vs-code-settings-legacy-catalog)
- [Git attributes (legacy catalog)](#git-attributes-legacy-catalog)
- [Related projects](#related-projects)
- [Project Information](#project-information)


## Introduction

**misc-config-scripts** is a collection of **machine / shell environment** configuration resources intended to be **copied** into developer environments (and, historically, some project trees).

**Target product surface (after cutover):** **`.commonrc`** and **`.gitconfig`** only. Language-specific **project** drop-ins (**`.editorconfig`**, **`.gitattributes`**, **`.gitignore`**, **`.vimrc`**, **`.vscode/settings.json`**) move to [**misc-dev-scripts**](https://github.com/synesissoftware/misc-dev-scripts) `templates/`.

Each resource has a canonical copy in its owning repository; consuming projects should record the relevant **VERSION** in their **CHANGES.md** when updating.

Sibling project: [**misc-dev-scripts**](https://github.com/synesissoftware/misc-dev-scripts) (project helpers and project drop-in templates).


## Ownership and migration (Phase 0)

**Status: intent declared — cutover not complete.** Do not dual-ship new language templates here.

| Kind | This repo | **misc-dev-scripts** |
| --- | --- | --- |
| **Self** (this repository’s own) **`.editorconfig`**, **`.gitattributes`**, **`.gitignore`**, **`.vimrc`**, **`.vscode/settings.json`** | ✅ (complete in a later phase if still missing) | ✅ |
| **Templates:** **`.gitconfig`**, **`.commonrc`** | ✅ only | ❌ |
| **Templates:** language-specific **`run_all_unit_tests.sh`**, **`.editorconfig`**, **`.gitattributes`**, **`.gitignore`**, **`.vimrc`**, **`.vscode/settings.json`** | ❌ (legacy trees frozen) | ✅ only |

**Freeze:** do **not** add new language directories or expand the product catalogs under **`settings.json/`** or **`gitattributes/`**. Fix defects in place if required; new work belongs under **misc-dev-scripts** `templates/`.


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


## VS Code settings (legacy catalog)

> **Deprecated for new work.** Canonical home after cutover: **misc-dev-scripts** `templates/vscode/`. This tree remains until migration completes.

Drop-in workspace settings are provided as **.vscode/settings.json** templates under **settings.json/**.

* Language-specific templates cover C, C++, C#, Go, JavaScript, Python, Ruby, Rust, and Zig;
* **settings.json/generic/settings.json** provides a union for mixed-language workspaces; and
* templates establish shared formatting, whitespace, ruler, and language-tooling preferences without machine-specific paths.

See [**settings.json/README.md**](./settings.json/README.md) for the template conventions, contents, and layout.


## Git attributes (legacy catalog)

> **Deprecated for new work.** Canonical home after cutover: **misc-dev-scripts** `templates/gitattributes/`. This tree remains until migration completes.

Drop-in root **.gitattributes** templates are provided under **gitattributes/**.

* Language-specific templates cover C, C++, C#, Go, JavaScript, Python, Ruby, Rust, and Zig;
* **gitattributes/c_cxx/.gitattributes** combines the C and C++ rules for mixed native-language projects;
* **gitattributes/generic/.gitattributes** provides a union of all language templates; and
* templates normalise text to LF, identify common binaries, configure language-aware diffs, and mark common generated build paths.

See [**gitattributes/README.md**](./gitattributes/README.md) for the template conventions, sources, and usage.


## Related projects

A peer project providing development helpers and project drop-in templates is [**misc-dev-scripts**](https://github.com/synesissoftware/misc-dev-scripts).


## Project Information

* **VERSION** — see [**VERSION**](./VERSION);
* **CHANGES** — see [**CHANGES.md**](./CHANGES.md);
* **NEWS** — see [**NEWS.md**](./NEWS.md);
* **TODO** — see [**TODO.md**](./TODO.md);
* **License** — BSD-3-Clause; see [**LICENSE**](./LICENSE).


<!-- ########################### end of file ########################### -->
