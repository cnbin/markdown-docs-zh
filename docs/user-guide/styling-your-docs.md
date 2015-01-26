# 配置主题

如何配置主题.

---

## 内建主题

#### Bootstrap

![Bootstrap](http://bootstrapdocs.com/v2.3.1/docs/assets/img/examples/bootstrap-example-fluid.png)

#### Read the Docs

![ReadTheDocs](https://docs.readthedocs.org/en/latest/_images/screen_mobile.png)

#### The bootswatch themes

![Amelia](http://bootswatch.com/amelia/thumbnail.png)

![Cerulean](http://bootswatch.com/cerulean/thumbnail.png)

![Cosmo](http://bootswatch.com/cosmo/thumbnail.png)

![Cyborg](http://bootswatch.com/cyborg/thumbnail.png)

![Flatly](http://bootswatch.com/flatly/thumbnail.png)

![Journal](http://bootswatch.com/journal/thumbnail.png)

![Readable](http://bootswatch.com/readable/thumbnail.png)

![Simplex](http://bootswatch.com/simplex/thumbnail.png)

![Slate](http://bootswatch.com/slate/thumbnail.png)

![Spacelab](http://bootswatch.com/spacelab/thumbnail.png)

![United](http://bootswatch.com/united/thumbnail.png)

![Yeti](http://bootswatch.com/yeti/thumbnail.png)

## 自定义主题

自定义主题最少只需要一个 `base.html` 模板文件就可以了. 模板目录应当被放置到与 `mkdocs.yml` 配置文件相同目录下. 在 `mkdocs.yml` 文件中指定 `theme_dir` 选项为包含 `base.html` 文件的目录即可. 例如, 如下目录结构:

    mkdocs.yml
    docs/
        index.md
        about.md
    custom_theme/
        base.html
        ...

你需要配置自定义主题目录选项:

    theme_dir: 'custom_theme'

如果和 `theme` 选项结合使用, 自定义主题可以用于替换内建主题的特定部分. 例如, 上述目录结构如果你设置了 `theme: mkdocs` , 那么 `base.html` 将替换主题中的相应文件, 而其他的则保持不变. 这在你希望对主题进行小调整时是十分有用的.

最简单的 `base.html` 结构如下:

    <!DOCTYPE html>
    <html>
      <head>
      </head>
      <body>
        {{ content }}
      </body>
    </html>

`mkdocs.yml` 中指定的每一页的文档内容使用 `{{ content }}` 标签来插入. 可以像处理普通 HTML 文档一样导入样式表和脚本. 相应的, 导航栏和内容列表可以通过  `nav` 和 `toc` 对象自动生成和包含. 如果你想设计自定义的主题, 最好从修改 [内建主题](https://github.com/tomchristie/mkdocs/tree/master/mkdocs/themes) 开始.
