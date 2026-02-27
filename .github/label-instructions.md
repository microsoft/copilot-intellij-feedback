# GitHub Labels System for Copilot IntelliJ Feedback

This document describes the label system for the microsoft/copilot-intellij-feedback repository.

## 📋 Quick Reference

### Essential Labeling Rules
1. **Every issue must have exactly one label from each category**: Type + Component + Priority
2. **Only one label per category** — do not apply multiple labels from the same category
3. **Do NOT apply `needs more info`** or any labels with similar meaning — leave this for humans to apply

---

## 🏷️ Label Categories

### 1. Priority Labels (Severity)

Apply exactly **one** priority label per issue.

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

Apply exactly **one** component label per issue. Choose the **primary** component most relevant to the issue.

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
- Slow completions → `component: performance` (choose the most impactful component)
- Can't login → `component: authentication`

---

### 3. Type Labels (Nature of Issue)

Apply exactly **one** type label per issue.

| Label | Description | Color |
|-------|-------------|-------|
| `bug` | Something is broken | 🔴 Red |
| `feature-request` | New feature or enhancement | 🔵 Blue |
| `type: regression` | Previously worked, now broken | 🔴 Red |
| `type: docs` | Documentation needed | 📘 Blue |
| `type: question` | User question | 💜 Purple |

---

## 📝 Notes

- Each issue receives exactly **three labels**: one Type, one Component, one Priority
- If an issue spans multiple components, choose the single most relevant one
- Labels should be updated as the issue evolves (e.g., type or priority changes)
