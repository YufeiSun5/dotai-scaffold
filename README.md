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
3. Review the architecture, two core workflows, initial feature-map scope and evidence gaps, risks, verification methods, and minimum document list.
4. After approval, the agent initializes or updates the documentation and checks the result.

An already approved concrete proposal does not require repeated approval. Analysis-only requests must not modify files. Documentation initialization does not automatically authorize product refactoring, database migrations, or on-site configuration changes.

以下适用于项目设计版。

1. 在 AI 编程工具中打开目标项目，粘贴对应语言的提示词。
2. Agent 先进行只读分析，给出具体方案。
3. 评审架构、两条核心流程、初始功能地图范围与证据缺口、风险、验证方法和最小文档清单。
4. 批准后，Agent 初始化或更新文档并检查结果。

已批准的具体方案无需重复批准。只分析的请求不得修改文件。文档初始化不自动授权产品重构、数据库迁移或现场配置变更。

以下はプロジェクト設計版の手順です。

1. AIコーディングツールで対象プロジェクトを開き、対応言語のプロンプトを貼り付けます。
2. エージェントが読み取り専用で分析し、具体的な案を提示します。
3. アーキテクチャ、2つの主要フロー、初期機能マップの範囲と根拠の不足、リスク、検証方法、最小限の文書一覧を確認します。
4. 承認後、エージェントが文書を初期化または更新し、結果を確認します。

承認済みの具体案に再承認は不要です。分析のみの依頼ではファイルを変更しません。文書の初期化は、製品のリファクタリング、データベース移行、現場設定の変更を自動的に許可するものではありません。

## Design Coverage / 设计覆盖 / 設計の対象

| Area / 方面 / 項目 | Requirements / 要求 / 要件 |
| --- | --- |
| Business / 业务 / 業務 | Users, core workflows, acceptance criteria, system boundaries, data ownership, operating requirements, and explicit exclusions / 用户、核心流程、验收条件、系统边界、数据归属、运行要求和明确不做的事项 / 利用者、主要フロー、受け入れ条件、システム境界、データ所有権、運用要件、対象外事項 |
| Architecture / 架构 / アーキテクチャ | Prefer a modular monolith; define responsibilities and dependency directions without mechanical layering / 优先模块化单体，明确职责和依赖方向，不机械分层 / モジュラーモノリスを優先し、機械的な階層化を避けて責務と依存方向を定義 |
| Constraints / 约束 / 制約 | State ownership, saving versus activation, consistency, concurrency, retries, async processing, history, protocols, security, compatibility / 状态归属、保存与生效、一致性、并发、重试、异步、历史、协议、安全、兼容 / 状態の管理主体、保存と反映、整合性、並行処理、再試行、非同期、履歴、プロトコル、安全性、互換性 |
| Workflows / 流程 / フロー | Walk through two critical use cases, including failure, recovery, and outcome confirmation / 走通两条关键用例，包含失败、恢复和结果确认 / 失敗、復旧、結果確認を含む2つの主要ユースケースを確認 |
| Feature map / 功能地图 / 機能マップ | User goals, entry points and prerequisites, driving methods, observable results, implementation and test links / 用户目标、入口与前置条件、驱动方法、可观察结果、实现与测试链接 / ユーザーの目的、入口と前提条件、駆動方法、観測可能な結果、実装とテストへのリンク |
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
| Existing documentation section or `.ai/docs/feature-map/` as needed / 已有文档章节或按需拆分 / 既存文書の節または必要に応じた分割 | Maintained user journeys and verification recipes; link implementation, contracts, and test evidence / 持续维护的用户旅程与验证方法，引用实现、契约和测试证据 / 保守するユーザーの操作手順と検証方法。実装、契約、検証の証拠を参照 |

Add `.ai/skills/`, `.ai/agents/`, `.ai/prompts/`, and editor adapters only when needed. A single architecture document may be enough. Major or hard-to-reverse decisions should have short ADRs. Neither a full directory tree nor multiple agents are mandatory.

按需增加 `.ai/skills/`、`.ai/agents/`、`.ai/prompts/` 和编辑器适配。一个架构文档即可承载多个设计主题；重大或难以逆转的决策记录简短 ADR。不以目录齐全或启动多个 Agent 为要求。

`.ai/skills/`、`.ai/agents/`、`.ai/prompts/`、エディタ用アダプタは必要な場合だけ追加します。複数の設計テーマを1つの文書にまとめてもかまいません。重要または取り消しが難しい決定は短いADRに記録します。全ディレクトリや複数Agentの起動は必須ではありません。

## Feature Map / 功能地图 / 機能マップ

All four prompts now use a lightweight feature map to help AI locate a capability and exercise it as a user would. Start with 3–5 core features (fewer if appropriate), reusing an existing section; split into an index such as `.ai/docs/feature-map/README.md` and feature details only when useful. Each entry covers user goals, entry points and prerequisites, actual steps and driving methods, observable success including relevant side effects, and links to implementation, contracts, and tests. Reuse existing harnesses and verification maps. Source inference, planned behavior, and live evidence stay distinct; actual run results remain in verification records or task packages. `AGENTS.md` defines reading triggers. Before work, locate relevant journeys; afterward, exercise them, report actual coverage and blockers, and update affected entries and links. The map is neither a passing test nor another store for business rules, task status, or test logs. Separate documentation drift and harness gaps from product bugs; never rewrite a journey to conceal a bug. For non-software work, describe the real use or delivery process without imposing a UI or browser.

