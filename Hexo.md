# 安装

## 安装前提

- [Node.js](https://nodejs.org/)
- [Git](https://git-scm.com/)
  - Linux (Ubuntu, Debian)：`sudo apt-get install git-core`
  - Linux (Fedora, Red Hat, CentOS)：`sudo yum install git-core`

## 安装Hexo

```shell
npm install -g hexo-cli    # 安装Hexo
npm install hexo           # 手选局部安装Hexo
```

# 建站

```shell
hexo init <folder>         # 
cd <folder>
npm install
```

- _config.yml：网站配置信息
- package.json：应用程序的信息
- scaffolds：模板文件夹
- source：存放用户资源的地方
- themes：主题文件夹

# 配置

| 参数          | 描述                                                         |
| :------------ | :----------------------------------------------------------- |
| `title`       | 网站标题                                                     |
| `subtitle`    | 网站副标题                                                   |
| `description` | 网站描述                                                     |
| `keywords`    | 网站的关键词。支持多个关键词。                               |
| `author`      | 您的名字                                                     |
| `language`    | 网站使用的语言。常见的有 `zh-Hans`和 `zh-CN`。               |
| `timezone`    | 网站时区。Hexo 默认使用您电脑的时区。一般的，对于中国大陆地区可以使用 `Asia/Shanghai`。 |

## 网址

| 参数                         | 描述                                                         | 默认值                      |
| :--------------------------- | :----------------------------------------------------------- | :-------------------------- |
| `url`                        | 网址, 必须以 `http://` 或 `https://` 开头                    |                             |
| `root`                       | 网站根目录                                                   | `url's pathname`            |
| `permalink`                  | 文章的永久链接格式                                           | `:year/:month/:day/:title/` |
| `permalink_defaults`         | 永久链接中各部分的默认值                                     |                             |
| `pretty_urls`                | 改写 `permalink`的值来美化 URL                               |                             |
| `pretty_urls.trailing_index` | 是否在永久链接中保留尾部的 `index.html`，设置为 `false` 时去除 | `true`                      |
| `pretty_urls.trailing_html`  | 是否在永久链接中保留尾部的 `.html`, 设置为 `false` 时去除 (*对尾部的 `index.html`无效*) | `true`                      |

如果您的网站存放在子目录中，例如 `http://example.com/blog`，则请将您的 `url` 设为 `http://example.com/blog` 并把 `root` 设为 `/blog/`。

```shell
# 比如，一个页面的永久链接是 http://example.com/foo/bar/index.html
pretty_urls:
  trailing_index: false
# 此时页面的永久链接会变为 http://example.com/foo/bar/
```

## 目录

| 参数           | 描述                                                         | 默认值           |
| :------------- | :----------------------------------------------------------- | :--------------- |
| `source_dir`   | 资源文件夹，这个文件夹用来存放内容。                         | `source`         |
| `public_dir`   | 公共文件夹，这个文件夹用于存放生成的站点文件。               | `public`         |
| `tag_dir`      | 标签文件夹                                                   | `tags`           |
| `archive_dir`  | 归档文件夹                                                   | `archives`       |
| `category_dir` | 分类文件夹                                                   | `categories`     |
| `code_dir`     | Include code 文件夹，`source_dir` 下的子目录                 | `downloads/code` |
| `i18n_dir`     | 国际化（i18n）文件夹                                         | `:lang`          |
| `skip_render`  | 跳过指定文件的渲染。匹配到的文件将会被不做改动地复制到 `public` 目录中。您可使用 glob 表达式来匹配路径。 |                  |

如果您刚刚开始接触 Hexo，通常没有必要修改这一部分的值。

```shell
skip_render: "mypage/**/*"
# 将会直接将 `source/mypage/index.html` 和 `source/mypage/code.js` 不做改动地输出到 'public' 目录
# 你也可以用这种方法来跳过对指定文章文件的渲染
skip_render: "_posts/test-post.md"
# 这将会忽略对 'test-post.md' 的渲染
```

## 文章

| 参数                    | 描述                                              | 默认值    |
| :---------------------- | :------------------------------------------------ | :-------- |
| `new_post_name`         | 新文章的文件名称                                  | :title.md |
| `default_layout`        | 预设布局                                          | post      |
| `auto_spacing`          | 在中文和英文之间加入空格                          | false     |
| `titlecase`             | 把标题转换为 title case                           | false     |
| `external_link`         | 在新标签中打开链接                                | true      |
| `external_link.enable`  | 在新标签中打开链接                                | `true`    |
| `external_link.field`   | 对整个网站（`site`）生效或仅对文章（`post`）生效  | `site`    |
| `external_link.exclude` | 需要排除的域名。主域名和子域名如 `www` 需分别配置 | `[]`      |
| `filename_case`         | 把文件名称转换为 (1) 小写或 (2) 大写              | 0         |
| `render_drafts`         | 显示草稿                                          | false     |
| `post_asset_folder`     | 启动 Asset 文件夹                                 | false     |
| `relative_link`         | 把链接改为与根目录的相对位址                      | false     |
| `future`                | 显示未来的文章                                    | true      |
| `highlight`             | 代码块的设置                                      |           |
| `prismjs`               | 代码块的设置                                      |           |

## 分类 & 标签

| 参数               | 描述     | 默认值          |
| :----------------- | :------- | :-------------- |
| `default_category` | 默认分类 | `uncategorized` |
| `category_map`     | 分类别名 |                 |
| `tag_map`          | 标签别名 |                 |

## 日期 / 时间格式

| 参数             | 描述                                                    | 默认值       |
| :--------------- | :------------------------------------------------------ | :----------- |
| `date_format`    | 日期格式                                                | `YYYY-MM-DD` |
| `time_format`    | 时间格式                                                | `HH:mm:ss`   |
| `updated_option` | 当 Front Matter 中没有指定 `updated`时 `updated` 的取值 | `mtime`      |

`updated_option` 控制了当 Front Matter 中没有指定 `updated` 时，`updated` 如何取值：

 - `mtime`: 使用文件的最后修改时间。这是从 Hexo 3.0.0 开始的默认行为。
 - `date`: 使用 `date` 作为 `updated` 的值。可被用于 Git 工作流之中，因为使用 Git 管理站点时，文件的最后修改日期常常会发生改变
 - `empty`: 直接删除 `updated`。使用这一选项可能会导致大部分主题和插件无法正常工作。


## 分页

| 参数             | 描述                                | 默认值 |
| :--------------- | :---------------------------------- | :----- |
| `per_page`       | 每页显示的文章量 (0 = 关闭分页功能) | `10`   |
| `pagination_dir` | 分页目录                            | `page` |

## 扩展

| 参数             | 描述                                                         |
| :--------------- | :----------------------------------------------------------- |
| `theme`          | 当前主题名称。值为`false`时禁用主题                          |
| `theme_config`   | 主题的配置文件。在这里放置的配置会覆盖主题目录下的 `_config.yml` 中的配置 |
| `deploy`         | 部署部分的设置                                               |
| `meta_generator` | Meta generator标签。 值为 `false` 时 Hexo 不会在头部插入该标签 |

### 包括或不包括目录和文件

在 Hexo 配置文件中，通过设置 include/exclude 可以让 Hexo 进行处理或忽略某些目录和文件夹。你可以使用 glob 表达式对目录和文件进行匹配。

`include` 和 `exclude` 选项只会应用到 `source/` ，而 `ignore` 选项会应用到所有文件夹。

| 参数      | 描述                                                         |
| :-------- | :----------------------------------------------------------- |
| `include` | Hexo 默认会不包括 `source/` 下的文件和文件夹（包括名称以下划线和 `.` 开头的文件和文件夹，Hexo 的 `_posts` 和 `_data` 等目录除外）。通过设置此字段将使 Hexo 处理他们并将它们复制到 `source` 目录下。 |
| `exclude` | Hexo 不包括 `source/` 下的这些文件和目录                     |
| `ignore`  | Hexo 会忽略整个 Hexo 项目下的这些文件夹或文件                |

```shell
# 处理或不处理目录或文件
include:
  - ".nojekyll"
  - "css/_typing.css"    # 处理 'source/css/_typing.css'
  - "_css/*"             # 处理 'source/_css/' 中的任何文件，但不包括子目录及其其中的文件。
  - "_css/**/*"          # 处理 'source/_css/' 中的任何文件和子目录下的任何文件

exclude:
  - "js/test.js"         # 不处理 'source/js/test.js'
  - "js/*"               # 不处理 'source/js/' 中的文件、但包括子目录下的所有目录和文件
  - "js/**/*"            # 不处理 'source/js/' 中的文件和子目录下的任何文件
  - "js/test*"           # 不处理 'source/js/' 目录下的所有文件名以 'test' 开头的文件，但包括其它文件和子目录下的单文件
  - "js/**/test*"        # 不处理 'source/js/' 及其子目录中任何以 'test' 开头的文件
# 不要用 exclude 来忽略 'source/_posts/' 中的文件。你应该使用 'skip_render'，或者在要忽略的文件的文件名之前加一个下划线 '_'
# 在这里配置一个 - "_posts/hello-world.md" 是没有用的。

ignore:
  - "**/foo"             # 忽略任何一个名叫 'foo' 的文件夹
  - "**/themes/*/foo"    # 只忽略 'themes/' 下的 'foo' 文件夹
  - "**/themes/**/foo"   # 对 'themes/' 目录下的每个文件夹中忽略名叫 'foo' 的子文件夹
```

列表中的每一项都必须用单引号或双引号包裹起来。

`include` 和 `exclude` 并不适用于 `themes/` 目录下的文件。如果需要忽略 `themes/` 目录下的部分文件或文件夹，可以使用 `ignore` 或在文件名之前添加下划线 `_`。

### 使用代替配置文件

可以在 hexo-cli 中使用 `--config` 参数来指定自定义配置文件的路径。你可以使用一个 YAML 或 JSON 文件的路径，也可以使用逗号分隔（无空格）的多个 YAML 或 JSON 文件的路径。

```shell
# 用 'custom.yml' 代替 '_config.yml'
$ hexo server --config custom.yml

# 使用 'custom.yml' 和 'custom2.json'，优先使用 'custom3.yml'，然后是 'custom2.json'
$ hexo generate --config custom.yml,custom2.json,custom3.yml
```

当你指定了多个配置文件以后，Hexo 会按顺序将这部分配置文件合并成一个 `_multiconfig.yml`。如果遇到重复的配置，排在后面的文件的配置会覆盖排在前面的文件的配置。这个原则适用于任意数量、任意深度的 YAML 和 JSON 文件。

```shell
# 例：使用 `--options` 指定了两个自定义配置文件：
$ hexo generate --config custom.yml,custom2.json
```

如果 `custom.yml` 中指定了 `foo: bar`，在 custom2.json 中指定了 `"foo": "dinosaur"`，那么在 `_multiconfig.yml` 中你会得到 `foo: dinosaur`。

### 使用代替主题配置文件

通常情况下，Hexo 主题是一个独立的项目，并拥有一个独立的 `_config.yml` 配置文件。

除了自行维护独立的主题配置文件，你也可以在其它地方对主题进行配置。

**配置文件中的 `theme_config`**

```shell
# _config.yml
theme: "my-theme"
theme_config:
  bio: "My awesome bio"
  foo:
    bar: 'a'
# themes/my-theme/_config.yml
bio: "Some generic bio"
logo: "a-cool-image.png"
  foo:
    baz: 'b'
```

最终主题配置的输出是：

```shell
{
  bio: "My awesome bio",
  logo: "a-cool-image.png",
  foo: {
    bar: "a",
    baz: "b"
  }
}
```

**独立的 `_config.[theme].yml` 文件**

独立的主题配置文件应放置于站点根目录下，支持 `yml` 或 `json` 格式。需要配置站点 `_config.yml` 文件中的 `theme` 以供 Hexo 寻找 `_config.[theme].yml` 文件。

```shell
# _config.yml
theme: "my-theme"
# _config.my-theme.yml
bio: "My awesome bio"
foo:
  bar: 'a'
# themes/my-theme/_config.yml
bio: "Some generic bio"
logo: "a-cool-image.png"
  foo:
    baz: 'b'
```

最终主题配置的输出是：

```shell
{
  bio: "My awesome bio",
  logo: "a-cool-image.png",
  foo: {
    bar: "a",
    baz: "b"
  }
}
```

Hexo 在合并主题配置时，Hexo 配置文件中的 `theme_config` 的优先级最高，其次是 `_config.[theme].yml` 文件，最后是位于主题目录下的 `_config.yml` 文件。

# 指令

## init

```shell
$ hexo init [folder]           # 新建一个网站
```

如果没有设置 `folder` ，Hexo 默认在目前的文件夹建立网站。

## new

```shell
$ hexo new [layout] <title>    # 新建一篇文章
```

`layout`缺省使用 config.yml中的 `default_layout` 参数。如果标题包含空格的话，请使用引号括起来。

| 参数              | 描述                                          |
| :---------------- | :-------------------------------------------- |
| `-p`, `--path`    | 自定义新文章的路径                            |
| `-r`, `--replace` | 如果存在同名文章，将其替换                    |
| `-s`, `--slug`    | 文章的 Slug，作为新文章的文件名和发布后的 URL |

默认情况下，Hexo 会使用文章的标题来决定文章文件的路径。对于独立页面来说，Hexo 会创建一个以标题为名字的目录，并在目录中放置一个 `index.md` 文件。你可以使用 `--path` 参数来覆盖上述行为、自行决定文件的目录：

```shell
hexo new page --path about/me "About me"
# 以上命令会创建一个source/about/me.md文件，同时Front Matter中的title为"About me"
```

**注意！title 是必须指定的！如果你这么做并不能达到你的目的：**

```shell
hexo new page --path about/me
# 此时Hexo会创建source/_posts/about/me.md，同时me.md的Front Matter中的title为"page"。
# 这是因为在上述命令中，hexo-cli将page视为指定文章的标题、并采用默认的layout。
```

## generate

```shell
$ hexo generate       # 生成静态文件
$ hexo g              # 命令简写
```

| 选项                  | 描述                                                         |
| :-------------------- | :----------------------------------------------------------- |
| `-d`, `--deploy`      | 文件生成后立即部署网站                                       |
| `-w`, `--watch`       | 监视文件变动                                                 |
| `-b`, `--bail`        | 生成过程中如果发生任何未处理的异常则抛出异常                 |
| `-f`, `--force`       | 强制重新生成文件 Hexo 引入了差分机制，如果 `public` 目录存在，那么 `hexo g` 只会重新生成改动的文件。 使用该参数的效果接近 `hexo clean && hexo generate` |
| `-c`, `--concurrency` | 最大同时生成文件的数量，默认无限制                           |

## publish

```shell
$ hexo publish [layout] <filename>    # 发表草稿
```

## server

```shell
$ hexo server                         # 启动服务器。默认情况下，访问网址为：http://localhost:4000/。
```

| 选项             | 描述                           |
| :--------------- | :----------------------------- |
| `-p`, `--port`   | 重设端口                       |
| `-s`, `--static` | 只使用静态文件                 |
| `-l`, `--log`    | 启动日记记录，使用覆盖记录格式 |

## deploy

```shell
$ hexo deploy                         # 部署网站
$ hexo d                              # 命令简写
```

| 参数               | 描述                     |
| :----------------- | :----------------------- |
| `-g`, `--generate` | 部署之前预先生成静态文件 |

## render

```shell
$ hexo render <file1> [file2] ...     # 渲染文件
```

| 参数             | 描述         |
| :--------------- | :----------- |
| `-o`, `--output` | 设置输出路径 |

## clean

```shell
$ hexo clean                          # 清除缓存文件(db.json)和已生成的静态文件(public)
```

## 其它

```shell
$ hexo migrate <type>                 # 从其他博客系统迁移内容
$ hexo list <type>                    # 列出网站资料
$ hexo version                        # 显示Hexo版本
```

## 选项

```shell
$ hexo --safe                         # 安全模式
# 在安全模式下，不会载入插件和脚本。当您在安装新插件遭遇问题时，可以尝试以安全模式重新执行。

$ hexo --debug                        # 调试模式
# 在终端中显示调试信息并记录到debug.log。当您碰到问题时，可以尝试用调试模式重新执行一次，并提交调试信息到GitHub

$ hexo --silent                       # 简洁模式，隐藏终端信息
$ hexo --draft                        # 显示source/_drafts文件夹中的草稿文章
$ hexo --cwd /path/to/cwd             # 自定义CWD，自定义当前工作目录（Current working directory）的路径
```

# [Hexo官网](https://hexo.io/zh-cn/docs/)

