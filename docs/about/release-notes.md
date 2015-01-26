# 更新说明

---

## 升级

使用 pip 升级 MkDocs 到最新版:

    pip install -U mkdocs

查看当前安装的版本使用 `pip freeze`:

    pip freeze | grep mkdocs

## 0.11.1 (2014-11-20)

* 修复: Fix a CSS wrapping issue with code highlighting in the ReadTheDocs
  theme. (#233)


## 0.11.0 (2014-11-18)

* 如果当前主题存在 404.html 则生成 404 页面 (#194)
* 修复: Fix long nav bars, table rendering and code highlighting in MkDocs
  and ReadTheDocs themes (#225)
* 修复: Fix an issue with the google_analytics code. (#219)
* 修复: Remove `__pycache__` from the package tar. (#196)
* 修复: Fix markdown links that go to an anchor on the current page (#197)
* 修复: Don't add `prettyprint well` CSS classes to all HTML, only add it in
  the MkDocs theme (#183)
* 修复: Display section titles in the ReadTheDocs theme (#175)
* 修复: Use the polling observer in watchdog so rebuilding works on
  filesystems without inotify. (#184)
* 修复: Improve error output for common configuration related errors. (#176)


## 0.10.0 (2014-10-29)

* 添加 Python 3.3 和 3.4 支持. (#103)
* Configurable Python-Markdown extensions with the config setting
  `markdown_extensions`. (#74)
* Added `mkdocs json` command to output your rendered
  documentation as json files. (#128)
* Added `--clean` switch to `build`, `json` and `gh-deploy` commands to
  remove stale files from the output directory (#157)
* Support multiple theme directories to allow replacement of
  individual templates rather than copying the full theme. (#129)
* 修复: Fix `<ul>` rendering in readthedocs theme. (#171)
* 修复: Improve the readthedocs theme on smaller displays. (#168)
* 修复: Relaxed required python package versions to avoid clashes. (#104)
* 修复: Fix issue rendering the table of contents with some configs. (#146)
* 修复: Fix path for embedded images in sub pages. (#138)
* 修复: Fix `use_directory_urls` config behaviour. (#63)
* 修复: Support `extra_javascript` and `extra_css` in all themes (#90)
* 修复: Fix path-handling under Windows. (#121)
* 修复: Fix the menu generation in the readthedocs theme. (#110)
* 修复: Fix the mkdocs command creation under Windows. (#122)
* 修复: Correctly handle external `extra_javascript` and `extra_css`. (#92)
* 修复: Fixed favicon support. (#87)

