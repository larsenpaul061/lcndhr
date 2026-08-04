乐富官网下载【Q-——333307——】乐富官网下载【 辋芷《888yx●vip》 】
乐富官网下载【Q-——333307——】乐富官网下载【 辋芷《888yx●vip》 】

 从零搭建个人博客：GitHub Pages + Hexo 完整教程（2025版）

你是不是也想过拥有一个属于自己的博客？不用买服务器、不用备案，甚至完全免费——没错，我说的就是 GitHub Pages + Hexo 这套方案。今天这篇教程，我会带你从零开始，一步步搭建出属于你的技术博客。

 为什么选择 Hexo + GitHub Pages？

先聊点实际的。GitHub Pages 是 GitHub 提供的免费静态托管服务，支持自定义域名和 HTTPS。而 Hexo 是目前最流行的静态博客框架之一，基于 Node.js，速度极快，主题丰富。

这套组合的优势非常明显：
- 零成本：域名和托管全部免费
- 纯静态：加载速度快，SEO 友好，百度收录无障碍
- Markdown 写作：专注内容，无需关心样式
- 版本管理：所有文章都在 GitHub 上，不怕丢失

 搭建步骤：从零到上线

 第一步：环境准备

你需要准备三样东西：
1. Node.js（建议 v18+）— 去官网下载安装即可
2. Git — 用于代码版本管理
3. GitHub 账号 — 没有的话先注册一个

安装完成后，打开终端验证一下：

```bash
node -v && git --version
```

 第二步：安装 Hexo 并初始化项目

```bash
npm install -g hexo-cli
hexo init my-blog && cd my-blog
npm install
hexo server
```

看到终端输出 `Hexo is running at http://localhost:4000`，就说明本地博客已经跑起来了。访问这个地址，你会看到一个默认主题的博客——这是你的起点。

 第三步：部署到 GitHub Pages

先在 GitHub 上新建一个仓库，名字必须是：`你的用户名.github.io`。然后回到项目目录：

```bash
npm install hexo-deployer-git --save
```

修改根目录下的 `_config.yml` 文件，找到 `deploy` 字段，填入你的仓库地址：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

最后执行：

```bash
hexo clean && hexo generate && hexo deploy
```

等待几十秒，访问 `https://你的用户名.github.io`，你的博客就正式上线了！

 如何让百度更快收录你的博客？

很多朋友搭建完博客后，发现 Google 很快收录了，但百度迟迟没有动静。这里分享几个实测有效的优化技巧：

1. 主动提交 sitemap：在百度搜索资源平台提交你的站点，并提交 `sitemap.xml` 文件
2. 配置 robots.txt：确保没有屏蔽百度爬虫
3. 内链优化：文章之间互相推荐，增加站内链接密度
4. 持续输出原创内容：百度对原创内容的收录速度比其他平台更快

 下一步：个性化你的博客

到这里，你的博客已经能正常访问了。接下来你可以：
- 更换一个你喜欢的 Hexo 主题（推荐 NexT、Fluid、Butterfly）
- 配置评论系统（如 Giscus、Waline）
- 绑定自定义域名（购买域名 + CNAME 解析）
- 添加文章搜索、访客统计等功能

 写在最后

搭建博客只是第一步，真正有价值的是你开始持续写作。我在搭建过程中踩过不少坑，比如部署失败、主题配置报错、图片路径问题等等。如果你在搭建过程中遇到任何问题，欢迎在评论区留言——我会尽力帮你排查。

你的第一个博客主题准备写点什么？技术笔记、学习心得还是生活随笔？期待在评论区看到你的想法。如果这篇文章对你有帮助，顺手点个赞，让更多想要拥有自己博客的朋友看到它吧！

相关推荐：

https://github.com/leebradley6/ubrqlg/blob/main/2026%E5%AE%98%E7%BD%91%E6%8C%87%E5%8D%97%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%B9%B3%E5%8F%B0%E4%B8%BB%E7%AE%A1_%E7%88%AC%E8%B4%A8%E6%A6%B7%E6%82%94%E9%B2%9CVOBQE.md

<img src="https://i.postimg.cc/XJx6BJpR/lefu-00011.png" />

相关推荐：

https://github.com/leebradley6/ubrqlg/commit/eef53512194c7545e4892c5c8ca2d518ee33b5b8

<img src="https://i.postimg.cc/50pWQ0XN/lefu-00012.png" />
相关推荐：

https://github.com/larsenpaul061/lcndhr/blob/main/2026%E5%AE%98%E7%BD%91%E8%AE%BF%E8%B0%88%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%B9%B3%E5%8F%B0%E5%AE%A2%E6%9C%8D_%E6%85%B7%E7%9B%85%E9%85%B6%E5%AB%A1%E6%82%A3BVJRM.md

<img src="https://i.postimg.cc/xTBDzB1n/lefu-00020.png" />
相关推荐：

https://github.com/larsenpaul061/lcndhr/commit/7363d6afbae6ace18736e5390df5892e23729a83

<img src="https://i.postimg.cc/9McjfTF9/lefu-00009.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
