# Feedback Research Report — GitHub Copilot for JetBrains IDEs
**Report Date:** March 9, 2026
**Period Covered:** February 9 – March 9, 2026 (recent month)
**Sources:** GitHub Issues ([microsoft/copilot-intellij-feedback](https://github.com/microsoft/copilot-intellij-feedback)) + [JetBrains Marketplace Reviews](https://plugins.jetbrains.com/plugin/17718-github-copilot/reviews)

---

## Executive Summary

The plugin is experiencing a **severe user-satisfaction crisis**. Across both feedback channels, the dominant sentiment is overwhelmingly negative, driven by persistent stability, UI, and performance bugs. The average marketplace rating over the past month is **1.3 / 5** (83 reviews), and GitHub received **261 open + 86 closed** issues in the same period. The top pain points are IDE freezes/crashes, truncated chat output, poor scrolling/UI, and feature parity gaps vs. VS Code.

---

## 1. GitHub Issues — Overview

| Metric | Count |
|---|---|
| Open issues (since Feb 9) | 261 |
| Closed issues (since Feb 9) | 86 |
| Total fetched for analysis | 186 |

### 1.1 Type Distribution

| Type | Count |
|---|---|
| Bug | 148 (80%) |
| Feature Request | 29 (16%) |
| Docs / Question / Regression | 3 each |

> **80% of all issues are bug reports**, underscoring the stability-first narrative.

### 1.2 Component Breakdown

| Component | Issues | Share |
|---|---|---|
| Chat | 42 | 23% |
| Agent Mode | 42 | 23% |
| UI | 30 | 16% |
| Authentication | 23 | 12% |
| Performance | 14 | 8% |
| Model Selection | 13 | 7% |
| Context | 10 | 5% |
| Completions | 9 | 5% |
| MCP | 4 | 2% |
| Remote Dev | 1 | <1% |

**Chat and Agent Mode** each represent nearly a quarter of all issues. Authentication (12%) is surprisingly high, primarily OAuth/login failures and corporate proxy issues.

### 1.3 Priority Distribution

| Priority | Count |
|---|---|
| Critical | 13 |
| High | 29 |
| Medium | 68 |
| Low | 49 |

### 1.4 Top GitHub Issues — Critical/High Priority

| # | Title | Component | Priority |
|---|---|---|---|
| 1453 | Plugin crash — chat sidepanel blank (NoClassDefFoundError) | Agent Mode | Critical |
| 1452 | Rider hangs frequently when Copilot enabled (57s EDT freeze) | Performance | High |
| 1454 | Remains of inline proposed edits stuck on screen | UI | High |
| 1449 | Claude Opus 4.6 returns missing characters in words | Chat | High |
| 1448 | Chat throws 403 error | Chat | High |
| 1447 | Proxy authentication not working (NTLM) | Authentication | High |
| 1443 | Cannot stop agent when it loops (red button disappears) | Agent Mode | High |
| 1432 | Plugin incompatible with latest IntelliJ update | UI | High |
| 1431 | Formatting swallows characters (Claude) | Chat | High |
| 1430 | Corrupted text in Copilot Chat (Opus 4.6) | Chat | High |
| 1428 | Agent requests fail with 502 errors | Agent Mode | High |
| 1427 | MCP OAuth with Azure EntraID fails | MCP | High |

### 1.5 Top Feature Requests

| # | Title | Component |
|---|---|---|
| 1451 | Export / Import chat history (Markdown/JSON) | Chat |
| 1441 | Support project-local MCP configuration (workspace-scoped) | MCP |
| 1437 | Allow paste images and files from disk to chat | Chat |
| 1433 | Terminal auto-approve for wrapper commands | Agent Mode |
| 1423 | Quota Usage without rounding (show x of y instead of %) | Model Selection |
| 1421 | Azure Responses API endpoint not supported (gpt-5.1-codex-max) | Model Selection |

---

## 2. JetBrains Marketplace Reviews — Overview

| Metric | Value |
|---|---|
| Total reviews (last month) | 83 |
| Average rating | **1.3 / 5** |
| Total downloads (all time) | 40.3M |

### 2.1 Rating Distribution

```
5 ★ :   4  ( 5%)  ████
4 ★ :   3  ( 4%)  ███
3 ★ :   3  ( 4%)  ███
2 ★ :  11  (13%)  ███████████
1 ★ :  47  (57%)  ███████████████████████████████████████████████
0 ★ :  15  (18%)  ███████████████
```

**75% of reviews are 0–1 stars.** Only 8% (7 reviews) are 4–5 stars.

### 2.2 Common Themes Extracted from Reviews

| Theme | Mentions | % of Reviews |
|---|---|---|
| Crash / broken / unusable | 22 | 27% |
| UI / scrolling issues | 22 | 27% |
| Agent mode issues | 16 | 19% |
| Freeze / hang / unresponsive | 13 | 16% |
| Rate limits | 10 | 12% |
| Performance / slow | 9 | 11% |
| Truncated / incomplete output | 7 | 8% |
| Model parity with VS Code | 6 | 7% |
| Terminal output issues | 5 | 6% |
| Auth / login failures | 3 | 4% |

### 2.3 Notable Marketplace Comments (Curated)

**Stability / Crashes:**
> *"Full of persistent bugs. After 6 months of use, I'm disappointed by the consistent technical issues: terminal outputs not returning, frequent chat history loss, scrolling issues, 10-20 second IDE freezes."* — niko.riccitelli (1★)

> *"Since installing the latest version (1.5.66-243), the entire IDE (Rider) crashes almost every time."* — Code.Nascher (1★)

> *"crashes every 2 minutes when using the IDE."* — henning.sprang (1★)

**Truncated Output (Widespread in Feb 11–14):**
> *"The generated code is incomplete, and the code block cannot copy. After two updates the issues remain."* — shouruyang (1★)

> *"As of today, Github Copilot only displays suggestions that are interrupted in the middle of the code. The tool is no longer usable."* — info (0★)

**UI / Scrolling:**
> *"Scrolling chat window using touchpad on macOS is the ultimately worst out there I've ever seen. Completely freezes the IDE when an agent runs."* — Serhii Hultiaiev (1★)

> *"Scrolling and formatting is very bad."* — kumohamm (1★)

**Feature Parity:**
> *"I really wonder why GPT 5.3-codex and Gemini 3.1 Pro are still not available in Android Studio while they can be accessed in VS Code long ago?"* — Yuchen Liu (3★)

> *"Compared to VS Code version this plugin is a disaster. Constant issues, agent mode does not work when doing remote dev, models selection disappears."* — piotr (0★)

**Positive (rare):**
> *"Overall, it provides a great experience. I get especially impressive results with the Sonnet and Opus models."* — Enes Oscar (5★)

> *"I have a very good experience with it. Writing tests, writing documentation, altering code. Currently a very productive partner."* — demawi (5★)

---

## 3. Cross-Source Analysis — Key Findings

### 3.1 Converging Pain Points (Both Sources)

1. **IDE Freezes & Performance Degradation** — The single most impactful issue. Multiple GitHub issues report 10–57 second EDT freezes, and 16% of marketplace reviewers mention freezing. Directly attributed to the Copilot plugin by users who confirm the problem disappears when the plugin is disabled.

2. **Chat Output Corruption / Truncation** — A wave of reports (especially v1.5.64 around Feb 11) about code blocks being cut off, incomplete, or displaying corrupted markdown. Issue clusters: #1352, #1354, #1356, #1349, #1345. Multiple marketplace reviews independently confirm.

3. **Agent Mode Instability** — The stop button disappearing during loops (#1443), inability to read terminal output, and mode confusion (Agent requests landing in Ask mode). 16 marketplace reviewers specifically mention agent issues.

4. **VS Code Feature Parity Gap** — Model selection (GPT 5.3-codex, Gemini 3.1 Pro missing: #1439, #1416), workspace MCP configs, image pasting, and BYOK Azure Responses API (#1421) all work in VS Code but not JetBrains.

5. **Character Swallowing / Rendering Bug (Claude Opus 4.6)** — Multiple independent reports (#1431, #1449, #1445) of characters being dropped in chat output specifically with Claude models.

### 3.2 Emerging Concerns

- **Rate Limit Frustration** — 10 marketplace reviews and multiple issues about hitting rate limits on Pro plans, wasting premium requests on failed/incomplete generations.
- **Authentication Failures** — OAuth login failing (#1434), NTLM proxy issues (#1447), Enterprise login broken in marketplace reviews.
- **Plugin Compatibility Breakage** — Users report the plugin not working after JetBrains IDE updates (#1432, #1453), indicating insufficient compatibility testing against new IDE builds.

### 3.3 Sentiment Trajectory

The negative sentiment is **intensifying**, not stabilizing. Reviewers who had previously been positive are now leaving 1-star updates. Multiple users explicitly state they are switching to alternatives (Cursor, JetBrains AI, etc.) or seriously considering it.

---

## 4. Recommendations

1. **Freeze/Performance — Highest Priority:** The `ComponentTreeWatcher` recursive registration freeze (#1452) and EDT blocking in `CopilotChatSessionPanel.showContent` must be resolved immediately. These regressions are the #1 driver of negative reviews.

2. **Chat Rendering Engine:** The truncation and character-swallowing bugs need a systematic fix. Multiple versions have shipped with rendering regressions.

3. **Model Parity:** Ship GPT 5.3-codex and Gemini 3.1 Pro support for JetBrains. The gap is highly visible and frustrating to paying users.

4. **Agent Mode Reliability:** Terminal output capture, stop-button persistence, and mode switching need hardening.

5. **Release Quality Gate:** Since v1.5.64 (Feb 11 timeframe), every release has generated a spike in negative feedback. Consider adding integration tests against multiple JetBrains IDE versions before publishing.

---

## 5. Raw Data Files

| File | Description |
|---|---|
| `raw_github_issues.json` | 186 GitHub issues (open + closed) since Feb 9, 2026 — number, title, state, labels, user, body summary |
| `raw_marketplace_reviews.json` | 83 JetBrains Marketplace reviews since Feb 9, 2026 — rating, date, author, full comment |

---

*Report generated automatically from GitHub MCP API and JetBrains Marketplace REST API.*