四份提示词均加入轻量功能地图，帮助 AI 定位能力并按用户方式实际验证。从 3–5 个核心功能开始（较少时可更少），优先复用已有章节；确有需要才拆成如 `.ai/docs/feature-map/README.md` 的索引与功能详情。每项说明用户目标、入口与前置条件、实际步骤与驱动方法、包含相关副作用的可观察成功结果，以及实现、契约和测试链接。复用已有驱动工具和验证地图，区分源码推断、计划行为与实际执行证据；运行结果留在验证记录或任务包。`AGENTS.md` 定义阅读触发条件，开工前定位旅程，完成后实际走受影响旅程、报告覆盖与阻塞，并更新条目及链接。地图不是测试通过证明，也不另存业务规则、任务状态或测试日志；区分文档漂移、驱动工具缺口与产品 bug，不通过改写旅程掩盖 bug。非软件工程描述真实使用或交付流程，不强加 UI 或浏览器。

4つのプロンプトに簡潔な機能マップを追加しました。AIが機能を探し、ユーザーと同じ操作で検証できるようにします。主要な3–5機能（少ない場合はそれ以下）から始め、既存の節を優先して再利用します。必要な場合だけ `.ai/docs/feature-map/README.md` のような索引と機能別の詳細に分割します。各項目は目的、入口と前提条件、実際の操作と駆動方法、関連する副作用を含む観測可能な成功結果、実装・契約・テストへのリンクを示します。既存のハーネスや検証マップを再利用し、ソースからの推定、予定の挙動、実動作の証拠を区別します。実行結果は検証記録またはタスクパッケージに残します。`AGENTS.md` に読む条件を定め、着手前に関連手順を特定し、完了後に実際に操作して検証範囲と阻害要因を報告し、関連項目とリンクを更新します。マップはテスト合格の証明でも、業務ルール・タスク状態・テストログの別の正本でもありません。文書のずれ、駆動ツールの不足、製品の不具合を区別し、不具合を隠すために手順を書き換えないでください。ソフトウェア以外では実際の利用・納品手順を扱い、UIやブラウザを強制しません。

References / 参考 / 参考資料: Cursor pstack's [create-verification-skill](https://github.com/cursor/plugins/blob/main/pstack/skills/create-verification-skill/SKILL.md) and [maintain-verification-skill](https://github.com/cursor/plugins/blob/main/pstack/skills/maintain-verification-skill/SKILL.md). This repository adapts those published workflows to its own documentation model; it is not a transcript of Lauren's talk. / 本仓库将上述公开流程适配到自己的文档模型，不是 Lauren 演讲原话。 / 公開された手順を本リポジトリの文書モデルに適応したもので、Laurenの講演の書き起こしではありません。

## Verification and Parallel Work / 验证与并行协作 / 検証と並行作業

Reuse an existing test or acceptance document or skill for the shared verification recipe: launch, identify the intended instance/build, check usable readiness, drive the actual user input path, assert results and relevant side effects, preserve evidence, and clean up only the run's scratch resources. Expected results come from requirements or an independent contract. Internal handlers, state assignments, or nearby input paths do not prove the requested path; mocks may isolate external boundaries without bypassing the chain under test. Record the tested object, instance/environment and mocked boundaries, actual path, results, evidence, cleanup, and uncovered scope. Reuse existing tools; no new CLI or service is mandatory. Prove one minimal loop before expanding parallel work that depends on that setup. Short-lived tools and non-software workflows use equivalent input/output and artifact checks.

共享验证方法复用已有测试、验收文档或 Skill，涵盖启动、目标实例与构建识别、实际就绪检查、真实用户输入路径、结果与相关副作用断言、证据保存和本轮临时资源清理。预期来自需求或独立契约；内部 handler、状态赋值或邻近输入路径不能证明目标路径，mock 可隔离外部边界但不能跳过被测链路。记录受测对象、实例与环境及 mock 边界、实际路径、结果、证据、清理和未覆盖范围。复用已有工具，不强制新 CLI 或服务；扩大依赖该环境的并行工作前先走通一个最小闭环。短时工具或非软件流程使用对应的输入输出和产物检查。

共有の検証手順は既存のテスト・受け入れ文書やSkillに置き、起動、対象インスタンスとビルドの識別、利用可能な状態の確認、実際のユーザー入力経路、結果と副作用の検証、証拠保存、今回の一時リソースの終了処理を扱います。期待結果は要件や独立した契約から定めます。内部ハンドラ、状態の代入、近い入力経路では対象経路を証明できません。mockで外部境界を分離できても、検証対象の経路を飛ばしてはいけません。対象、インスタンスと環境・mock境界、実際の経路、結果、証拠、終了処理、未検証範囲を記録します。既存ツールを再利用し、新しいCLIやサービスを強制しません。同じ環境に依存する並行作業を拡大する前に、最小限の一巡を確認します。短時間のツールやソフトウェア以外の工程では対応する入出力・成果物を検証します。

