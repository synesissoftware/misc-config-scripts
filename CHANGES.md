# misc-config-scripts - CHANGES <!-- omit in toc -->


## Table of Contents <!-- omit in toc -->

- [0.6.0](#060)
- [0.5.0](#050)
- [0.4.1](#041)
- [0.4.0](#040)
- [0.3.2](#032)
- [0.3.1](#031)
- [0.3.0](#030)
- [0.2.0](#020)
- [0.1.0](#010)
- [0.0.3](#003)
- [0.0.2](#002)
- [0.0.1](#001)
- [0.0.0](#000)


## 0.6.0

* Added per-language **.gitattributes** files;


## 0.5.0 - 10th August 2026

* Added per-language **settings.json** files;


## 0.4.1 - 25th July 2026

* Improved boilerplate;


## 0.4.0 - 28th August 2025

* Added **.gitconfig**;


## 0.3.2 - 28th August 2025

* **unix/.commonrc**:
  * fixed `rbenv` initialization (#2);
* added **LICENSE**;
* added **README.md**;
* added settings;
* added ignores;


## 0.3.1 - 6th February 2024

* **unix/.commonrc**:
  * directed ALERT messages to standard error;


## 0.3.0 - 10th December 2023

* **unix/.commonrc**:
  * improved handling of aliasing;
  * eschewed use of double square brackets;
  * improved diagnostics;
  * used `source` over `.`;
  * quoted paths;
  * whitespace and various simple boilerplate changes;
* added **.gitattributes**;


## 0.2.0 - 18th July 2022

* **unix/.commonrc**:
  * suppressed echo if not a TTY;
* tidied files;


## 0.1.0 - 26th June 2021

* **unix/.commonrc**:
  * changed processing of environment variables, such that content of **~/.common_environment_variables** is always included if present, and then **.bash_environment_variables** (Bash-only) / **.zsh_environment_variables** (zsh-only) is included if present;
  * fixed Bash prompt;
  * dealt with some Bash implementations that won't update prompt when calling function;
  * fixed finding of Go (as in golang);
  * added sourcing of **~/.common_custom_rc**, alternatively **~/.bash_custom_rc** (if Bash) or **~/.zsh_custom_rc** (if zsh);
  * cleaned up, ensuring `~` replaced by `$HOME`;
  * automatically brings in **/etc/bashrc** (when Bash);
  * consolidated (between Bash and Zsh) the definition(s) of ignore-elements;
  * refactored;
  * added support for a prompt-leader, obtained by defining (in your own custom environment variables) the variable `PROMPT_LEADER`;
  * added support for customising environment variables;
* added ignores;


## 0.0.3 - 8th June 2021

* tidied files;
* fixed issues;


## 0.0.2 - 25th April 2021

* improved prompt;
* improved paths;
* added history ignores;
* added mods;


## 0.0.1 - 24th April 2021

* added **unix/.commonrc**;
* added ignores;


## 0.0.0 - 23th April 2021

* initial commit;


<!-- ########################### end of file ########################### -->
