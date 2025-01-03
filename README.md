
# TypechoAutoPublishTools

Typecho文章自动发布工具，使用 Github Actions 自动更新文章到 Typecho

这个项目可以让你用Markdown写博客，push更新到Github后，Github Actions自动将文章更新到Typecho，并将Typecho站的文章索引更新到Github仓库的README.md，供搜索引擎收录。

参考了 [WordPressXMLRPCTools](https://github.com/zhaoolee/WordPressXMLRPCTools/)，基于Github Actions + Python3.10 + PyTypecho + XMLRPC 实现的文章自动检查及发布

![Static Badge](https://img.shields.io/badge/Python-3.10-blue)
![Static Badge](https://img.shields.io/badge/PyTypecho-2.1.0-blue)
![Static Badge](https://img.shields.io/badge/Typecho-1.2.1-blue)
![Static Badge](https://img.shields.io/badge/XMLRPC-green)

## Features

- 自动检查项目内的所有文章，新文章自动发布，旧文章比对MD5自动更新

- 自动更新文章发布链接到项目仓库，增加google收录

## Quick Start

### 本地运行

1. 下载项目，然后安装 Python 3.10、Pip、Pipenv  

```shell
git clone https://github.com/Thinker-Joe/TypechoAutoPublishTools

pip3 install pipenv
```

2. 安装依赖  

```shell
pipenv install
```

3. 本地运行配置  

复制根目录下的 config.txt 为 local_config.txt ，并按说明修改配置里的地址、用户名、密码

```json
{
    "USERNAME": "填写登录后台的用户名",
    "PASSWORD": "填写登录后台的密码",
    "XMLRPC_PHP": "填写xmlrpc地址信息，如 https://blog.yycdev.com/action/xmlrpc"
}
```

4. 检查更新及发布文章

```shell
pipenv run build
```

命令运行成功后即可在Typecho后台即可看到新发布或更新后的文章

### Github Actions运行

1. 配置 Github Secrets

Settings > Security > Secrets and variables > Actions

在该菜单下添加 PASSWORD、USERNAME、XMLRPC_PHP 这三个配置参数，参数值参考项目里的config.txt

![](https://img.yycdev.com/202403041737177.png)

2. 配置完成后，在 _post 文件夹新建文件并提交保存更新到仓库触发 Github Action 自动运行

![](https://img.yycdev.com/202403041742805.png)

3. Action运行成功后，在Typecho后台即可看到新发布或更新后的文章

### 新建文章

在 _post 目录下新建 后缀为 .md 的markdown文件即可

### 文章格式

```yaml
---
title: 标题
tags: 
- 标签1
- 标签2
categories:
- 分类1
- 分类二
---

正文开始...
```

样例参考: https://github.com/Thinker-Joe/TypechoAutoPublishTools/blob/main/_posts/2020-01-18-blog.md

### 固定链接

固定链接参考了 简书 的文章url形式，域名后加 /p/ , 再加英文文件名，只要不改变英文文件名，文章就有固定的链接

> 例子：_posts 目录下新建一个 2020-01-18-blog.md 文件，同步后的文章url为 https://xxx.com/p/2020-01-18-blog/

同时在Typecho后台也要配置好文章的永久链接设置
> 管理后台>设置>永久链接>自定义文章路径  
> 个性化定义：/p/{slug}.html

![](https://img.yycdev.com/202403041751952.png)

## 感谢

- [WordPressXMLRPCTools](https://github.com/zhaoolee/WordPressXMLRPCTools/)

- [PyTypecho](https://github.com/veoco/PyTypecho)

- [Typecho](https://typecho.org/)

---start---
## 目录(2025年01月03日更新)
[思い出すだけで笑う](https://www.misstwo.top/index.php/p/post001/)

[建立个人独立博客有什么好处?](https://www.misstwo.top/index.php/p/2020-01-18-blog/)

---end---