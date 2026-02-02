# GitHub Labels System for Copilot IntelliJ Feedback

This document describes the comprehensive label system for the microsoft/copilot-intellij-feedback repository.

## 📋 Quick Reference

### Essential Labeling Rules
1. **Every issue must have**: Type + Component + Priority
2. **Bug issues must have**: Status + Impact
3. **Platform-specific issues must have**: Appropriate platform label
4. **Issues needing info must have**: `status: needs-more-info`

---

## 🏷️ Label Categories

### 1. Priority Labels (Severity)

| Label | Description | When to Use |
|-------|-------------|-------------|
| `priority: critical` 🔴 | Blocking issues, crashes, data loss | Users cannot use the product at all |
| `priority: high` 🟠 | Major functionality broken | Significant impact on productivity |
| `priority: medium` 🟡 | Notable issues with workarounds | Annoying but manageable |
| `priority: low` 🟢 | Minor issues, cosmetic | Small inconvenience |

**Examples:**
- Critical: #630 (Agent window not opening), #529 (Extreme CPU usage)
- High: File edit failures, message loss, authentication failures
- Medium: UI quirks, scrolling issues
- Low: Tooltip missing, button order inconsistency

---

### 2. Component Labels (Area of Impact)

| Label | Description |
|-------|-------------|
| `component: agent-mode` | Agent mode execution, tools, workflows |
| `component: chat` | Chat interface, messages, conversations |
| `component: completions` | Inline completions, ghost text, suggestions |
| `component: authentication` | Login, logout, auth providers, tokens |
| `component: mcp` | Model Context Protocol, custom tools |
| `component: ui` | User interface, layout, rendering |
| `component: performance` | CPU, memory, speed issues |
| `component: remote-dev` | Remote development, Gateway |
| `component: context` | File references, context management |
| `component: model-selection` | Model picker, availability |

**Usage Examples:**
- Agent crashes → `component: agent-mode`
- Chat messages disappear → `component: chat`
- Slow completions → `component: completions` + `component: performance`
- Can't login → `component: authentication`

---

### 3. Type Labels (Nature of Issue)

| Label | Description | Color |
|-------|-------------|-------|
| `bug` | Something is broken | 🔴 Red |
| `feature-request` | New feature or enhancement | 🔵 Blue |
| `type: regression` | Previously worked, now broken | 🔴 Red |
| `type: docs` | Documentation needed | 📘 Blue |
| `type: question` | User question | 💜 Purple |

---

### 4. Platform Labels (IDE-Specific)

| Label | Use When |
|-------|----------|
| `platform: intellij` | Issue only affects IntelliJ IDEA |
| `platform: pycharm` | Issue only affects PyCharm |
| `platform: phpstorm` | Issue only affects PhpStorm |
| `platform: rider` | Issue only affects Rider |
| `platform: datagrip` | Issue only affects DataGrip |
| `platform: android-studio` | Issue only affects Android Studio |
| `platform: clion` | Issue only affects CLion |
| `platform: all-ides` | Affects all JetBrains IDEs |

**Note:** Only use if the issue is specific to that IDE. Most issues affect all IDEs.

---

### 5. Status Labels (Workflow)

| Label | Meaning | Next Action |
|-------|---------|-------------|
| `status: needs-triage` | Just opened | Team to categorize and prioritize |
| `status: needs-more-info` | Incomplete report | User to provide details |
| `status: needs-reproduction` | Can't reproduce | User to provide repro steps |
| `status: confirmed` | Validated | Ready for development |
| `status: in-progress` | Being worked on | Developer working on fix |
| `status: blocked` | Dependency issue | Resolve blocker first |
| `status: ready-for-review` | Fix complete | Code review needed |
| `status: fixed-pending-release` | Fixed, not released | Wait for next release |

**Workflow:**
```
needs-triage → needs-more-info (if unclear)
             → confirmed (if valid)
             → in-progress
             → ready-for-review
             → fixed-pending-release
             → CLOSED
```

---

### 6. Impact Labels (User Impact)

| Label | Criteria |
|-------|----------|
| `impact: blocking` | Cannot use the product |
| `impact: high` | Major productivity loss |
| `impact: medium` | Annoying but manageable |
| `impact: low` | Minor inconvenience |

**Examples:**
- Blocking: Can't login, complete freeze
- High: Files not saving, messages lost
- Medium: Slow responses, UI glitches
- Low: Missing tooltip, cosmetic issue

---

### 7. Root Cause Labels (Technical)

| Label | Description |
|-------|-------------|
| `root-cause: threading` | Concurrency, race conditions, EDT violations |
| `root-cause: state-management` | State sync issues |
| `root-cause: network` | Network, proxy issues |
| `root-cause: file-system` | File I/O, permissions |
| `root-cause: multi-window` | Multi-project handling |
| `root-cause: ide-integration` | IDE API usage |

**When to use:** After investigation reveals the underlying cause.

---

### 8. Feature Area Labels (Specific Features)

| Label | Scope |
|-------|-------|
| `feature: inline-chat` | Inline chat in editor |
| `feature: terminal-integration` | Terminal commands |
| `feature: git-operations` | Git diff, commits |
| `feature: file-operations` | File read/write/edit |
| `feature: context-exclusion` | Content exclusion |
| `feature: session-management` | Chat sessions |
| `feature: notifications` | Error messages |

---

### 9. Special Labels

| Label | Purpose |
|-------|---------|
| `good-first-issue` | Easy for new contributors |
| `help-wanted` | Community help welcome |
| `duplicate` | Duplicate issue |
| `wontfix` | Will not address |
| `needs-design` | Architecture discussion needed |
| `breaking-change` | May break existing functionality |
| `security` | Security implications |

---

### 10. Effort Labels (Planning)

| Label | Estimated Work |
|-------|----------------|
| `effort: small` | < 1 day |
| `effort: medium` | 1-3 days |
| `effort: large` | > 3 days |
| `effort: epic` | Multiple iterations |

## 📝 Notes

- This label system was created based on analysis of 200+ open issues
- Labels use color coding for visual distinction
- Multiple labels can and should be used together
- Labels should be updated as issue evolves (e.g., status changes)
- Use label automation where possible (e.g., auto-add `status: needs-triage`)