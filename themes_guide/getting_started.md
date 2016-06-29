# 入门指南
这篇文章将帮你了解和运行Ghost主题。

---

如果你想要对现有主题做一些改动，你可能可以在[support.ghost.org](http://support.ghost.org/?s=theme)里找到更有用的帮助文档，因为那些文章包含了最常见的改动，例如如何一步步地添加disqus或者导航栏。

如果你想要从头开始创建你自己的自定义主题，或者使用其他主题作为基础，那么这篇指南正式给你准备的:)

### 配置
你需要做的第一件事情是为Ghost配置一个本地的开发环境。你可以使用任意一种你喜欢的方式安装Ghost（zip，git或者npm），让它跑在你的机器上。Ghost的[README.md](https://github.com/TryGhost/Ghost)和[提供帮助的网站](http://support.ghost.org/installation)有更多关于安装的信息。

最重要的事情是你跑的Ghost需要在开发环境下，而不是在生产环境下（这意味着，使用`npm start`而不是使用`npm start --production`）。因为在开发环境下，你不必保持重启来看你修改的部分。

你也需要一个能较好的支持Handlebars的编辑器。[Brackets](http://brackets.io/)是一个免费的，能较好的支持编辑主题文件的编辑器。另外，IntelliJ，Sublime和很多其他有名的IDS都能很好的原生或者通过插件支持Handlebars。