乐富地址注册【Q-——333307——】乐富地址注册【 辋芷《888yx●vip》 】
乐富地址注册【Q-——333307——】乐富地址注册【 辋芷《888yx●vip》 】

 如何用 GitHub Actions 自动部署前端项目？一篇文章搞定 CI/CD

> 还在手动上传服务器？3 分钟学会 GitHub Actions，自动构建、测试、部署全搞定，小白也能轻松上手。

---

 为什么你需要 GitHub Actions？

每次改完代码，都要本地 build、再手动上传到服务器？不仅麻烦，还容易出错。

GitHub Actions 是 GitHub 自带的 CI/CD 工具，直接在仓库里配置 workflow，就能实现：

- 代码推送到 GitHub 后自动执行测试
- 测试通过后自动构建产物
- 构建完成后自动部署到服务器或静态托管平台

全程零人工干预，效率直接拉满。

---

 核心概念：Workflow / Job / Step

| 概念 | 作用 |
|------|------|
| Workflow | 一个完整的自动化流程，放在 `.github/workflows/` 目录 |
| Job | 流程中的一个任务，比如“构建”和“部署”是不同 Job |
| Step | Job 里的每一步操作，比如“安装依赖”“运行脚本” |

理解这三层，配置文件就能看懂了。

---

 实战：自动部署到 GitHub Pages

以 Vue 项目为例，新建 `.github/workflows/deploy.yml`：

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: Install & Build
        run: |
          npm install
          npm run build

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
```

> 替换 `./dist` 为你自己的构建输出目录即可。

---

 进阶技巧：缓存依赖 + 多环境部署

缓存 Node 依赖，加速构建：

```yaml
- name: Cache node_modules
  uses: actions/cache@v3
  with:
    path: node_modules
    key: ${{ runner.os }}-node-${{ hashFiles('package-lock.json') }}
```

多环境（测试/生产）部署，只需在 `on.push.branches` 里引用不同分支，再根据分支设置环境变量即可。

---

 常见坑 & 注意事项

1. 权限报错：仓库 Settings → Actions → Workflow permissions 改为 `Read and write permissions`
2. secrets 密钥：如需要 SSH 私钥，在仓库 Settings → Secrets and variables → Actions 中添加
3. 构建超时：默认 6 小时，一般够用；如果超时，检查是否有死循环或网络问题

---

 互动引导

是否遇到这些问题？留言区聊：

- 部署时 `permission denied` 怎么办？
- 如何推送失败时自动发邮件？
- 你目前项目用的是什么 CI/CD 方案？

---

如果你觉得这篇文章对你有帮助，欢迎 点赞 + 收藏 + 关注，后续我会继续输出 DevOps 实战干货。也欢迎在评论区留下你的疑问，我看到都会回复。

---

本文首发于 GitHub 技术社区，原创不易，未经授权禁止转载。

相关推荐：

https://github.com/hoffmanandrew448/cbjrry/blob/main/2026%E5%AE%98%E7%BD%91%E4%B8%A5%E9%80%89%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%A8%B1%E4%B9%90%E5%BC%80%E5%8F%B7_%E6%AD%A2%E4%BD%A3%E8%8B%8D%E8%85%A5%E5%B9%BDOBBHU.md

<img src="https://i.postimg.cc/YSKHJZ5P/lefu-00006.png" />

相关推荐：

https://github.com/hoffmanandrew448/cbjrry/commit/0ef8f71d90a45926befbdfc7e4aa3e8eef52e98b

<img src="https://i.postimg.cc/tJTQ3j6x/lefu-00013.png" />
相关推荐：

https://github.com/leebradley6/ubrqlg/blob/main/2026%E5%AE%98%E7%BD%91%E6%89%8B%E5%86%8C%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%A8%B1%E4%B9%90%E5%AE%98%E7%BD%91_%E6%8E%8F%E7%B2%9F%E6%B3%BB%E6%81%8D%E5%AE%A4FNBPQ.md

<img src="https://i.postimg.cc/FKy4mGmf/lefu-00008.png" />
相关推荐：

https://github.com/leebradley6/ubrqlg/commit/90b36ec47996564add37326b03cfd00fb3fee3b9

<img src="https://i.postimg.cc/XqJSfb5x/lefu-00014.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
