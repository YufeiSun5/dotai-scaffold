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
    ai-workflow.md             #   Documentation update rules (required)
    backend.md                 #   applyTo: **/*.go, **/*.py, etc. (as needed)
    frontend.md                #   applyTo: src/**/*.tsx, etc. (as needed)
  docs/                       # Feature design & tracking
    README.md                  #   Directory guide: purpose & conventions
    architecture.md            #   (as needed)
  skills/                     # Reusable operation templates
    README.md                  #   Directory guide: what skills are & criteria
    add-api-endpoint/SKILL.md  #   (as needed)
  agents/                     # Custom agents with tool restrictions
    README.md                  #   Directory guide: agent format & tool rules
    code-review.agent.md       #   tools: [read, search] (as needed)
  prompts/                    # Quick-trigger task templates
    README.md                  #   Directory guide: prompt format & usage
    new-api.prompt.md          #   (as needed)
```

### Editor Adapter Layer / 编辑器适配层 / エディタアダプタレイヤー

```
.github/                       # Copilot adapter (thin entry layer)
  copilot-instructions.md       #   Repo-level: read AGENTS.md + .ai-instructions
  instructions/
    frontend.instructions.md    #   Path-level: points to .ai/instructions/frontend.md
    backend.instructions.md     #   Path-level: points to .ai/instructions/backend.md
    tests.instructions.md       #   Path-level: points to .ai/instructions/tests.md

.cursor/                       # Cursor adapter (thin entry layer)
  rules/
    00-core.mdc                 #   Always-on: read AGENTS.md + .ai-instructions
    frontend.mdc                #   Glob-scoped: points to .ai/instructions/frontend.md
    backend.mdc                 #   Glob-scoped: points to .ai/instructions/backend.md
    tests.mdc                   #   Glob-scoped: points to .ai/instructions/tests.md
```

## Usage / 使用方法 / 使い方

1. Open your project in any AI-powered editor
2. Start a new chat with the AI agent
3. Paste the content of the prompt file for your language
4. The agent will first analyze your project and output a report
5. Confirm the report, then the agent creates the `.ai/` structure

For small projects (≤10 core modules), the agent may skip confirmation and create files directly.

---

1. 在任意 AI 编辑器中打开你的项目
2. 开启一个新的 AI 对话
3. 粘贴对应语言的提示词文件内容
4. Agent 会先分析项目并输出分析报告
5. 确认报告后，Agent 创建完整的 `.ai/` 结构

小型项目（≤10 个核心模块）Agent 可跳过确认直接创建。

---

1. 任意のAI対応エディタでプロジェクトを開く
2. AIエージェントと新しいチャットを開始
3. 対応言語のプロンプトファイルの内容を貼り付ける
4. エージェントがまずプロジェクトを分析しレポートを出力
5. レポートを確認後、エージェントが `.ai/` 構造を作成

小規模プロジェクト（コアモジュール10以下）の場合、確認をスキップして直接作成可。

## Prompt Files / 提示词文件 / プロンプトファイル

| Language | File |
|----------|------|
| English | [prompt-en.txt](prompt-en.txt) |
| 简体中文 | [prompt-zh.txt](prompt-zh.txt) |
| 日本語 | [prompt-ja.txt](prompt-ja.txt) |

## Design Principles / 设计原则 / 設計原則

| Principle | Why |
|-----------|-----|
| **Evidence first** | All documentation must be grounded in source code, config, tests — no fabrication |
| **Concise first** | AGENTS.md loads every conversation — shorter = more room for code |
| **Keyword-driven discovery** | `description` is how agents find files — keywords must be precise |
| **One file, one concern** | Don't mix backend rules with frontend rules |
| **Show don't tell** | Brief code examples over long paragraphs |
| **Link don't embed** | Details in docs/, main files only index |
| **Cross-editor compatible** | No editor-specific hooks — works everywhere |
| **Safe writes** | Supplement over overwrite; mark uncertainties; no empty files |

| 原则 | 原因 |
|------|------|
| **证据优先** | 文档内容必须基于源码、配置、测试推断——不得编造 |
| **精简优先** | AGENTS.md 每次对话全量加载——越短留给代码的空间越多 |
| **关键词驱动发现** | `description` 是 Agent 发现文件的唯一依据——关键词要准 |
| **一个文件一个关注点** | 不要把后端规范和前端规范混在一起 |
| **Show don't tell** | 用简短代码示例而非长段落 |
| **Link don't embed** | 详细内容放 docs/，主文件只索引 |
| **跨编辑器兼容** | 不依赖特定编辑器——到处能用 |
| **安全写入** | 已有文件优先补充不覆盖，不确定标记待确认，不创建空洞文件 |

## Key Features / 核心特性 / 主な特徴

### Phased Execution / 分阶段执行 / 段階的実行

The prompt follows a 3-phase approach instead of creating everything at once:
1. **Analyze** — Understand the project within defined scan boundaries
2. **Report** — Output findings for user confirmation before creating files
3. **Create** — Build files in priority order with safe write rules

提示词采用三阶段方式而非一次性创建全部：
1. **分析** — 在定义的扫描边界内理解项目
2. **报告** — 输出分析结果供用户确认后再创建文件
3. **创建** — 按优先级创建文件，遵循安全写入规则

### Degradation Strategy / 降级策略 / デグレード戦略

When the AI can't determine something with certainty, it documents the current state rather than guessing. Unconfirmed content is explicitly marked as TBD.

当 AI 无法确定某些内容时，记录现状而非猜测。未确认内容显式标记为"待确认"。

### Editor Adapter Layer / 编辑器适配层 / エディタアダプタレイヤー

`.ai/` is the single source of truth. Thin adapter entries in `.github/` (Copilot) and `.cursor/` (Cursor) point editors to the right source files — no duplication.

`.ai/` 为唯一母本。`.github/`（Copilot）和 `.cursor/`（Cursor）中的薄适配层将编辑器引导到正确的源文件——不复制规范。

## Compatibility / 兼容性 / 互換性

Tested with: **VS Code + Copilot**, **Cursor**, **Trae**, **Claude Code**

The `.ai/` directory convention is recognized by multiple AI coding tools. YAML frontmatter (`description`, `applyTo`, `name`, `tools`) follows the emerging cross-editor standard.

The editor adapter layer provides native integration:
- **Copilot**: `.github/copilot-instructions.md` + `.github/instructions/*.instructions.md`
- **Cursor**: `.cursor/rules/*.mdc` + `AGENTS.md`

## License

[MIT](LICENSE)
