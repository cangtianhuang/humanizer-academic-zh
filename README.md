# humanizer-academic-zh

Humanizer 中文学术版本，Claude Code Skills / System Prompt，轻量级中文学术论文去 AI 痕迹提示词——运行迅速，节约 token，开箱即用！

## 这是什么

一套精简的中文学术写作润色规则，用于指导 LLM 识别并消除论文中的 AI 生成痕迹。规则基于 AIGC 检测器的统计识别逻辑设计：不改内容，改模式。

本项目追求**短、准、省**——去掉了冗长的示例和评分体系，只保留对 LLM 执行有效的规则本身，适合直接粘贴使用，不浪费上下文窗口。

## 文件说明

| 文件 | 格式 | 说明 |
|---|---|---|
| [`SKILL.md`](SKILL.md) | Claude Code Skills | 带 YAML frontmatter，可直接安装到 `~/.claude/skills/` |
| [`SYSTEM_PROMPT.md`](SYSTEM_PROMPT.md) | System Prompt | 纯提示词，适用于任意 LLM |

两个文件核心内容一致，选适合你工作流的即可。

---

## 安装

### Claude Code Skills

#### 方法一：通过 npx skills 安装（推荐）

[npx skills](https://github.com/vercel-labs/agent-skills) 是一项 AI Agent 技能管理工具，支持 Claude Code、Cursor、Codex 等 40+ 编程助手，一条命令即可完成安装与分发：

```bash
npx skills add cangtianhuang/humanizer-academic-zh
```

安装完成后，技能会自动链接到已安装的 AI 编程助手。验证安装：

```bash
npx skills list
```

更新到最新版本：

```bash
npx skills update cangtianhuang/humanizer-academic-zh
```

卸载：

```bash
npx skills remove cangtianhuang/humanizer-academic-zh
```

#### 方法二：手动安装

1. 下载或克隆本仓库：

   ```bash
   git clone https://github.com/cangtianhuang/humanizer-academic-zh.git
   ```

2. 将 `SKILL.md` 复制到 Claude Code 的 skills 目录：

   - **macOS / Linux**：`~/.claude/skills/`
   - **Windows**：`%USERPROFILE%\.claude\skills\`

   ```bash
   cp humanizer-academic-zh/SKILL.md ~/.claude/skills/humanizer-academic-zh.md
   ```

3. 重启 Claude Code 或重新加载 skills，输入以下命令验证：

   ```
   /humanizer-academic-zh
   ```

#### 方法三：直接下载单文件

只需要 `SKILL.md` 一个文件，无需克隆整个仓库：

```bash
curl -o ~/.claude/skills/humanizer-academic-zh.md \
  https://raw.githubusercontent.com/cangtianhuang/humanizer-academic-zh/main/SKILL.md
```

---

### 作为 System Prompt 使用（适用于任意 LLM）

将 `SYSTEM_PROMPT.md` 的全部内容复制，粘贴到 Claude / ChatGPT / DeepSeek 等模型的系统提示词（System Prompt）字段中，即可在任意对话中激活。

无需安装，复制即用。

---

## 使用

### Claude Code Skills 用法

激活技能后，直接将需要润色的论文片段发给 Claude：

```
/humanizer-academic-zh 请润色以下段落：

[粘贴论文片段]
```

也可以省略前缀，在技能激活状态下直接发送文本：

```
请润色以下段落：

[粘贴论文片段]
```

### System Prompt 用法

设置好系统提示词后，直接在对话框发送需要处理的文本即可，无需额外指令。

---

## 参考来源

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)（WikiProject AI Cleanup）
- [blader/humanizer](https://github.com/blader/humanizer)
- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)
- [redbaronyyyyy-eng/humanizer-zh-academic](https://github.com/redbaronyyyyy-eng/humanizer-zh-academic)

## 协议

MIT License
