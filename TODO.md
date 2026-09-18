# misc-config-scripts - TODO <!-- omit in toc -->


## Table of Contents <!-- omit in toc -->

- [Functional improvements](#functional-improvements)
- [Performance improvements](#performance-improvements)
- [Packaging improvements](#packaging-improvements)


## Functional improvements

* [x] ~~~Enhance Git command prompt to show terse status counts (`+` staged, `*` changed, `?` unknown/untracked) in a single-pass `git status` call~~~ ✅;
* [ ] Add a facility for preloading command history from a file (e.g. **~/.common_history_preload**) or an environment variable;


## Performance improvements

* \<none>;


## Packaging improvements

* [x] ~~~Phase 0: declare ownership with **misc-dev-scripts**; freeze **settings.json/** and **gitattributes/** product catalogs~~~ - ✅;
* [x] ~~~Phase 1: complete **self** boilerplate for this repo (**`.editorconfig`**, **`.vimrc`**; confirm **`.gitattributes`**, **`.gitignore`**, **`.vscode/settings.json`**)~~~ - ✅;
* [x] ~~~Phase 2 companion: **misc-dev-scripts** **0.6.0** owns canonical project drop-ins; keep legacy catalogs until Phase 3~~~ - ✅;
* [x] ~~~Phase 3: remove legacy **settings.json/** and **gitattributes/** product trees; README product surface = **`.commonrc`** + **`.gitconfig`** only~~~ - ✅;
* [x] ~~~Phase 4: align self **`.vscode/settings.json`**, **`.gitignore`**, and **`.gitattributes`** with **misc-dev-scripts** templates gold (keep shell/docs **`.editorconfig`** / **`.vimrc`**)~~~ - ✅;
* [ ] Add sample **.bashrc** and **.zshrc** files under **unix/** to bootstrap **unix/.commonrc** cleanly;
* [x] ~~~Add GitHub Actions workflow (**ci.yml**) to validate **unix/.commonrc** syntax~~~ ✅;
* [ ] Extend **ci.yml** to run ShellCheck and validate syntax for Zsh as well as Bash;


<!-- ########################### end of file ########################### -->
