---
layout: post
title: "Build Personal Blog bases On Github and Jekyll"
data: 2020-02-09 01:01:01 +0800
---

* content
{:toc}


# Jekyell
## Construction
> `_config.yml`：**保存配置数据**
> >(配置选项可以直接在命令行中进行设置，将配置数据保存在`_config.yml`中就不用记住那些命令了。)
> 
> `_drafts`：**未发布的文章**。(这些文件的格式中都没有 `title.MARKUP` 数据)
> > `begin-with-the-crazy-ideas.textile`
> > `on-simplicity-in-technology.markdown`
>
> `_includes`：**加载**`_includes`**包含部分到布局或者文章中以方便重用**。
> >(可以用这个标签 `{% include file.ext %}` 来把文件 `_includes/file.ext`包含进来。) 
> > `footer.html`
> > `header.html`
>
> `_layouts`：**包裹在文章外部的模板**。
> >(布局可以在 `YAML` 头信息中根据不同文章进行选择。标签 `{{ content }}` 可以将`content`插入页面中。) 
> > `default.html`
> > `post.html`
> 
> `_posts`：**要发布的文章**。（文件格式必须符合: YEAR-MONTH-DAY-title.MARKUP。 `永久链接`可以在文章中自己定制，但是数据和标记语言都是根据文件名来确定的。）
> > `year-month-date-filename.md`
> >`year-month-date-filename.textile`
>
> `_data`:**存放格式化好的网站数据**。
> >`jekyll` 的引擎会自动加载在该目录下所有的 `yaml` 文件（后缀是 `.yml`, `.yaml`, `.json` 或者 `.csv` ）。这些文件可以经由 `'site.data'`访问。如果有一个 `members.yml` 文件在该目录下，你就可以通过 `site.data.members` 获取该文件的内容。
>
> `_site` ：**默认存放**`Jekyll`**转换生成的页面
> >**最好将这个目录放进 `.gitignore` 文件中。 
> 
> `.jekyll-metadata`：
> > 该文件帮助 `Jekyll` 跟踪哪些文件从上次建立站点开始到现在没有被修改，哪些文件需要在下一次站点建立时重新生成。该文件不会被包含在生成的站点中。将它加入到你的 `.gitignore` 文件可能是一个好注意
> 
> `index.html`and other `HTML, Markdown, Textile files`：
> >**如果这些文件中包含** `YAML` **头信息部分，**`Jekyll`**就会自动将它们进行转换**。(其他的如 .html, .markdown, .md, 或者 .textile 等在你的站点根目录下或者不是以上提到的目录中的文件也会被转换.)
> 
> `Other Files/Folders`
> >其他一些未被提及的目录和文件如 `css` 还有 `images` 文件夹， `favicon.ico` 等文件都将被完全拷贝到生成的 `site` 中。


## Configuration
[Jekyll的配置功能](http://jekyllcn.com/docs/configuration/)
    既可以配置在网站根目录下的 _config.yml 文件，也可以作为命令行的标记来配置。

## Blog structure
### Header
`Jekyll`处理的文件需要包含`YAML`头信息，头信息必须在文件的开始部分`,按照`YAML`的格式写在两行`---`之间。例如：
```
---
layout: post
title: Blogging Like a Hacker
---
```
在这两行`---`之间，可以设置预定义的变量（下面这个例子可以作为参考），创建一个自定义的变量。这样在接下来的文件和任意模板中或者在包含这些页面或博客的模板中都可以通过使用 Liquid 标签来访问这些变量。

> ！警告：`UTF-8`编码
> > 如果使用 `UTF-8` 编码，那么在文件中一定不要出现 `BOM` 头字符，尤其在 `Windows` 上使用 `Jekyll` 的时候。
> 
>提示：头信息变量是可选的
> > 如果你想使用 `Liquid` 标签和变量但在头信息中又不需要任何定义，那你就让头信息空着！在头信息为空的情况下，`Jekyll` 仍然能够处理文件。（这对于一些像 `CSS` 和 `RSS` 的文件非常有用）

#### 预定义的全局变量Permalink
在头信息里设置预定义好的全局变量：
|变量名称 |	描述 |
|:-:|:-|
|`layout`|如果设置的话，会指定使用该模板文件。指定模板文件时候不需要文件扩展名。模板文件必须放在 `_layouts` 目录下。
|`permalink`|如果你需要让你发布的博客的 `URL` 地址不同于默认值 `/year/month/day/title.html`，那你就设置这个变量，然后变量值就会作为最终的 URL 地址。|
|`published`|如果你不想在站点生成后展示某篇特定的博文，那么就设置（该博文的）`published = false`。

#### 自定义变量Permalink
在头信息中没有预先定义的任何变量都会在数据转换中通过 Liquid 模板被调用。例如，如果你设置一个 title 变量，然后你就可以在你的模板中使用这个 title 变量来设置页面的标题（title）：
```
<!DOCTYPE HTML>
<html>
  <head>
    <title>{{ page.title }}</title>
  </head>
  <body>
...
```
#### 在文章中预定义的变量
在文章中可以使用这些在头信息变量列表中未包含的变量。
|变量名称 |	描述|
|:-:|:-|
|`date`|这里的日期会覆盖文章名字中的日期。日期的具体格式为`YYYY-MM-DD HH:MM:SS +/-TTTT`；时，分，秒和时区都是可选的。|
|`category` `categories`|除过将博客文章放在某个文件夹下面外，你还可以指定博客的一个或者多个分类属性。这样当你的站点生成后，这些文章就可以根据这些分类来阅读。`categories` 可以通过 `YAML list`，或者以逗号隔开的字符串指定。|
|`tags`|类似分类 `categories`，一篇文章也可以给它增加一个或者多个标签。同样，`tags` 可以通过 `YAML` 列表或者以逗号隔开的字符串指定。| 
>提示: 不要重复
>> 如果你不想重复设置你常用的头信息变量，只需为它们定义默认值，仅在必要的时候（或者从不）覆盖它们即可。这种方式对预定义变量和自定义变量都有效。
