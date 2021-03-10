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
***