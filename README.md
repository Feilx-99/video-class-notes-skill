# 视频课堂笔记（video-class-notes）

> **English.** A Cursor Agent Skill that turns a Bilibili, YouTube, or local video link into student-style class notes in Markdown: timestamps on each point, screenshots saved beside the note, and about ten quizzes with answers collected at the end.

把视频链接当成一堂课来整理。产出一份可复盘的 `.md` 课堂笔记，以及与笔记放在同一目录的截图。笔记按学生口吻写清「讲了什么、为什么重要」，并带上时间段。

## 这个技能做什么

- 接受 B 站（含多 P）、YouTube、短链或本地视频。
- 写成 Markdown：元信息、章节总览表、正文知识点（时间段 + 截图）、约 8–12 道自测题。
- 题目和答案分开：答案单独放在文末「参考答案」。
- 关键观点、板书、标题卡、金句各配截图。

教学规矩都写在 [`video-class-notes/SKILL.md`](video-class-notes/SKILL.md) 里。文件夹 ID 是 `video-class-notes`；技能 frontmatter 里的 `name` 仍是「视频课堂笔记」。

## 安装

把整个 `video-class-notes/` 目录复制到 Cursor 的技能目录，文件夹名保持 `video-class-notes`，里面保留 `SKILL.md`。Cursor 启动时会自动发现这些位置下的技能：

| 位置 | 范围 |
| --- | --- |
| `~/.cursor/skills/video-class-notes/` | 当前用户，本机所有项目 |
| `.cursor/skills/video-class-notes/` | 仅当前项目（可提交进该项目仓库） |
| `~/.agents/skills/video-class-notes/` | 当前用户（Agent Skills 兼容路径） |
| `.agents/skills/video-class-notes/` | 仅当前项目（Agent Skills 兼容路径） |

兼容目录同样可用：`~/.claude/skills/`、`.claude/skills/`、`~/.codex/skills/`、`.codex/skills/`。

用户级安装示例：

```bash
git clone https://github.com/Feilx-99/video-class-notes-skill.git
mkdir -p ~/.cursor/skills
cp -R video-class-notes-skill/video-class-notes ~/.cursor/skills/
```

项目级安装示例（在目标项目根目录执行）：

```bash
mkdir -p .cursor/skills
cp -R /path/to/video-class-notes-skill/video-class-notes .cursor/skills/
```

装好后打开 Cursor 的 Customize → Skills，应能看到「视频课堂笔记」。对话输入 `/` 可搜索并手动挂上该技能。希望 Cloud Agent 使用时，把技能放进仓库的 `.cursor/skills/`，或在本机 Settings → Agents 里打开 Sync Skills for Cloud Agents（只同步 `~/.cursor/skills/`）。

## 触发说法

对 Agent 这样说就会用到本技能：

- 「按视频笔记规矩整理」
- 发来视频链接，并要求当学生做课堂笔记、详细笔记，或「知识点 + 时间段」
- 提到「每个知识点标时间段」「每 P 整理」「自测题」「截图」「.md」

## 许可

[MIT License](LICENSE)。
