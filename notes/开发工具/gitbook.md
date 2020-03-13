# <center>gitbook 入门</center>

# 一、运行环境

## nodejs

 	版本号：v8.11.x

​    安装教程：下载node就是，链接https://nodejs.org/en/download/，下载完以后直接安装即可。

​    安装成功后，点击开始-运行-cmd（win+R），打开dos，输入“node --version”检查Node.js版本。如果显示“不是内部或外部命令，也不是可运行的程序”，则需要手动配置环境变量。打开系统环境变量,在系统的path环境变量中配置了node.exe的目录路径。

## npm

 	版本号：5.6.x

​    npm是随同NodeJS一起安装的包管理工具。在dos窗口使用‘npm -v’查看npm的版本。

## gitbook-cli

```
npm install -g gitbook-cli
```

## 开发工具

 GitBook + Typora + Git

# 二、gitbook使用

## 初始化

~~~bash
gitbook init  ---- 项目初始化
~~~

## 目录结构

```
README.md —— 书籍的介绍写在这个文件里
SUMMARY.md —— 书籍的目录结构在这里配置
```

书籍的目录结构如下：

```markdown
# 目录

* [前言](README.md)
* [第一章](Chapter1/README.md)
  * [第1节：衣](Chapter1/衣.md)
  * [第2节：食](Chapter1/食.md)
  * [第3节：住](Chapter1/住.md)
  * [第4节：行](Chapter1/行.md)
* [第二章](Chapter2/README.md)
* [第三章](Chapter3/README.md)
* [第四章](Chapter4/README.md)
```

## 项目运行

```bash
//默认4000端口
gitbook serve
gitbook serve --port 2333
gitbook serve --open
```

## 项目打包

~~~bash
gitbook build [书籍路径] [输出路径]
gitbook build --log=debug
gitbook pdf ./ ./mybook.pdf
gitbook epub ./ ./mybook.epub
gitbook mobi ./ ./mybook.mobi
~~~

## 其他命令

```bash
//输出gitbook的帮助信息
gitbook --help
//生成静态网页并运行服务器
gitbook serve
//生成静态网页
gitbook build
//生成静态网页时指定gitbook的版本，如果本地没有将先下载
gitbook build --gitbook=3.2.3
//列出所有的gitbook版本
gitbook ls
//列出远程可用的gitbook版本
gitbook ls-remote
//更新到gitbook的最新版本
gitbook update
//卸载对应的gitbook版本
gitbook uninstall 3.2.3
//安装依赖
gitbook install
//指定log的级别
gitbook build --log=debug
//输出错误信息
gitbook builid --debug
```

# 三、插件配置

## book.json 配置

book.json文件是gitbook项目的配置文件。

book.json常用配置如下：

```json
{
    "title": "title 设置书本的标题",
    "author": "author 作者的相关信息",
    "description": "description 本书的简单描述",
    "language": "language Gitbook使用的语言 支持 en, ar, bn, cs, de, en, es, fa, fi, fr, he, it, ja, ko, no, pl, pt, ro, ru, sv, uk, vi, zh-hans, zh-tw",
    "gitbook": "3.2.3", // gitbook  版本
    "links": // 侧边栏链接
    {
        "sidebar":
        {
            "Personal Book": "http://www.gtwteam.com"
        }
    },
    "styles":
    { // 页面自定义样式
        "website": "styles/website.css",
        "ebook": "styles/ebook.css",
        "pdf": "styles/pdf.css",
        "mobi": "styles/mobi.css",
        "epub": "styles/epub.css"
    },

    "plugins": [ // 插件
        "-sharing",
        "favicon",
    ],
    "pluginsConfig":
    {
        "sharing":
        {
            "facebook": true,
            "twitter": true,
            "weibo": true,
            "qq": true,
            "all": [
                "douban",
                "google",
                "instapaper",
                "linkedin",
                "twitter",
                "messenger",
                "qzone",
                "viber",
                "whatsapp"
            ]
        },
        "favicon":
        {
            "shortcut": "./static/icon/favicon.ico",
            "bookmark": "./static/icon/favicon.ico",
            "appleTouch": "./static/icon/favicon.ico",
            "appleTouchMore":
            {
                "120x120": "./static/icon/favicon.ico",
                "180x180": "./static/icon/favicon.ico"
            }
        }
    }
}
```

## 常用插件

* #### back-to-top-button（返回顶部）

* #### code（代码添加行号&复制按钮）

```json
{
    "pluginsConfig": {
      "code": {
        "copyButtons": false
      }
    }
}
```

* #### search-pro（高级搜索，支持中文）

* #### github（在右上角添加github图标）

```json
{
    "pluginsConfig": {
        "github": {
            "url": "https://github.com/lijiam"
        }
    }
}
```

* #### splitter（侧边栏宽度可调节）

