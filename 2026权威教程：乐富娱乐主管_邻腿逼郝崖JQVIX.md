乐富娱乐主管【Q-——333307——】乐富娱乐主管【 辋芷《888yx●vip》 】
乐富娱乐主管【Q-——333307——】乐富娱乐主管【 辋芷《888yx●vip》 】

 从零到一：我用 GitHub Actions 自动化部署了自己的博客

> 你是否也曾因为手动部署博客而感到繁琐？今天，我将分享如何利用 GitHub Actions 实现完全自动化的部署流程，让每次提交代码后，网站自动更新，真正实现“只管写文章，其余交给流水线”。

 为什么选择 GitHub Actions？

作为一名独立开发者，我最初是手动执行 `hexo g && hexo d` 或者 `npm run build && scp` 到服务器，直到有一次出差忘带电脑，博客却急需更新线上内容。那一刻，我认识到自动化部署的迫切性。

GitHub Actions 的核心优势在于：它直接集成在代码托管平台中，无需额外购买 CI/CD 服务，且有免费额度。它通过 `.github/workflows` 目录下的 YAML 文件描述工作流，代码推送即触发构建，天然适合开源项目与个人站点。

 我的自动化工作流配置

下面是一个极简但完整的配置示例，我将它放在 `.github/workflows/deploy.yml` 中：

```yaml
name: Deploy Blog

on:
  push:
    branches: [main]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout 代码
        uses: actions/checkout@v4

      - name: 安装 Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: 安装依赖与构建
        run: |
          npm ci
          npm run build

      - name: 部署到服务器
        uses: easingthemes/ssh-deploy@main
        with:
          SSH_PRIVATE_KEY: ${{ secrets.SSH_PRIVATE_KEY }}
          ARGS: "-rlgoDzvc -i --delete"
          SOURCE: "public/"
          REMOTE_HOST: ${{ secrets.REMOTE_HOST }}
          REMOTE_USER: ${{ secrets.REMOTE_USER }}
          TARGET: "/var/www/html"
```

关键点解析：
- `on.push` 触发条件：只有推送到 main 分支才构建。
- 使用 `secrets` 存储敏感信息（如 SSH 私钥），避免明文暴露。
- `--delete` 参数保证远端与本地目录完全同步，避免残留旧文件。

 遇到的坑与排查技巧

在实际操作中，最容易出错的是 SSH 密钥权限问题。记得在服务器上生成密钥后，将私钥内容完整复制到仓库的 `Secrets and variables -> Actions` 中，并确保公钥已加入 `~/.ssh/authorized_keys`。

此外，如果构建时间过长，建议开启 Actions 的缓存功能。只需添加 `actions/cache` 步骤，将 `node_modules` 或 `public` 目录缓存，构建速度能提升 50% 以上。

 自动化的收益与延伸思考

配置完成后，我的工作流变成了：本地编辑 Markdown → git push → 云端自动构建部署 → 两分钟后访问新文章。这节省了我每周约一小时的手动操作时间，更重要的是，不再担心“服务器本地文件忘了同步”这类低级错误。

如果你也在用 VuePress、Hugo 或 MkDocs，思路完全一致，只需替换构建命令。建议下一步可以尝试在 Action 中接入 Webhook 通知，比如部署成功后通过邮件或微信推送给你的订阅读者，让博客运营本身也“自动化”起来。

相关推荐：

https://github.com/vazquezdarin376/rowkxj/blob/main/2026%E5%AE%98%E7%BD%91%E7%94%84%E9%80%89%EF%BC%9A%E4%B9%90%E5%AF%8C%E4%B8%BB%E7%AE%A1%E5%9C%B0%E5%9D%80_%E8%BE%A3%E8%B0%B0%E6%94%B6%E7%9D%A3%E7%9B%8FNOUVP.md

<img src="https://i.postimg.cc/1XjxMj0W/lefu-00015.png" />

相关推荐：

https://github.com/vazquezdarin376/rowkxj/commit/6aff8daab2dfa02cc8571a270939f0d6a8908f89

<img src="https://i.postimg.cc/XNH0VrMC/lefu-00016.png" />
相关推荐：

https://github.com/sheppardrandall419/okbjfs/blob/main/2026%E7%A7%91%E6%8A%80%E7%83%AD%E6%A6%9C%EF%BC%9A%E4%B9%90%E5%AF%8C%E4%B8%BB%E7%AE%A1%E6%B5%8B%E9%80%9F_%E8%83%83%E8%AF%8D%E6%82%8D%E6%85%B0%E6%A1%A5OPQQY.md

<img src="https://i.postimg.cc/tJTQ3j6x/lefu-00013.png" />
相关推荐：

https://github.com/sheppardrandall419/okbjfs/commit/37fac4e877e18afedf731c341916df08ca641b1c

<img src="https://i.postimg.cc/wT1Y39gp/lefu-00019.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
