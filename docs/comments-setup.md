# Utterances 评论设置说明

此站点已切换到 Utterances（基于 GitHub Issues 的评论系统），因为它比 Giscus 在不启用 Discussions 的仓库中更便捷。

要使 Utterances 正常工作，请确认：
1. 仓库已启用 Issues（Settings -> Issues）。我们的仓库已启用 Issues。
2. config.yaml 中 params.utterances 已启用（enable: true）并设置了 repo（格式 owner/repo）。

已填写的默认配置示例：

params:
  utterances:
    enable: true
    repo: "luoxingqi/myblog"
    issueTerm: "pathname"  # 可选：pathname / url / title / og:title
    label: "comment"
    theme: "github-light"

说明：
- issueTerm 控制 Utterances 如何匹配文章对应的 Issue。通常使用 pathname 可以确保每篇文章对应一个 issue。
- label 可选，用于给 Utterances 创建的 Issue 添加标签，便于管理。
- theme 控制评论框的配色风格，可使用 utterances 支持的主题（如 github-light, github-dark, preferred-color-scheme 等）。

如果你想改回 Giscus，请在仓库启用 Discussions 并按照 docs/giscus-setup.md 中的说明获取 repositoryId 与 categoryId，然后将 params.giscus.enable 设置为 true 并填入相应 ID。
