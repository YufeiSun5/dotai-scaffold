# dotai-scaffold

> One prompt to make any project AI-agent-ready.
>
> 一个提示词，让任何项目对 AI Agent 就绪。
>
> ワンプロンプトで、あらゆるプロジェクトをAIエージェント対応に。

## What is this? / 这是什么？ / これは何？

A universal prompt that instructs any AI agent (Copilot, Cursor, Trae, Claude, etc.) to analyze your project and scaffold a complete `.ai/` documentation system — coding standards, reusable skills, custom agents, prompt templates, and progress tracking.

一个通用提示词，指导任意 AI Agent（Copilot、Cursor、Trae、Claude 等）分析你的项目并搭建完整的 `.ai/` 文档体系——编码规范、可复用技能、自定义 Agent、Prompt 模板和开发进度追踪。

汎用プロンプト。任意のAIエージェント（Copilot、Cursor、Trae、Claude等）にプロジェクトを分析させ、完全な `.ai/` ドキュメント体系を構築させます——コーディング規約、再利用可能なスキル、カスタムエージェント、プロンプトテンプレート、開発進捗管理。

## Generated Structure / 生成结构 / 生成される構造

```
.ai-instructions              # Entry point for AI agents
AGENTS.md                     # Project overview (≤30 lines)
MEMORY.md                     # Development progress tracking
.ai/
  instructions/               # Coding standards with frontmatter
    backend.md                #   applyTo: **/*.go, **/*.py, etc.
    frontend.md               #   applyTo: src/**/*.tsx, etc.
    ai-workflow.md             #   Documentation update rules
  docs/                       # Feature design & tracking
    architecture.md
  skills/                     # Reusable operation templates
    add-api-endpoint/SKILL.md
    update-progress/SKILL.md
  agents/                     # Custom agents with tool restrictions
    code-review.agent.md      #   tools: [read, search] (read-only)
  prompts/                    # Quick-trigger task templates
    new-api.prompt.md
```

## Usage / 使用方法 / 使い方

1. Open your project in any AI-powered editor
2. Start a new chat with the AI agent
3. Paste the content of the prompt file for your language
4. The agent will analyze your project and create the full `.ai/` structure

---

1. 在任意 AI 编辑器中打开你的项目
2. 开启一个新的 AI 对话
3. 粘贴对应语言的提示词文件内容
4. Agent 会分析项目并创建完整的 `.ai/` 结构

---

1. 任意のAI対応エディタでプロジェクトを開く
2. AIエージェントと新しいチャットを開始
3. 対応言語のプロンプトファイルの内容を貼り付ける
4. エージェントがプロジェクトを分析し、完全な `.ai/` 構造を作成

## Prompt Files / 提示词文件 / プロンプトファイル

| Language | File |
|----------|------|
| English | [prompt-en.txt](prompt-en.txt) |
| 简体中文 | [prompt-zh.txt](prompt-zh.txt) |
| 日本語 | [prompt-ja.txt](prompt-ja.txt) |

## Design Principles / 设计原则 / 設計原則

| Principle | Why |
|-----------|-----|
| **Concise first** | AGENTS.md loads every conversation — shorter = more room for code |
| **Keyword-driven discovery** | `description` is how agents find files — keywords must be precise |
| **One file, one concern** | Don't mix backend rules with frontend rules |
| **Show don't tell** | Brief code examples over long paragraphs |
| **Link don't embed** | Details in docs/, main files only index |
| **Cross-editor compatible** | No editor-specific hooks — works everywhere |

| 原则 | 原因 |
|------|------|
| **精简优先** | AGENTS.md 每次对话全量加载——越短留给代码的空间越多 |
| **关键词驱动发现** | `description` 是 Agent 发现文件的唯一依据——关键词要准 |
| **一个文件一个关注点** | 不要把后端规范和前端规范混在一起 |
| **Show don't tell** | 用简短代码示例而非长段落 |
| **Link don't embed** | 详细内容放 docs/，主文件只索引 |
| **跨编辑器兼容** | 不依赖特定编辑器——到处能用 |

## Compatibility / 兼容性 / 互換性

Tested with: **VS Code + Copilot**, **Cursor**, **Trae**, **Claude Code**

The `.ai/` directory convention is recognized by multiple AI coding tools. YAML frontmatter (`description`, `applyTo`, `name`, `tools`) follows the emerging cross-editor standard.

## License

[MIT](LICENSE)
