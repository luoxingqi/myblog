# myblog

这是由 Hugo + PaperMod 主题生成的个人博客模板，已配置：

- 语言：中文
- 主题：PaperMod（通过 Hugo Module 导入）
- 评论：Giscus（需要在仓库启用 Discussions 并填入 repoId/categoryId）
- 部署：GitHub Pages（使用 GitHub Actions 自动构建并部署到 gh-pages 分支）
- 包含 2 篇示例文章

快速开始（在本地）：

1. 克隆仓库并进入目录：
   git clone https://github.com/luoxingqi/myblog.git
   cd myblog

2. 在本地安装 Hugo（版本 0.111 及以上推荐）。
   https://gohugo.io/getting-started/installing

3. 获取 Hugo Module（拉取 PaperMod 主题）：
   hugo mod get -u

4. 本地运行：
   hugo server -D

5. 打包生成：
   hugo --minify

如何配置 Giscus（步骤）：

1. 在仓库的 Settings -> Discussions 中启用 Discussions（如果未启用）。
2. 在 Discussions 中创建一个 Category（例如：Comments）。
3. 获取 repositoryId 与 categoryId：
   - repositoryId 可用 GitHub GraphQL API 查询，或者使用下面的步骤：
     a. 打开仓库页面，按 F12 打开开发者工具 -> Network -> 搜索 repo or repositories 接口，查找 repositoryId。
     b. 推荐使用第三方工具或 CLI，如 gh api 或 GraphQL 查询获取。
   - categoryId 也可通过 GraphQL 查询获得（category id 形如 DIC_kw...）。
4. 在 config.yaml 中把 params.giscus 下对应字段替换为你的 repo / ids。

或者你可以改用 Utterances（基于 Issues），那只需开启 Issues 即可。

部署说明：
- 我已添加 GitHub Actions workflow，会在 push 到 main 后构建并把 public/ 发布到 gh-pages 分支。你需要在仓库的 Settings -> Pages 中把部署来源设置为 gh-pages 分支（/ 根）。

如需我代为开启 Discussions 或替换 Giscus 的 repoId/categoryId，请告诉我对应 ID 或授权说明。
