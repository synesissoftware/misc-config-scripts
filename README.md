# misc-config-scripts <!-- omit in toc -->


Miscellaneous Configuration Scripts

![Shells](https://img.shields.io/badge/shells-bash%20%7C%20zsh-blue.svg)
[![License](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![Last Commit](https://img.shields.io/github/last-commit/synesissoftware/misc-config-scripts)](https://github.com/synesissoftware/misc-config-scripts/commits/master)
[![CI](https://github.com/synesissoftware/misc-config-scripts/actions/workflows/ci.yml/badge.svg)](https://github.com/synesissoftware/misc-config-scripts/actions/workflows/ci.yml)


## Table of Contents <!-- omit in toc -->

- [Introduction](#introduction)
- [Bash/Zsh run-scripts](#bashzsh-run-scripts)
- [Git configuration](#git-configuration)
- [VS Code settings](#vs-code-settings)
- [Git attributes](#git-attributes)
- [Related projects](#related-projects)
- [Project Information](#project-information)


## Introduction

**misc-config-scripts** is a collection of configuration resources intended to be **copied** into Synesis and related projects or developer environments.

The resources cover shell startup, Git, VS Code, and GitHub-hosted repository attributes. Each resource has a canonical copy in this repository; consuming projects should record the relevant **VERSION** in their **CHANGES.md** when updating.

Sibling project: [**misc-dev-scripts**](https://github.com/synesissoftware/misc-dev-scripts) (development and test-runner scripts).


## Bash/Zsh run-scripts

* **.commonrc** (**unix/.commonrc**) is a basic **.bashrc** / **.zshrc** that:
  * works with both `bash` and `zsh`;
  * defines a prompt (`PS1`) containing the user name, host, directory, and Git branch;
  * locates and preloads **/etc/bashrc** when present;
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


## VS Code settings

Drop-in workspace settings are provided as **.vscode/settings.json** templates under **settings.json/**.

* Language-specific templates cover C, C++, C#, Go, JavaScript, Python, Ruby, Rust, and Zig;
* **settings.json/generic/settings.json** provides a union for mixed-language workspaces; and
* templates establish shared formatting, whitespace, ruler, and language-tooling preferences without machine-specific paths.

See [**settings.json/README.md**](./settings.json/README.md) for the template conventions, contents, and layout.


## Git attributes

Drop-in root **.gitattributes** templates are provided under **gitattributes/**.

* Language-specific templates cover C, C++, C#, Go, JavaScript, Python, Ruby, Rust, and Zig;
* **gitattributes/c_cxx/.gitattributes** combines the C and C++ rules for mixed native-language projects;
* **gitattributes/generic/.gitattributes** provides a union of all language templates; and
* templates normalise text to LF, identify common binaries, configure language-aware diffs, and mark common generated build paths.

See [**gitattributes/README.md**](./gitattributes/README.md) for the template conventions, sources, and usage.


## Related projects

A peer project providing development and test-runner scripts is [**misc-dev-scripts**](https://github.com/synesissoftware/misc-dev-scripts).


## Project Information

* **VERSION** — see [**VERSION**](./VERSION);
* **CHANGES** — see [**CHANGES.md**](./CHANGES.md);
* **NEWS** — see [**NEWS.md**](./NEWS.md);
* **TODO** — see [**TODO.md**](./TODO.md);
* **License** — BSD-3-Clause; see [**LICENSE**](./LICENSE).


<!-- ########################### end of file ########################### -->
