# 撰写文档

如何撰写 markdown 源码并安排目录结构.

---

## 目录结构

文档是普通的 Markdown 文件, 放到项目目录里.  通常目录以 `docs` 命名, 和 `mkdocs.yml` 配置文件一起放置于项目的顶级目录中.

最简单的项目目录结构可能是这样的:

    mkdocs.yml
    docs/
        index.md

默认项目主页是 `index`.  Markdown 源码文件的后缀可以是以下任意一种: `markdown`, `mdown`, `mkdn`, `mkd`, `md`.

你可以创建多个 markdown 文件以创建多页文档:

    mkdocs.yml
    docs/
        index.md
        about.md
        license.md

The file layout you use determines the URLs that are used for the generated pages.
Given the above layout, pages would be generated for the following URLs:

    /
    /about/
    /license/

You can also include your Markdown files in nested directories if that better suits your documentation layout.

    docs/
        index.md
        user-guide/getting-started.md
        user-guide/configuration-options.md
        license.md

Source files inside nested directories will cause pages to be generated with nested URLs, like so:

    /
    /user-guide/getting-started/
    /user-guide/configuration-options/
    /license/


## 链接

MkDocs 可以使用 Markdown 超链接语法来创建链接.

#### 内部超链接

创建内部超链接只需使用 Markdown 超链接语法, 包含目标 Markdown 文档的相对路径即可.

    Please see the [project license](license.md) for further details.

当运行 MkDocs 构建工具时, 超链接将指向相应的 HTML 页面.

你可以通过点击链接以在新编辑器窗口中打开目标 Markdown 文档.

如果目标文档在另一个目录中, 确保超链接中正确包含了相对路径.

    Please see the [project license](../about/license.md) for further details.

你可用通过锚链接以定位到目标文档的特定部分.  生成的 HTML 将正确转换路径部分, 而不会去改变锚链接部分.

    Please see the [project license](about.md#license) for further details.

<!--
#### Cross-referencing your documentation

Ex eam quem facilisi deserunt. Veri audiam audire id his, quo at aperiri moderatius. In admodum partiendo est, ei rebum minimum eam, singulis accusata delicatissimi eos ut. Imperdiet vulputate assueverit eos an, elit recusabo et usu. Eam ad euismod accusata vituperata. Oratio vocent nominavi ei eum.

    At mel verear persius torquatos, his dolores [Sensibus](ref:) id, alia urbanitas in usu.

Eam ad euismod accusata vituperata. Oratio vocent nominavi ei eum.

    Ne his mucius oporteat, [mea ut eros delicatissimi](ref:delicatissimi), iudico nonumes moderatius an mel.
-->

## 图片和多媒体

除了 Markdown 文件, 你可以在文档中包含其他文件, 这些文件将在你构建文档时被复制到指定位置.  可以包含图片和其他多媒体.

例如, 如果你的文档需要包含一个 [GitHub pages CNAME file](https://help.github.com/articles/setting-up-a-custom-domain-with-pages#setting-the-domain-in-your-repo) 和 一张 PNG 图片, 你可以安排目录结构如下:

    mkdocs.yml
    docs/
        CNAME
        index.md
        about.md
        license.md
        img/
            screenshot.png

要包含图片到你的源码文档, 只需使用 Markdown 语法:

    Cupcake indexer is a snazzy new project for indexing small cakes.

    ![Screenshot](img/screenshot.png)

    *Above: Cupcake indexer in progress*

图片链接将在构建时被嵌入, 如果使用了 Markdown 编辑器, 你还可以实时预览.

## Markdown 扩展

MkDocs 支持以下 Markdown 扩展.

<!--
#### Page metadata

Unum errem propriae vis cu, et deseruisse interpretaris eam. Illum graecis per an, ludus laoreet repudiare nec an, molestie recteque et eam. Purto duis rationibus id eum, pro et amet appetere referrentur, minim impedit ad ius. Et nostrud perfecto sapientem vix, et dicit impedit consequat vim. Vis liber blandit no.

At mel verear persius torquatos, his dolores sensibus id, alia urbanitas in usu. Te pri cibo blandit. Debet dolore periculis ei pro, eu vis vidit ignota, vim natum dicta cu. Et appareat delicata vix, mei at solum lorem quodsi, verterem electram sit eu. Eius malis cum an, pro malorum euripidis ad, oblique appetere est cu. Eos ei fugit deterruisset. Vix ei aliquip dolorem, usu te euripidis reformidans, volumus pertinacia ea eam.

    page_title: Lorum
	page_description: "lorum ipsum dolor"
	source_files: example.js, lorum.js

	# Lorum Ipsum

	Unum errem propriae vis cu, et deseruisse interpretaris eam. Illum graecis per an, ludus laoreet repudiare nec an, molestie recteque et eam.
-->

#### 表格

以下是一个简单的表格:

    First Header | Second Header | Third Header
    ------------ | ------------- | ------------
    Content Cell | Content Cell  | Content Cell
    Content Cell | Content Cell  | Content Cell

可以在起始和结束位置添加管道到表格:

    | First Header | Second Header | Third Header |
    | ------------ | ------------- | ------------ |
    | Content Cell | Content Cell  | Content Cell |
    | Content Cell | Content Cell  | Content Cell |

可以在分隔符行添加冒号已指定每一列的对其方式:

    First Header | Second Header | Third Header
    :----------- | :-----------: | -----------:
    Left         | Center        | Right
    Left         | Center        | Right

#### 代码块

以三个以上 \` （反引号）开始一行, 并在结束位置以相同数目的反引号 \` （反引号）开始一行即可包含一个代码块:

    ```
    Fenced code blocks are like Stardard
    Markdown regular code blocks, except that
    theye not indented and instead rely on a
    start and end fence lines to delimit the code
    block.
    ```

<!--
#### Admonitions

Ad est nibh suscipiantur. Quaeque deleniti delectus an has, tempor accusamus eu vix. Et democritum expetendis nam, putent fuisset duo ea, elaboraret efficiendi no vis.

    !!! danger "Don't try this at home"
        May cause grevious bodily harm
-->
