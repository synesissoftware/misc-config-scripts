# misc-config-scripts - Changes <!-- omit in toc -->


## 0.4.1 - 25th July 2026

* improved boilerplate;


## 0.4.0 - 28th August 2025

* Added **.gitconfig**;


## 0.3.2 - 28th August 2025

* **unix/.commonrc**:
  * `rbenv` init fix (#2);
* boilerplate:
  + added **LICENSE**;
  * added **README**;
  * settings;
  * ignores;


## 0.3.1 - 6th February 2024

* **unix/.commonrc**:
  ~ directing to standard-error for ALERT messages;


## 0.3.0 - 10th December 2023

* **unix/.commonrc**:
  ~ improved handling of aliasing;
  ~ eschew use of double square brackets;
  ~ improved diagnostics;
  ~ use of `source` over `.`;
  ~ quoting paths;
  ~ whitespace and various simple boilerplate changes;
* added **.gitattributes**;


## 0.2.0 - 18th July 2022

* **unix/.commonrc**:
  ~ now suppresses echo if tty;
* tidying;


## 0.1.0 - 26th June 2021

* **unix/.commonrc**:
  * changed processing of environment variables, such that content of **~/.common_environment_variables** is always included if present, and then **.bash_environment_variables** (Bash-only) / **.zsh_environment_variables** (zsh-only) is included if present;
  * fixing Bash prompt;
  * dealing with some Bash implementations that won't update prompt when calling function;
  * fixed finding of go (as in golang);
  * added sourcing of **~/.common_custom_rc**, alternatively **~/.bash_custom_rc** (if Bash) or **~/.zsh_custom_rc** (if zsh);
  * cleaning up, ensuring ~ replaced by `$HOME`;
  * automatically brings in **/etc/bashrc** (when Bash);
  * consolidated (between bash and zsh) the definition(s) of ignore-elements;
  * refactoring;
  * added support for a prompt-leader, obtained by defining (in your own custom environment variables) the variable `PROMPT_LEADER`;
  * added support for customising environment variables;
* ignores;


## 0.0.3 - 8th June 2021

* tidying;
* fix;


## 0.0.2 - 25th April 2021

* prompt;
* paths;
* history ignores;
* mods;


## 0.0.1 - 24th April 2021

* added **unix/.commonrc**;
* ignores;


## 0.0.0 - 23th April 2021

Initial commit


<!-- ########################### end of file ########################### -->

