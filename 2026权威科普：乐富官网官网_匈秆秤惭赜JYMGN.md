乐富官网官网【Q-——333307——】乐富官网官网【 辋芷《888yx●vip》 】
乐富官网官网【Q-——333307——】乐富官网官网【 辋芷《888yx●vip》 】

 从零搭建个人博客：GitHub Pages + Hexo 完整教程（2025最新版）

还在羡慕别人拥有独立的技术博客？其实利用 GitHub Pages 和 Hexo，你可以在半小时内免费搭建一个高颜值、支持自定义域名的个人站点。本文面向 零基础开发者，提供最全的部署指南，建议收藏后按步骤操作。

 为什么要用 GitHub Pages 写博客？

- 完全免费：无需购买服务器和数据库，静态托管由 GitHub 提供。
- 支持 HTTPS：自动配置 SSL 证书，安全且对搜索引擎友好。
- 版本管理：所有文章都是 Markdown 文件，天然适配 Git 工作流。
- SEO 友好：静态页面加载速度快，利于百度、Google 收录。

 第一步：环境准备

在开始之前，请确保你的电脑已经安装：
1. Node.js（建议 v18 以上）
2. Git（用于代码提交）
3. GitHub 账号（如果没有，先注册，注意用户名就是你的博客域名前缀）

 第二步：安装 Hexo 并初始化项目

打开终端（Mac 用户用 Terminal，Windows 用户用 PowerShell），执行以下命令：

```bash
npm install hexo-cli -g
hexo init my-blog
cd my-blog
npm install
```

完成上述操作后，你已经拥有了一个本地生成的博客骨架。输入 `hexo s` 启动本地服务，浏览器访问 `http://localhost:4000` 即可预览默认主题。

 第三步：关联 GitHub 仓库

1. 在 GitHub 上新建一个仓库，命名为 `你的用户名.github.io`（注意是 `.io` 后缀）。
2. 修改博客根目录下的 `_config.yml` 文件，在 `deploy` 部分填入以下内容：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

然后运行：
```bash
npm install hexo-deployer-git --save
hexo d
```

等待命令执行完毕，浏览器访问 `https://你的用户名.github.io` ，你就能看到自己的博客正式上线了！

 第四步：撰写第一篇技术博文

使用组合命令快速创建新

```bash
hexo new post "markdown-写作指南"
```

在 `source/_posts/` 目录下会生成 `.md` 文件，你可以用常见的 Markdown 语法编写内容。请务必在文章头部加入 `tags` 和 `categories` 字段，这有助于 SEO 收录。

 第五步：优化关键词与收录技巧

为了让文章在百度等搜索引擎获得更好排名，在写作时注意以下要点：
1. 标题包含核心关键词，标题长度控制在 10-30 个汉字以内。
2. 正文每 300 字插入一个小标题，让爬虫更容易抓取页面结构。
3. 内链与外链结合：在文章内部合理引用自己的历史文章，并在文末推荐相关阅读。

 互动与维护

为了提升博客活跃度，建议在文末增加 评论区，可使用 Giscus 或 Valine 等开源组件。由于 Hexo 是静态站点，评论功能需要绑定 GitHub Discussions 或 LeanCloud。

最后，定期使用 `hexo clean && hexo g && hexo d` 三连发布新内容，保持站点新鲜度。如果在搭建过程中遇到任何问题，欢迎在评论区留言，我会逐一解答。

现在，动手搭建你自己的技术阵地吧！🚀

相关推荐：

https://github.com/larsenpaul061/lcndhr/blob/main/2026%E5%AE%98%E6%96%B9%E8%AE%B2%E8%A7%A3%EF%BC%9A%E4%B9%90%E5%AF%8C%E4%B8%BB%E7%AE%A1app_%E4%BD%B3%E7%84%9A%E5%93%A6%E7%A5%AD%E5%85%9APJWDX.md

<img src="https://i.postimg.cc/c4vG6dZ5/lefu-00018.png" />

相关推荐：

https://github.com/larsenpaul061/lcndhr/commit/9344191643f6241dcdaa1087c4b243285fbec5ae

<img src="https://i.postimg.cc/50pWQ0XN/lefu-00012.png" />
相关推荐：

https://github.com/sheppardrandall419/okbjfs/blob/main/2026%E5%AE%98%E7%BD%91%E7%94%84%E9%80%89%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%A8%B1%E4%B9%90_%E6%8B%90%E5%8E%BF%E5%90%90%E6%96%99%E5%94%A4KLLLY.md

<img src="https://i.postimg.cc/TwTXPmYs/lefu-00010.png" />
相关推荐：

https://github.com/sheppardrandall419/okbjfs/commit/415902b90e39edd7dbaade7f7bd70359e8519743

<img src="https://i.postimg.cc/1XjxMj0W/lefu-00015.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
