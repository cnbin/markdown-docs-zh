# 配置

所有配置参数.

---

## 简介

项目配置在 `mkdocs.yml` 文件中设置.

配置文件中至少应包含 `site_name` 选项.  其余选项都是可选的.

## 项目信息

### site_name

这个是 **必须的**, 代表用于项目文档的主标题.  例如:

    site_name: Mashmallow Generator

渲染主题时该选项将作为 `site_name` 环境变量传递.

### site_url

设置站点的 URL. 这将添加带有规范的 URL 的 link 标签到 HTML 头部.

**默认值**: `null`

### repo_url

如果设置了该项, 每个页面将会添加一个链接到你的  GitHub 或 Bitbucket 版本库.

    repo_url: https://github.com/example/repository/

**默认值**: `null`

### repo_name

如果设置了该项, 每个页面将会添加一个链接到你的  GitHub 或 Bitbucket 版本库.

**默认值**: `'GitHub'` 或 `'Bitbucket'` 如果 `repo_url` 匹配相应域名, 否则为 `null`

### site_description

设置站点描述. 这将这 HTML 头部添加一个 meta 标签.

**默认值**: `null`

### site_author

设置站点作者. 这将这 HTML 头部添加一个 meta 标签.

**默认值**: `null`

### site_favicon

设置 favicon . 需要将 `favicon.ico` 放到 `docs/` 目录, 配置文件将如下所示:

```yaml
site_favicon: favicon.ico
```

**默认值**: `null`

### copyright

设置站点版权信息.

**默认值**: `null`

### google_analytics

设置 Google 站点分析工具.

```yaml
google_analytics: ['UA-36723568-3', 'mkdocs.org']
```

**默认值**: `null`


## 目录结构

### pages

该选项设置需要生成的页面范围.

该选项为一个列表.  列表中的每一行用一个字符串列表表示一个页面.  第一个字符串代表源文件的路径, 应为相对于 `docs_dir` 的路径.  其余字符串代表导航条中的页面标题.

下面的例子将在构建阶段生成三个页面:

    pages:
    - ['index.md', 'Introduction']
    - ['user-guide.md', 'User Guide']
    - ['about.md', 'About']

假定 `docs_dir` 采用默认值 `docs`, 则构建阶段源文件的路径分别为 `docs/index.md`, `docs/user-guide.md` 和 `docs/about.md`.

如果你有大量项目文档, 你需要用导航头部来按目录来组织你的导航.  你可以在 page 选项中包含一个额外的字符串来表示导航头部, 如下所示:

    pages:
    - ['index.md', 'Introduction']
    - ['user-guide/creating.md', 'User Guide', 'Creating a new Mashmallow project']
    - ['user-guide/api.md', 'User Guide', 'Mashmallow API guide']
    - ['user-guide/configuration.md', 'User Guide', 'Configuring Mashmallow']
    - ['about/license.md', 'About', 'License']

## 构建目录


### theme

设置站点主题, 查看可用的主题
[文档样式](styling-your-docs.md).

**默认值**: `'mkdocs'`


### theme_dir

设置自定义主题.  这可以是相对目录, 相对于你的配置文件位置来解析该路径, 也可以是绝对路径.

查看 [文档样式](styling-your-docs.md#custom-themes) 了解自定义主题.

**默认值**: `null`


### docs_dir

设置包含 markdown 源码的目录.  这可以是相对目录, 相对于你的配置文件位置来解析该路径, 也可以是绝对路径.

**默认值**: `'docs'`


### site_dir

设置生成的 HTML 和其他文件所在目录.  这可以是相对目录, 相对于你的配置文件位置来解析该路径, 也可以是绝对路径.

**默认值**: `'site'`

**Note**: 如果你使用了版本控制系统, 通常不希望 *构建输出* 文件被提交到版本库, 而只需要对 *源码* 进行版本控制.  例如, 如果使用 `git` , 你可以添加以下代码到 `.gitignore` 文件:

    site/

如果使用其他版本控制系统请参阅相应的文档以排除特定目录.


### extra_css

设定主题所需的额外的样式文件.

**默认值**: 默认情况下 `extra_css` 将包含 `docs_dir` 目录下的样式文件, 如果没有找到则为 `[]` (空表).


### extra_javascript

设定主题所需的额外的脚本文件.

**默认值**: 默认情况下 `extra_javascript` 将包含 `docs_dir` 目录下的脚本文件, 如果没有找到则为 `[]` (空表).

## 预览控制

### use_directory_urls

This setting controls the style used for linking to pages within the documentation.

The following table demonstrates how the URLs used on the site differ when setting `use_directory_urls` to `true` or `false`.

Source file  | Generated HTML       | use_directory_urls=true  | use_directory_urls=false
------------ | -------------------- | ------------------------ | ------------------------
index.md     | index.html           | /                        | /index.html
api-guide.md | api-guide/index.html | /api-guide/              | /api-guide/index.html
about.md     | about/index.html     | /about/                  | /about/index.html

The default style of `use_directory_urls=true` creates more user friendly URLs, and is usually what you'll want to use.

The alternate style can occasionally be useful if you want your documentation to remain properly linked when opening pages directly from the file system, because it create links that point directly to the target *file* rather than the target *directory*.

**默认值**: `true`

### dev_addr

Determines the address used when running `mkdocs serve`.  Setting this allows you to use another port, or allows you to make the service accessible over your local network by using the `0.0.0.0` address.

As with all settings, you can set this from the command line, which can be usful, for example:

    mkdocs serve --dev-addr=0.0.0.0:80  # Run on port 80, accessible over the local network.

**默认值**: `'127.0.0.1:8000'`

## Formatting options

### markdown_extensions

MkDocs uses the [Python Markdown][pymkd] library to translate Markdown files into HTML. Python Markdown supports a variety of [extensions][pymdk-extensions] that customize how pages are formatted. This setting lets you enable a list of extensions beyond the ones that MkDocs uses by default (`meta`, `toc`, `tables`, and `fenced_code`).

For example, to enable the [SmartyPants typography extension][smarty], use:

    markdown_extensions: [smartypants]

**默认值**: `[]`

[pymdk-extensions]: http://pythonhosted.org/Markdown/extensions/index.html
[pymkd]: http://pythonhosted.org/Markdown/
[smarty]: https://pypi.python.org/pypi/mdx_smartypants
