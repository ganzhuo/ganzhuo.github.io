#### **简介：**

docsify：一个神奇的文档网站生成器

概述：docsify 可以快速帮你生成文档网站。不同于 GitBook、Hexo 的地方是它不会生成静态的 `.html` 文件，所有转换工作都是在运行时。

特性：

- 无需构建，写完文档直接发布
- 容易使用并且轻量 
- 智能的全文搜索
- 提供多套主题
- 丰富的 API
- 支持 Emoji
- 兼容 IE11
- 支持服务端渲染 SSR 

#### **快速开始：**

1.全局安装 `docsify-cli` 工具：

```markdown
npm i docsify-cli -g
```

2.`init` 初始化项目:

```markdown
docsify init ./docs
```

3.运行 `docsify serve` 启动一个本地服务器:

```markdown
docsify serve docs
```



#### **定制侧边栏：**

1.创建自己的`_sidebar.md`

2.配置 `loadSidebar`

```html
<!-- index.html -->

<script>
  window.$docsify = {
    loadSidebar: true
  }
</script>
```

3.创建 `_sidebar.md` 文件

```markdown
<!-- docs/_sidebar.md -->

* [首页](zh-cn/)
* [指南](zh-cn/guide)
```



#### **自定义导航栏：**

1.配置 `loadNavbar`

```html
<!-- index.html -->

<script>
  window.$docsify = {
    loadNavbar: true
  }
</script>
```

2.创建`_navbar.md`文件

```markdown
<!-- _navbar.md -->

* [En](/)
* [中文](/zh-cn/)
```



#### **开启封面：**

```html
<!-- index.html -->

<script>
  window.$docsify = {
    coverpage: true
  }
</script>
```



#### **取消封面和首页同页面：**

```html
<!-- index.html -->

<script>
  window.$docsify = {
    onlyCover: true
  }
</script>
```



#### **设置生成目录的最大层级:**

```html
<!-- index.html -->

<script>
  window.$docsify = {
    subMaxLevel: 2
  }
</script>
```

