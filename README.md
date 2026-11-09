# clean-ui

一个给 AI 编程助手用的 skill：让它写出的前端界面**干净、好看、像成熟产品**，而不是像带批注的草稿。

AI 做界面最常见的两个毛病：

- **话多**：每块都配一段说明、口径、操作提示、"这是演示数据"。
- **花哨**：七八种颜色的标签、到处是阴影和渐变、卡片套卡片、数字发光、emoji 当图标。

这个 skill 把"删字、收敛、截图自查"变成 AI 每次都会执行的流程。规则来自真实项目里一轮轮的改版记录，不是凭空列的。

## 内容

| 文件 | 作用 |
| --- | --- |
| [`SKILL.md`](SKILL.md) | 核心原则、三步工作流（沿用现有体系 → 文字关 + 视觉关 → 截图自查）、不能破坏的底线 |
| [`references/text-audit.md`](references/text-audit.md) | 哪些字该删、删了用什么替代、措辞规范 |
| [`references/visual-rules.md`](references/visual-rules.md) | 颜色、层次、圆角、字号、间距、常见组件、图表规则，附起步 token（Ant Design / Tailwind 写法） |
| [`references/review-checklist.md`](references/review-checklist.md) | 桌面 + 手机截图自查清单 |

一句话核心：**用户如果不看这行字，会做错什么吗？不会就删。**

## 安装

### 一句话安装

把下面这段话直接发给你的 AI 编程助手（Claude Code、Codex、Cursor 等）：

```text
帮我安装 clean-ui 这个 skill：https://github.com/4646with/clean-ui 。先判断你自己是哪个工具：Claude Code 就 clone 到 ~/.claude/skills/clean-ui，Codex 就 clone 到 ~/.codex/skills/clean-ui，其他支持 SKILL.md 的工具放进它的 skills 目录；不支持 skill 的工具，把 SKILL.md 和 references/ 的要点合并进当前项目的规则文件（如 AGENTS.md 或 .cursor/rules）。装完告诉我装在哪，以及以后怎么触发它。
```

### 手动安装

**Claude Code**

```bash
git clone https://github.com/4646with/clean-ui.git ~/.claude/skills/clean-ui
```

**Codex**

```bash
git clone https://github.com/4646with/clean-ui.git ~/.codex/skills/clean-ui
```

其他支持 `SKILL.md` 格式的工具，放进对应的 skills 目录即可。不支持 skill 的工具（如 Cursor），可以把 `SKILL.md` 和 `references/` 的内容合并进项目规则文件。

## 使用

装好后新开会话，说"界面好看一点""字太多""太乱""像 AI 做的"之类会自动触发；在 Claude Code 里也可以直接输入 `/clean-ui`。

截图自查默认使用 ego-browser（ego lite），没有的话会用当前环境里其他可用的浏览器工具。

与框架无关：React / Vue / Next.js / Vite，Ant Design / shadcn / Tailwind 都适用。

## License

MIT
