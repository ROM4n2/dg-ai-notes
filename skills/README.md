# Skills

本目录存放可独立下载使用的 AI Agent Skills。skill 采用通用的 `SKILL.md` 格式（文件夹 + SKILL.md 主文件 + references 参考资料），所有支持 Agent Skills 的智能体都能直接使用。

| Skill | 用途 |
|---|---|
| [dg-piagent](./dg-piagent/) | Pi-Agent SDK（[@earendil-works/pi-coding-agent](https://github.com/earendil-works/pi)）开发助手：创建 agent、自定义工具、编写扩展、事件系统、会话管理、企业内网接口接入评估。API 核对到 v0.83.0 |

## 怎么安装

把 skill 文件夹放进你所用的智能体的 skills 目录即可，无需其他配置：

| 智能体 | 用户级目录 | 项目级目录 |
|---|---|---|
| Claude Code | `~/.claude/skills/dg-piagent/` | `<项目>/.claude/skills/dg-piagent/` |
| ZCode | `~/.zcode/skills/dg-piagent/` | — |
| Codex | `~/.codex/skills/dg-piagent/` | — |
| pi | `~/.pi/agent/skills/dg-piagent/` | `<项目>/.pi/skills/dg-piagent/` |

> 各智能体的 skills 目录以其官方文档为准；Windows 下 `~` 即 `%USERPROFILE%`。也兼容 `.agents/skills/` 这类跨工具共享目录约定。

下载方式任选其一：

```bash
# 方式一：克隆整个仓库后拷贝
git clone https://github.com/buchidonggua/dg-ai-notes.git
cp -r dg-ai-notes/skills/dg-piagent ~/.claude/skills/
```

```bash
# 方式二：只拉 skills 目录（浅克隆 + 稀疏检出）
git clone --depth 1 --filter=blob:none --sparse https://github.com/buchidonggua/dg-ai-notes.git
cd dg-ai-notes && git sparse-checkout set skills
cp -r skills/dg-piagent ~/.claude/skills/
```

- 方式三：在 GitHub 页面点 **Code → Download ZIP**，解压后取出 `skills/dg-piagent/` 文件夹。

装好后无需重启即可在对话中触发；skill 的触发条件写在 `SKILL.md` 的 frontmatter description 里。变更记录见各 skill 目录下的 `CHANGELOG.md`。
