# Giscus 占位配置说明

你需要把下面的信息替换到 config.yaml 中的 params.giscus 字段：

- repo: "你的 GitHub 仓库，格式 owner/repo，例如 luoxingqi/myblog"
- repoId: "repositoryId（可通过 GraphQL 或 gh cli 获取）"
- category: "你在 Discussions 中创建的分类名称（例如 Comments）"
- categoryId: "对应分类的 ID（通过 GraphQL 获取，形如 DIC_kw...）"

示例 GraphQL 查询（使用 gh CLI）：

gh api graphql -f query='query { repository(owner:"luoxingqi", name:"myblog") { id, discussionCategories(first:10) { nodes { id, name } } } }'

把得到的 id 填入 config.yaml 的 repoId 与 categoryId。
