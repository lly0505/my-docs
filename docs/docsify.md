# [【工具】10分钟快速搭建属于自己的文档网站](https://juejin.cn/post/6937452670202413087)

## 前言
***
很多同学都希望能够拥有自己的一个文档系统，去记录/总结自己所学到的知识。

本文就来介绍一下  [Docsify](https://docsify.js.org/#/) + Github Page 的方式，旨在快速搭建属于自己的文档网站

本文的 Demo 代码可以通过 [Github](https://github.com/) 查看，演示看[这里](https://lly0505.github.io/my-docs)
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

![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/07d8bf3840bf4d9e93eeeadbba3b97f5~tplv-k3u1fbpfcp-zoom-1.image)

## 简单的配置
***
接下来就是配置我们的文档了
### 配置侧边栏
在 index.html 中，新增配置 `loadSidebar: true`
```
window.$docsify = {
  name: '',
  repo: '',
+  loadSidebar: true
}
```
在 docs 中新建一个文件 `_sidebar.md`，写入
```
- JavaScript
  - [闭包](closure.md)
  - [原型](prototype.md)

- CSS
  - [布局](layout.md)
```
同时在 `docs` 中新建 `closure.md` 、`prototype.md`和 `layout.md`三个 Markdown 文件

可以在 `closure.md` 中写入如下，查看效果
```
# 介绍闭包
## 什么是闭包
哈哈哈哈

## 闭包的作用是什么
```
![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8514d447ebfc41049175cdea3d432203~tplv-k3u1fbpfcp-zoom-1.image)

### 自动生成目录
可以根据标题生成目录，这个在文章很长的时候很有用，直接演示配置和效果
```
window.$docsify = {
  name: '',
  repo: '',
  loadSidebar: true,
+ subMaxLevel: 2
}
```
![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4876514f881e4c1cbe61cc5fd036bf2e~tplv-k3u1fbpfcp-zoom-1.image)

## 插件的使用
***
基础的配置已经完成了，当然还有其他更多的功能配置，这里不再细说。`Docsify` 还提供了丰富的插件，接下来我们看看

### 全文搜索
配置非常简单
```
<script>
  window.$docsify = {
    name: '',
    repo: '',
    loadSidebar: true,
    subMaxLevel: 2,
+   search: 'auto'
  }
</script>
<!-- Docsify v4 -->
<script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
+  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
```
查看效果

![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/23eae04c9d2045969242b3c578fdad05~tplv-k3u1fbpfcp-zoom-1.image)

### 图片缩放
`Docsify` 是需要插件才能实现图片缩放的，但其实也很简单，如下

```
    <script>
      window.$docsify = {
        name: '',
        repo: '',
        loadSidebar: true,
        subMaxLevel: 2,
        search: 'auto'
      }
    </script>
    <!-- Docsify v4 -->
    <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
    <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
+   <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/zoom-image.min.js"></script>
```
### 支持 CodePen 插入
随便找到一个 `CodePen`，打开，找到 `Embed`，点击进入

![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/dcf0790bc1014c359f90849605e33106~tplv-k3u1fbpfcp-zoom-1.image?imageslim)

点击 `iframe`,`copy` 里面的代码。粘贴到你的 `markdown` 文件中

![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/208fd9e4d2354286a9c1f5934c8817a9~tplv-k3u1fbpfcp-zoom-1.image?imageslim)

就可以查看 `CodePen` 的了

![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2b4d56e29e484c8ea50dc6554261272d~tplv-k3u1fbpfcp-zoom-1.image?imageslim)

### 更多的插件实现方案
`Docsify` 还提供了 [Gitalk](https://docsify.js.org/#/zh-cn/plugins?id=gitalk) 评论插件等。更多请看[官方文档](https://docsify.js.org/#/zh-cn/plugins)，这里不再赘述。

## 部署
***
你不需要一台服务器（当然也可以），我们直接部署到 `Github Page` 中。先上传我们的代码到 `Github`。这里不再演示这一步，请读者自行完成

找到 `Settings`

![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/73a93a0972934ad0957cb377521ac439~tplv-k3u1fbpfcp-zoom-1.image?imageslim)

找到 `GitHub Pages`，选择 `main` 和 `docs` 文件夹，点击 `save`

![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/10e118a732ff4332914ca16c0ee849eb~tplv-k3u1fbpfcp-zoom-1.image?imageslim)

稍等一会，就会生成我们的文档地址了，可以点击[这里](https://lly0505.github.io/my-docs)查看本文的演示效果

![Image text](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2eb4e062428345a9bfa5a26fd32f5c01~tplv-k3u1fbpfcp-zoom-1.image?imageslim)

## 总结
***
本文从 0 到 1 介绍以 [Docsify](https://docsify.js.org/#/zh-cn/quickstart) + `Github Page` 的方式，快速搭建属于自己的文档系统，并部署到线上。当然文章提到的只是 `Docsify` 的一小部分功能，赶兴趣的可以去官方查看