Real-entry requirements concern claims of user-journey coverage. Unit tests may call internal logic and use appropriate doubles; they do not replace real journey acceptance. / 真实入口要求针对用户旅程覆盖的声明，单元测试仍可调用内部逻辑或使用适当替身，但不能替代真实旅程验收。 / 実際の入口の要件はユーザーの操作手順の検証に関するものです。単体テストでは内部ロジックや適切なテストダブルを使えますが、実際の操作の受け入れ検証を代替しません。

A delivery task may contain parallel subtasks. In the task-package version, existing `owner` coordinates and integrates unless delegated in the plan; the only optional metadata addition, `workItems`, links an existing section or index when useful. Subtask progress lives in its own record; task metadata remains authoritative for overall status. Designated writers maintain shared summaries, contracts, and feature maps. Workers update assigned outputs, records, and separate events; handoffs transfer writing and resource ownership. Isolated branches may touch the same logical file, but also isolate runtime data/resources, coordinate shared contracts, and verify the integrated revision. Separate branch passes do not prove integrated success. Single-executor work omits subtask records and extra roles; no second board or scheduler is required. Prompts do not guarantee any particular number of running agents.

同一交付任务可以含并行子任务。任务包版沿用 `owner` 负责总体协调与集成（委派写在方案中）；唯一新增的可选元数据 `workItems` 按需引用已有章节或索引。子任务进展以自己的记录为准，任务元数据仍是总体状态母本。共享摘要、契约和功能地图由指定维护者更新。执行者维护分配的输出、记录和独立事件，转交时交接写入及资源所有权。隔离分支可修改同一逻辑文件，但运行数据和资源也需隔离；公共契约先协调，集成版本再验证，各分支分别通过不代表集成通过。单执行者省略子任务记录和额外角色，不增第二套看板或调度器；提示词不保证任何特定 Agent 并发数量。

同じ納品タスク内に並行する子タスクを持てます。タスクパッケージ版では既存の `owner` が全体の調整と統合を担い、委任は計画に記載します。追加する任意メタデータは `workItems` だけで、必要な場合に既存の節や索引を参照します。子タスクの進捗は各記録、全体の状態はタスクメタデータを正本とします。共有の要約、契約、機能マップは指定担当者が更新します。実行者は割り当てた出力・記録・個別イベントを管理し、引き継ぎでは書き込みとリソースの担当も渡します。分離したブランチで同じ論理ファイルを変更できますが、実行データとリソースも分離し、共有契約を調整して統合リビジョンを検証してください。各ブランチの合格だけでは統合後の合格になりません。単独作業では子タスク記録と追加役割を省略でき、別のボードやスケジューラは不要です。プロンプトは特定数のAgentの同時稼働を保証しません。

Example only / 仅为示例 / 例示のみ:

```text
T42: Save configuration / 保存配置 / 設定保存
owner C: shared contract + overall status + integration
  API/A: isolated branch and test data; implement the agreed interface
  UI/B: isolated branch and profile; consume that same interface
  TEST/V: prepare checks in parallel; run the real journey after integration
C integrates -> V checks save + reopen + persistence on the integrated revision
```

Verification record template, not an executed result / 验证记录模板，未执行 / 未実行の検証記録テンプレート:

```text
case: T42/save-config-persistence
object / instance / environment: <revision or build or tree fingerprint; instance; mocks>
actual path: <real input steps used, including reopen if applicable>
expected / actual / side effects: <requirement or contract; observations; persistence check>
status: not-run
evidence / cleanup / uncovered: <action and assertion paths; owned-resource cleanup; gaps>
```

Prefer existing type, lint, dependency, test, CI, or production quality checks for critical constraints. Repeated failures trigger a targeted review of their shared cause and the smallest verifiable structural or tooling improvement, within authorization; they do not authorize unlimited refactoring. / 关键约束优先落到已有类型、lint、依赖、测试、CI 或生产质量检查；反复失败触发共因和最小可验证结构或工具改进的针对性审查，实施受授权范围约束，不自动授权无限重构。 / 重要な制約には既存の型・lint・依存・テスト・CI・制作上の品質検証を優先します。失敗が繰り返される場合は共通原因と最小限の検証可能な構造・ツールの改善を対象を絞って見直し、許可範囲内で実施します。無制限のリファクタリングは許可しません。

Further references / 补充参考 / 追加参考: [pstack orchestration](https://github.com/cursor/plugins/blob/main/pstack/skills/poteto-mode/playbooks/orchestrate.md), [verification-skill-example](https://github.com/poteto/verification-skill-example/blob/main/README.md). The latter is fictional and omits its driver CLI; use it as a structural example, not an installable tool. / 后者是虚构示例，未附驱动 CLI，仅参考结构，不作为可安装工具。 / 後者は架空の例で駆動CLIを含みません。構造の参考であり、インストール可能なツールではありません。

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