* #### tbfed-pagefooter（页面添加页脚，简单的）

```json
{
    "pluginsConfig": {
        "tbfed-pagefooter": {
            "copyright":"Copyright &copy lijiam 2019",
            "modify_label": "本书发布时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        }
    }
}
```

* #### page-copyright（页面页脚版权，复杂的）

```json
{
    "pluginsConfig": {
        "page-copyright": {
          "description": "modified at",
          "signature": "你的签名",
          "wisdom": "Designer, Frontend Developer & overall web enthusiast",
          "format": "YYYY-MM-dd hh:mm:ss",
          "copyright": "Copyright &#169; 你的名字",
          "timeColor": "#666",
          "copyrightColor": "#666",
          "utcOffset": "8",
          "style": "normal",
          "noPowered": false,
        }
    }
}
```

* #### donate（打赏插件）

```
{
    "pluginsConfig": {
        "donate": {
            "wechat": "微信收款的二维码URL",
            "alipay": "支付宝收款的二维码URL",
            "title": "",
            "button": "赏",
            "alipayText": "支付宝打赏",
            "wechatText": "微信打赏"
        }
    }
}
```

* #### sharing-plus（分享当前页面）

```json
{
    "plugins": ["-sharing", "sharing-plus"],
    "pluginsConfig": {
        "sharing": {
            "facebook": true,
            "twitter": true,
            "weibo": true,
            "qq": true,
        "all": [
            "douban", "google", "instapaper", "linkedin", "twitter", "messenger", "qzone", "viber", "whatsapp"
           ]
       }
    }
}
```

* #### custom-favicon（修改标题栏图标）

```json
{
    "pluginsConfig": {
        "favicon": "images/favicon.ico"
    }
}
```

* #### prism（代码高亮）

~~~json
{
    "plugins": ["prism", "-highlight"],
    "pluginsConfig": {
        "prism": {
            "css": [
                "prismjs/themes/prism-okaidia.css"
            ],
            "lang": {
                "flow": "typescript"
            }
        }
    }
}
~~~

* #### todo（复选框）

~~~
* [ ] 这是一个未选中的
* [x] 这是一个已选中的
~~~

* #### pageview-count（阅读量计数）

```javascript
// 未调整前
var fontSize = bookHeader.find('.dropdown');
// 调整后
var fontSize = bookHeader.find('.font-settings');
```

* #### auto-scroll-table（表格滚动条）

* #### image-captions（显示图片名称）

~~~json
{
    "pluginsConfig": {
        "image-captions": {
          "caption": "Image _PAGE_LEVEL_._PAGE_IMAGE_NUMBER_ - _CAPTION_"
      }
    }
}
~~~

* #### styles-sass（使用sass替换css）

~~~json
{
    "plugins": ["styles-sass"],
    "styles": {
        "pdf": "styles/pdf.sass"
    }
}
~~~

* #### styles-less（使用less替换css）

~~~json
{
    "plugins": ["styles-less"],
    "styles": {
        "pdf": "styles/pdf.less"
    }
}
~~~

* #### toggle-chapters（目录折叠）

* #### multipart（分章节展示）

~~~markdown
# GitBook

## 第一章
* [第一节](part1/1/README.md)
    * [1.1](part1/1.1/README.md)
* [第二节](part1/2/README.md)
* [第三节](part1/3/README.md)

## 第二章
* [第一节](part2/1/README.md)

## 第三章
~~~

~~~json
{
    "pluginsConfig": {
        "theme-default": {
            "showLevel": true
        }
    }
}
~~~

* #### favicon-absolute （设置网站图标）

```json
{
    "plugins": ["favicon-absolute"],
    "pluginsConfig": {
        "favicon-absolute":{
            "favicon": "/favicon.ico",
            "appleTouchIconPrecomposed152": "/apple-touch-icon-precomposed-152.png"
        }
    }
}
```

```json
{
    "title": "favicon-absolute 插件官方文档",
    "author": "snowdreams1006",
    "description": "gitbook-plugin-favicon-absolute 插件官方文档",
    "plugins": [
        "favicon-absolute"
    ],
    "pluginsConfig": {
        "favicon-absolute":{
            "favicon": "/favicon.ico",
            "bookmark": "/bookmark.ico",
            "appleTouchIcon152": "/apple-touch-icon-152.png",
            "appleTouchIconPrecomposed152": "/apple-touch-icon-precomposed-152.png",
            "appleTouchIconMore": {
                "120x120": "/apple-touch-icon-120.png",
                "180x180": "/apple-touch-icon-180.png"
            },
            "appleTouchIconPrecomposedMore": {
                "120x120": "/apple-touch-icon-precomposed-120.png",
                "180x180": "/apple-touch-icon-precomposed-180.png"
            }
        }
    }
}
```