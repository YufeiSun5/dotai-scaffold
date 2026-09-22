# dotai-scaffold

> One prompt to establish actionable architecture, development, and testing constraints.
>
> 一个提示词，建立可执行的架构、开发和测试约束。
>
> ひとつのプロンプトで、実行可能なアーキテクチャ・開発・テストの制約を整備。

## What is this? / 这是什么？ / これは何？

A reusable prompt for establishing or maintaining a software project's design and AI collaboration system. It starts with business needs, defines module responsibilities and dependency directions, and connects critical constraints to implementation locations and verification methods. The goal is to help future AI agents know where rules belong, where to change code, how to verify changes, and what remains unfinished.

一份可复用的提示词，用于建立或维护软件项目的设计与 AI 协作体系。从业务需求出发，明确模块职责和依赖方向，将关键约束落实到实现位置和验证方法，让后续 AI 清楚规则在哪里、代码改在哪里、如何验证、哪些事情尚未完成。

ソフトウェアプロジェクトの設計とAI協業体系を構築・保守するための再利用可能なプロンプトです。業務要件から出発し、モジュールの責務と依存方向を定め、重要な制約を実装箇所と検証方法に結び付けます。後続のAIがルールの所在、コードの変更先、検証方法、未完了事項を把握できるようにします。

## Prompt Files / 提示词文件 / プロンプトファイル

| Version / 版本 / バージョン | File / 文件 / ファイル |
| --- | --- |
| Project design — English | [prompt-en.txt](prompt-en.txt) |
| 项目设计版 — 简体中文 | [prompt-zh.txt](prompt-zh.txt) |
| プロジェクト設計版 — 日本語 | [prompt-ja.txt](prompt-ja.txt) |
| 多任务包通用版 — 简体中文 | [prompt-zh-task-packages.txt](prompt-zh-task-packages.txt) |

The three project design prompts have the same structure and requirements. The separate Chinese task-package prompt focuses on independent delivery units, task handoffs, and coordination across software, data, and content projects. It has its own execution and documentation rules; choose the version that fits the work instead of combining both sets of rules verbatim.

项目设计版的三种语言保持相同结构和要求。独立的中文多任务包通用版侧重最小独立交付单元、任务接续，以及软件、数据、内容等工程的多任务协作，有自己的执行和文档规则。按工作需要选择版本，避免直接叠加两套规则。

プロジェクト設計版の3言語は同じ構成と要件です。独立した中国語のタスクパッケージ版は、独立して受け入れ可能な成果単位、作業の引き継ぎ、ソフトウェア・データ・コンテンツ工程の複数タスク協業を扱います。独自の実行・文書ルールがあるため、両方をそのまま重ねず、作業に合う版を選んでください。

## Usage / 使用方法 / 使い方

The following applies to the project design prompts.

1. Open the target project in your AI coding tool and paste the prompt for your language.
2. The agent first performs read-only analysis and presents a concrete proposal.
3. Review the architecture, two core workflows, risks, verification methods, and minimum document list.
4. After approval, the agent initializes or updates the documentation and checks the result.

An already approved concrete proposal does not require repeated approval. Analysis-only requests must not modify files. Documentation initialization does not automatically authorize product refactoring, database migrations, or on-site configuration changes.

以下适用于项目设计版。

1. 在 AI 编程工具中打开目标项目，粘贴对应语言的提示词。
2. Agent 先进行只读分析，给出具体方案。
3. 评审架构、两条核心流程、风险、验证方法和最小文档清单。
4. 批准后，Agent 初始化或更新文档并检查结果。

已批准的具体方案无需重复批准。只分析的请求不得修改文件。文档初始化不自动授权产品重构、数据库迁移或现场配置变更。

以下はプロジェクト設計版の手順です。

1. AIコーディングツールで対象プロジェクトを開き、対応言語のプロンプトを貼り付けます。
2. エージェントが読み取り専用で分析し、具体的な案を提示します。
3. アーキテクチャ、2つの主要フロー、リスク、検証方法、最小限の文書一覧を確認します。
4. 承認後、エージェントが文書を初期化または更新し、結果を確認します。

承認済みの具体案に再承認は不要です。分析のみの依頼ではファイルを変更しません。文書の初期化は、製品のリファクタリング、データベース移行、現場設定の変更を自動的に許可するものではありません。

## Design Coverage / 设计覆盖 / 設計の対象

| Area / 方面 / 項目 | Requirements / 要求 / 要件 |
| --- | --- |
| Business / 业务 / 業務 | Users, core workflows, acceptance criteria, system boundaries, data ownership, operating requirements, and explicit exclusions / 用户、核心流程、验收条件、系统边界、数据归属、运行要求和明确不做的事项 / 利用者、主要フロー、受け入れ条件、システム境界、データ所有権、運用要件、対象外事項 |
| Architecture / 架构 / アーキテクチャ | Prefer a modular monolith; define responsibilities and dependency directions without mechanical layering / 优先模块化单体，明确职责和依赖方向，不机械分层 / モジュラーモノリスを優先し、機械的な階層化を避けて責務と依存方向を定義 |
| Constraints / 约束 / 制約 | State ownership, saving versus activation, consistency, concurrency, retries, async processing, history, protocols, security, compatibility / 状态归属、保存与生效、一致性、并发、重试、异步、历史、协议、安全、兼容 / 状態の管理主体、保存と反映、整合性、並行処理、再試行、非同期、履歴、プロトコル、安全性、互換性 |
| Workflows / 流程 / フロー | Walk through two critical use cases, including failure, recovery, and outcome confirmation / 走通两条关键用例，包含失败、恢复和结果确认 / 失敗、復旧、結果確認を含む2つの主要ユースケースを確認 |
| Evidence / 证据 / 根拠 | Separate current implementation, target requirements, proposals, and unknowns / 区分当前实现、目标要求、建议和待确认 / 現在の実装、目標要件、提案、要確認を区別 |
| Verification / 验证 / 検証 | Map constraints to code and checks; distinguish simulation from real-environment acceptance / 约束对应代码和检查，区分模拟与真实环境验收 / 制約をコードと検証に対応付け、シミュレーションと実環境の受け入れを区別 |
| Maintenance / 维护 / 保守 | Reuse rules, review specific boundary problems, and make small verifiable adjustments / 复用规则，针对边界问题审查，小步调整并验证 / ルールを再利用し、境界の問題を絞ってレビューし、小さく変更して検証 |

