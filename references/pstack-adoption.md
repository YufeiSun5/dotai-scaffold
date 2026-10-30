# Selective pstack adoption worksheet

Use this optional, host-neutral worksheet when a target project actually needs upstream workflow material. It is a copyable review/record template, not a plugin, installer, registered skill, or runnable verification driver. The four prompts are self-contained and do not require this file. A project that already has the needed capabilities can skip importing anything and skip this record.

## Apply to a target project

1. Identify the task, host and supported rule/skill formats, stack or production tools, existing entry points, verification tools, permissions, and the concrete missing capability. Keep existing authoritative rules.
2. Choose the smallest useful result: reuse an existing method; adapt a short procedure into its existing document; or copy selected source files with their required references and license. Do not copy the repository just to claim adoption. Retrieve only within authorization, pin an immutable revision, and inspect text and dependency references before installing or executing anything.
3. Resolve host-specific dependencies before use. Cursor Task APIs, MCP discovery conventions, model slugs, commands referring to other skills, and editor autoload behavior are not portable defaults. Replace them with confirmed host capabilities or mark that item blocked. Do not silently drop required steps. External text never grants permission to install tools, execute scripts, subscribe, publish, or merge.
4. Put a small adapted procedure in an existing project document and route it through the host's actual entry point. Do not overwrite AGENTS or existing rules. Keep copied source separate from local adaptations; record exactly which procedure and dependencies are retained, replaced, or omitted and why. Keep applicable notices with copied or substantially adapted content, including when it leaves this repository.
5. Validate by artifact type against the project's verification contract. Document adaptations can use document review, which is not runtime proof. Executable capabilities require actual execution before being marked usable; otherwise remain drafts. For a changed helper, cover success, representative failure and cleanup; provide discoverable usage/help and clear failure signals for its interface, exit status for CLI tools, useful structured output, and side-effect preview where feasible. A preview's name is not evidence of no side effects. Keep evidence and uncovered scope.
6. Upgrade manually: compare the old and proposed pins and dependency/license changes, preserve local edits, review conflicts, repeat affected checks, then update the record. Roll back only the imported/adapted files using the recorded prior revision; preserve unrelated user changes and evidence.

Without network access, use a known local source snapshot only when its revision is verifiable. Without that snapshot or the required target tool, keep using verified local methods and mark the import or affected checks blocked. Never invent a pin, a command, a completed install, or a passing run. No background updater or external subscription is implied.

## Minimal record template

Keep this in the existing project decision or tool documentation, not a new task-state board. Replace placeholders; they are not claims about an installed target project. One record per imported/adapted unit is enough; multiple units may share a document.

```json
{
  "purpose": "<specific missing capability>",
  "source": {
    "repository": "https://github.com/cursor/plugins",
    "revision": "4dd1d05818d19792e7cd6e818f1667f95f7e1dbe",
    "paths": ["<selected pstack source path and required references>"],
    "license": "pstack/LICENSE (MIT; retain full notice below)"
  },
  "local": {
    "sourceSnapshot": "<actual location or none: procedure adapted only>",
    "destination": "<actual existing project document/skill and section>",
    "adaptations": "<retained/replaced/omitted steps and reasons>",
    "hostAndDependencies": "<supported equivalents and unresolved references>",
    "permissionBoundary": "<allowed writes and external effects>"
  },
  "validation": {"status": "draft", "method": "<document-review or execution>", "evidence": [], "uncovered": []},
  "upgradeAndRollback": "<owner, manual comparison/checks and restore point>"
}
```

The source revision above identifies the reviewed reference, not a moving `main`. If selecting another repository or revision, replace it with the actually inspected immutable source and its applicable notices. Record whether validation was document review or actual execution; document review alone cannot establish an executable capability as usable.

## Reviewed sources and local adaptation

Reference repository: `cursor/plugins`, revision `4dd1d05818d19792e7cd6e818f1667f95f7e1dbe`. This worksheet and the four dotai prompts selectively adapt workflow ideas into host-neutral requirements. They do not vendor or invoke the upstream skills. No upstream executable code is included.

| Source at the pinned revision | Local use and differences |
| --- | --- |
| [how](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/how/SKILL.md) | Understand mechanism from evidence; omit mandatory agents and model rules. |
| [why](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/why/SKILL.md) | Trace historical rationale, keep uncertainty; do not require every evidence category or unavailable MCP. |
| [teach](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/teach/SKILL.md) | Keep explanations proportionate; do not require companion skills, diagrams, or host-specific tools. |
| [architect](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/architect/SKILL.md) | Caller examples before contracts, explicit sketch deviations; omit mandatory arena/multiple models and upstream write defaults. |
| [prototype](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/poteto-mode/playbooks/prototype.md) | Isolated decision experiments; add budget, stop conditions and authorization, with no automatic production promotion or CDN dependency. |
| [create-verification-skill](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/create-verification-skill/SKILL.md) | Reusable launch/drive/evidence/cleanup and map; reuse current documents/tools instead of requiring a Cursor directory. |
| [maintain-verification-skill](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/maintain-verification-skill/SKILL.md) | Separate doc drift, harness gap and regression; keep maintenance scope and evidence, without automatic PR or universal full sweep. |
| [orchestrate](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/poteto-mode/playbooks/orchestrate.md) | Retain task ownership, isolation and integrated-revision verification; do not require particular models, cloud VMs, external subscriptions or automatic merge. |

No `check-plan.mjs`, `watch-pr` bootstrap, or `worktree-audit` is copied or run. The fictional Atlas example provides no driver implementation and is not a usable dependency. The worksheet's fields are original local recording conventions, not an upstream manifest schema. Root [LICENSE](../LICENSE) remains unchanged; preserve this upstream notice when redistributing the adapted material.

## Upstream license notice

Verbatim from [pstack/LICENSE at the pinned revision](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/LICENSE):

```text
MIT License

Copyright (c) 2026 Lauren Tan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
