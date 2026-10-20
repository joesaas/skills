# skills

个人 Agent Skills 合集。

## prompt-forge — /prompt 提示词生成器

仅手动触发的提示词生成器：输入 `/prompt` 启动后，先解析你已给出的信息、只问缺的项（任务、背景、材料、角色、格式、语气、禁忌、例子、验收标准，每项可跳过），再按任务类型选模板，拼出一份可直接复制使用的提示词。

模板按任务类型分三套，放在各包的 `references/` 里：

- `writing.md` — 写作类（邮件、文案、总结）
- `analysis.md` — 分析类（解读、对比、调研）
- `agent-task.md` — Agent 执行类（项目、代码、多步任务，含验收标准与执行约定）

### 结构

| 路径 | 运行时 | 说明 |
|---|---|---|
| `prompt-forge/` | Claude Code / Codex / 通用 | 标准版：`SKILL.md`（frontmatter 含 `disable-model-invocation: true`，仅手动触发）、`references/`、`agents/openai.yaml`（`allow_implicit_invocation: false`） |
| `prompt-forge/muse/` | Muse | 变体：同一正文，元数据在 `skill.yaml`，包名 `prompt-forge-muse` |

安装：把对应变体目录复制到你的 Agent 的 skills 目录即可（如 Claude Code 的 `~/.claude/skills/`、Codex 的 `~/.codex/skills/`）。入口命令仍是 `/prompt`。