All four prompts require an explicit layering contract: responsibilities, actual or planned paths, public interfaces, allowed and forbidden dependencies or flows, ownership, and verification methods. The contract has one authoritative document, referenced by instructions, entry points, and relevant task templates. AI must establish ownership before implementation and check boundaries afterward. The task-package version distinguishes its four documentation layers from software architecture or production stages and adapts the latter to the project type.

四份提示词均要求明确分层契约：职责、实际或计划路径、公开接口、允许和禁止的依赖或流转、所有权及验证方式。契约保留唯一母本，由规范、入口和相关任务模板引用；AI 实施前确认归属，实施后检查边界。多任务包版区分协作文档四层与软件架构或生产环节，并按项目类型定义后者。

4つのプロンプトはいずれも、責務、実際または予定のパス、公開インターフェース、許可・禁止する依存や流れ、管理主体、検証方法を含む層の契約を要求します。契約の正本は1つとし、規約、入口、関連タスクテンプレートから参照します。AIは実装前に責務の所在を確認し、実装後に境界を検証します。タスクパッケージ版では、文書の4層とソフトウェア設計または制作工程の分担を区別し、後者をプロジェクトの種類に合わせて定義します。

## Documentation Model / 文档模型 / 文書モデル

Reuse existing documentation before creating new files. The project design prompts use these responsibilities:

优先复用已有文档。项目设计版使用以下职责划分：

新規作成より既存文書の再利用を優先します。プロジェクト設計版では次の責務を定めます。

| Path / 路径 / パス | Responsibility / 职责 / 責務 |
| --- | --- |
| `AGENTS.md` | Short project entry point, constraints, navigation, and verification commands / 简短入口、约束、导航和验证命令 / 簡潔な入口、制約、案内、検証コマンド |
| `MEMORY.md` | Current phase, effective decisions, recent results, necessary context / 当前阶段、有效决策、近期结果和必要上下文 / 現在フェーズ、有効な決定、最近の結果、必要な文脈 |
| `AI_BOARD.md` | Sole active work board: `open`, `in_progress`, `blocked`; impact, next step, evidence / 唯一活跃看板，记录状态、影响、下一步和证据 / 唯一の作業ボード。状態、影響、次の行動、根拠 |
| `.ai/instructions/` | Short, concrete, checkable coding and workflow constraints / 简短、具体、可检查的编码与流程约束 / 短く具体的で確認可能なコーディング・作業制約 |
| `.ai/docs/` | Stable architecture, contracts, testing strategy, decisions, and archives / 稳定架构、契约、测试策略、决策与归档 / 安定した設計、契約、テスト戦略、決定、アーカイブ |

Add `.ai/skills/`, `.ai/agents/`, `.ai/prompts/`, and editor adapters only when needed. A single architecture document may be enough. Major or hard-to-reverse decisions should have short ADRs. Neither a full directory tree nor multiple agents are mandatory.

按需增加 `.ai/skills/`、`.ai/agents/`、`.ai/prompts/` 和编辑器适配。一个架构文档即可承载多个设计主题；重大或难以逆转的决策记录简短 ADR。不以目录齐全或启动多个 Agent 为要求。

`.ai/skills/`、`.ai/agents/`、`.ai/prompts/`、エディタ用アダプタは必要な場合だけ追加します。複数の設計テーマを1つの文書にまとめてもかまいません。重要または取り消しが難しい決定は短いADRに記録します。全ディレクトリや複数Agentの起動は必須ではありません。

## Tool Integration / 工具接入 / ツール連携

A directory does not guarantee automatic loading. Define reading triggers in `AGENTS.md` and tool entry points. Adapters reference authoritative documents and use only formats confirmed to be supported by the tools in the target project. This repository provides prompts, not a universal loader or evidence that every editor integration has been tested.

目录存在不代表工具会自动加载。应在 `AGENTS.md` 和工具入口明确阅读触发条件；适配文件引用母本，只使用目标项目当前工具已确认支持的格式。本仓库提供提示词，不提供通用加载器，也不宣称所有编辑器接入都已测试。

ディレクトリの存在は自動読み込みを保証しません。`AGENTS.md`とツールの入口に読み取り条件を明記してください。アダプタは正本を参照し、対象プロジェクトのツールが対応していると確認できた形式だけを使用します。本リポジトリはプロンプトを提供するものであり、汎用ローダーやすべてのエディタ連携の検証実績を提供するものではありません。

## Completion Criteria / 完成标准 / 完了条件

Check documentation links, effective rules, implementation or planned locations for constraints, actual verification, and tool entry points. Report passed, failed, unexecuted, and blocked checks accurately. Do not declare completion merely because files exist.

检查文档链接、有效规则、约束的实现或计划位置、实际验证和工具入口。如实报告通过、失败、未执行和受阻项，不能仅因文件存在就宣布完成。

文書リンク、有効なルール、制約の実装箇所または予定箇所、実際の検証、ツールの入口を確認してください。合格、失敗、未実行、ブロックされた検証を正確に報告し、ファイルが存在するだけで完了と宣言しないでください。

## License

[MIT](LICENSE)
