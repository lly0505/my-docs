# [【工具】10分钟快速搭建属于自己的文档网站](https://juejin.cn/post/6937452670202413087)

## 前言
***
很多同学都希望能够拥有自己的一个文档系统，去记录/总结自己所学到的知识。

本文就来介绍一下  [Docsify](https://docsify.js.org/#/) + Github Page 的方式，旨在快速搭建属于自己的文档网站

本文的 Demo 代码可以通过 [Github](https://github.com/) 查看，演示看[这里](http://baidu.com/)
***

## 准备工作
***
全局安装 `docsify-cli` 工具，并创建文档项目目录
```
npm i docsify-cli -g
mkdir my-docs
cd my-docs
```

### 初始化项目
```
docsify init ./docs
```
成功后会生成一个 `docs` 的文件夹，并且里面有三个文件

+ index.html 入口文件。后面我们的配置很多都是在这里配置
+ README.md 会做为主页内容渲染
+ .nojekyll 用于阻止 GitHub Pages 忽略掉下划线开头的文件

### 启动项目
```
docsify serve docs
```
通过运行 `docsify serve` 启动一个本地服务器，可以方便地实时预览效果。默认访问地址 [http://localhost:3000](http://localhost:3000) 。下面的内容时间上是 `README.md` 中的内容









***