# 入门指南
这篇文章将帮你了解和运行Ghost主题。

---

如果你想要对现有主题做一些改动，你可能可以在[support.ghost.org](http://support.ghost.org/?s=theme)里找到更有用的帮助文档，因为那些文章包含了最常见的改动，例如如何一步步地添加disqus或者导航栏。

如果你想要从头开始创建你自己的自定义主题，或者使用其他主题作为基础，那么这篇指南正式给你准备的:)

### 配置
你需要做的第一件事情是为Ghost配置一个本地的开发环境。你可以使用任意一种你喜欢的方式安装Ghost（zip，git或者npm），让它跑在你的机器上。Ghost的[README.md](https://github.com/TryGhost/Ghost)和[提供帮助的网站](http://support.ghost.org/installation)有更多关于安装的信息。

最重要的事情是你跑的Ghost需要在开发环境下，而不是在生产环境下（这意味着，使用`npm start`而不是使用`npm start --production`）。因为在开发环境下，你不必保持重启来看你修改的部分。

你也需要一个能较好的支持Handlebars的编辑器。[Brackets](http://brackets.io/)是一个免费的，能较好的支持编辑主题文件的编辑器。另外，IntelliJ，Sublime和很多其他有名的IDS都能很好的原生或者通过插件支持Handlebars。

### 创建你自己的主题
一旦你已经完成了你开发环境的配置，并且在开发模式下运行，那么是时候决定你是否想要创建一个从头开始的新主题，或者是否想要使用类似[Casper](https://github.com/TryGhost/Casper)的其他主题作为基础模板。你可能更喜欢首先使用HTML&CSS代码创建你新的设计，然后将它们转换入一个正在运行的主题中。

无论你选择哪种方法，你需要确认在`/content/themes`目录下用适当的名字创建一个文件夹，并包含你主题。最起码，这个目录必须包含一个叫`index.hbs`的文件，一个叫`post.hbs`的文件和一个叫`package.json`的包含了主题名称和版本数的文件。查看[结构](http://themes.ghost.org/v0.8.0/docs/structure)章节来获取更进一步的关于推荐和必备部分的主题结构详情。

如果你已经在指定地方创建了主题目录，你需要重启Ghost。Ghost不会自动发现新的文件，但是它会发现它已经知道的的文件改变的部分（假设你在开发模式下）。前往`/ghost/settings/`，从下拉框中选择你的新主题，然后保存新的设置来激活你的主题。

你可以开始修改你的主题了。记住，如果你添加了新的`.hbs`文件，需要重启Ghost。除此之外，你只需要刷新页面就能看到你修改的部分了。

#### 展示文章
你的主题必须至少要有一个`index.hbs`和一个`post.hbs`模板。`index.hbs`是用来展示主要的文章列表，`post.hbs`是用来展示每个单独的文章。你可以添加更多的模板文件来提供更多的结构和你博客不同部分的样式，或者Ghost通常会使用`index.hbs`来展示列表，用`post.hbs`来展示一系列的文章。

想知道更多关于如何展示你的文章的细节，可以查看[文章文档](http://themes.ghost.org/docs/post)。

#### 文章列表
`index.hbs`能够活的文章的集合，可以使用foreach命令进行展示，例如
	
	{{#foreach posts}}
	// here we are in the post scope
	//whatever you put here gets run for each post
	{{/foreach}}
	
[{{#foreach}}](http://themes.ghost.org/v0.8.0/docs/foreach)命令行有多重选择来帮助你展示你的文章，而且在foreach的循环中可以用来展示详情，具体可查看[文章文档](http://themes.ghost.org/docs/post)。

当展示文章的列表时，你可能也需要使用[{{pagination}}](http://themes.ghost.org/v0.8.0/docs/pagination)命令行，这样你可以在多个文章页面之间跳转导航。

