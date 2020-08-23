# 介绍

ElasticSearch，简称ES， 是一个基于Lucene的分布式全文搜索服务器，和SQL Server的全文索引（Fulltext Index）有点类似，都是基于分词和分段的全文搜索引擎，具有分词，同义词，词干查询的功能，但是ES天生具有分布式和实时的属性。

# 安装

参考链接：https://www.cnblogs.com/gangle/p/9328257.html

## ElasticSearch 安装

1，从官方下载中心 [ElasticSearch Download](https://www.elastic.co/downloads/elasticsearch) 下载ElasticSearch安装包，当前最新版本是6.3.1

2，将zip文件解压到D盘，进入 **D:\elasticsearch-6.3.1\bin** 目录，双击执行 **elasticsearch.bat，该**脚本文件执行 ElasticSearch 启动程序

3，打开浏览器，输入 **http://localhost:9200** ，显式以下画面，说明ES安装成功。



## **安装head插件**

为了便于管理ES，可使用head插件，这是最初级的管理工具，在浏览器中显示ES集群，索引等信息，十分简便好用。 

1, 首先要安装Ｎodejs，下载地址：https://nodejs.org/en/

2, 解压  [elasticsearch-head-master](https://codeload.github.com/mobz/elasticsearch-head/zip/master) 到 **D:\elasticsearch-6.3.1****\elasticsearch-head-master**, 

3, 配置 elasticsearch-6.3.1\config\**elasticsearch.yml**

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
# 设成0.0.0.0让任何人都可以访问，线上服务不要这样设置。
#
network.host: 0.0.0.0
http.port: 9200
# 解决elasticsearch-head 集群健康值: 未连接问题
http.cors.enabled: true
http.cors.allow-origin: "*"
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

4, 在elasticsearch-head-master目录下执行 **npm install -g grunt-cli**

grunt 是基于Node.js的项目构建工具，可以进行打包压缩、测试、执行等等的工作，head插件就是通过grunt启动。

5, 在elasticsearch-head-master目录下执行**npm install** 安装依赖

6, 修改elasticsearch-head-master配置。

修改服务器监听地址:**Gruntfile.js** 

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
        connect: {
            server: {
                options: {
                    port: 9100,
                    base: '.',
                    keepalive: true,
                    hostname: '*'
                }
            }
        }
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

7, 启动运行head服务, 执行 **grunt server** 命令。

8, 访问head管理页面，地址:http://localhost:9100/ 