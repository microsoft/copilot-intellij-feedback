# IDE-Specific Feedback Report — GitHub Copilot for JetBrains
**Report Date:** March 9, 2026
**Period Covered:** February 9 – March 9, 2026
**Sources:** GitHub Issues (186 analyzed) + JetBrains Marketplace Reviews (83 analyzed)

---

## Summary Matrix

| IDE | GitHub Issues | Open | Closed | Bugs | Feature Requests | Marketplace Reviews | Avg Rating |
|---|---|---|---|---|---|---|---|
| **IntelliJ IDEA** | 66 | 33 | 33 | 57 | 6 | 6 | 2.5 |
| **PyCharm** | 18 | 10 | 8 | 17 | 1 | 4 | 1.2 |
| **Rider** | 17 | 6 | 11 | 16 | 0 | 2 | 2.5 |
| **PhpStorm** | 17 | 4 | 13 | 16 | 2 | 2 | 1.5 |
| **WebStorm** | 6 | 4 | 2 | 6 | 0 | 2 | 0.5 |
| **CLion** | 5 | 4 | 1 | 5 | 0 | 0 | — |
| **Android Studio** | 5 | 1 | 4 | 4 | 0 | 2 | 2.0 |
| **RustRover** | 2 | 1 | 1 | 2 | 0 | 0 | — |
| **GoLand** | 2 | 1 | 1 | 2 | 0 | 0 | — |
| **DataGrip** | 1 | 1 | 0 | 1 | 0 | 2 | 0.5 |
| **DataSpell** | 0 | 0 | 0 | 0 | 0 | 1 | 1.0 |
| *(IDE not specified)* | 53 | — | — | — | — | 62 | 1.2 |

> **Note:** 53 GitHub issues and 62 marketplace reviews did not specify a particular IDE. Many generic issues (UI, scroll, truncation) likely affect all IDEs equally.

---

## IntelliJ IDEA (66 issues, 6 reviews)

**The largest share by far** — 36% of all IDE-attributable issues. This reflects its market share as the flagship JetBrains product.

### Component Hotspots
| Component | Count |
|---|---|
| Chat | 15 |
| Agent Mode | 14 |
| UI | 12 |
| Authentication | 10 |
| Performance | 8 |
| Model Selection | 5 |

### Unique / IDE-Specific Patterns
- **7 critical issues** — more than any other IDE, including login failures with custom authentication providers (#1260, #1235), an infinite "Error report" modal loop (#1336), and inability to accept inline completions (#1265)
- **Authentication is disproportionately high** (10 issues) — OAuth failures, enterprise login, and custom auth provider support are heavily reported here since IntelliJ IDEA has the largest enterprise user base
- **BYOK / Azure integration issues** (#1421) specifically affect enterprise IntelliJ users deploying their own models

### Key Issues
| # | Priority | Title |
|---|---|---|
| 1339 | Critical | Not able to use GitHub Copilot |
| 1336 | Critical | Infinite "Error report" modal loop |
| 1265 | Critical | Can't accept inline completions |
| 1260 | Critical | IntelliJ does not recognize custom auth provider |
| 1448 | High | Chat throws 403 error |
| 1421 | High | Azure Responses API not supported (BYOK) |

### Marketplace Sentiment
One reviewer called it *"by far the worst agent experience I've had with any of the tools"* (1★). However, IntelliJ also received the most positive reviews (two 5★), suggesting the experience is inconsistent rather than universally broken.

---

## PyCharm (18 issues, 4 reviews)

### Component Hotspots
| Component | Count |
|---|---|
| Chat | 6 |
| UI | 4 |
| Agent Mode | 4 |
| Authentication | 3 |
| MCP | 2 |

### Unique / IDE-Specific Patterns
- **MCP OAuth integration broken** (#1390, #1427) — PyCharm users are the primary reporters of MCP server OAuth failures with Azure EntraID
- **UI freeze on chat open** — Multiple marketplace reviewers specifically mention PyCharm hanging when opening the Copilot chat panel, with one allocating 8GB RAM and still experiencing hangs
- **Terminal delay in WSL** — Not unique to PyCharm but reported here

### Key Issues
| # | Priority | Title |
|---|---|---|
| 998 | Critical | "An error occurred while processing your request" |
| 1427 | High | MCP OAuth with Azure EntraID fails |
| 1327 | High | Code generation cut off when using selected text |
| 1288 | High | Infinite terminal loop — keeps asking same questions |

### Marketplace Sentiment
Average rating **1.2/5**. One reviewer said PyCharm instability is *"a good enough reason at this point for switching from PyCharm to VS Code altogether"* (2★). The scrolling jitter on macOS M4 hardware is specifically mentioned.

---

## Rider (17 issues, 2 reviews)

### Component Hotspots
| Component | Count |
|---|---|
| UI | 5 |
| Chat | 4 |
| Agent Mode | 2 |
| Completions | 2 |
| Performance | 1 |

### Unique / IDE-Specific Patterns
- **57-second EDT freeze** (#1452) — The most severe performance report across all IDEs, with a stack trace pointing to `CopilotChatSessionPanel.showContent` → `ComponentTreeWatcher.register` recursive calls. This is a **Rider-specific** freeze pattern
- **Chat UI rendering fails until tab switch** (#1349) — Code blocks are invisible until the user switches tabs and back. This is reported as Rider-specific, with 5 comments and confirmed reproducibility
- **Model parity complaint** (#1439) — Rider users specifically note GPT 5.3-codex is missing
- **Tooltip overlay appears on top of other applications** (#1412) — A Rider-specific UI bug where the "changes" tooltip renders outside the IDE window

### Key Issues
| # | Priority | Title |
|---|---|---|
| 1265 | Critical | Can't accept inline completions |
| 1452 | High | Rider hangs frequently (57s freeze) |
| 1320 | High | Code block stops after 20-25 lines |
| 1349 | Medium | Chat UI invisible until tab switch |
| 1412 | Medium | Changes tooltip appears on top of any application |

### Marketplace Sentiment
Mixed: one reviewer says *"the entire IDE (Rider) crashes almost every time"* with v1.5.66 (1★), while another gives it 4★ and says *"I use this A LOT... the JetBrains implementation isn't half bad."*

---

## PhpStorm (17 issues, 2 reviews)

### Component Hotspots
| Component | Count |
|---|---|
| Agent Mode | 4 |
| Chat | 4 |
| Context | 2 |
| UI | 2 |

### Unique / IDE-Specific Patterns
- **Plugin crash on startup — blank chat sidepanel** (#1453) — `NoClassDefFoundError: org/jetbrains/plugins/terminal/TerminalOptionsProvider` causes the entire chat panel to go blank. This is PhpStorm-specific because PhpStorm bundles a different terminal plugin configuration
- **PhpStorm freeze on EDT** (#1237) — A separate, older critical freeze issue specific to PhpStorm
- **"Edit" mode crash** (#1383) — Sending a prompt in Edit mode throws `IllegalArgumentException: Unsupported chat mode: Edit`, destroying the user's prompt without saving it
- **Project isolation missing** (#1060) — Agent-mode terminal commands execute from the wrong project directory

### Key Issues
| # | Priority | Title |
|---|---|---|
| 1453 | Critical | Plugin crash — chat blank (NoClassDefFoundError) |
| 1237 | Critical | Plugin causes PhpStorm to freeze |
| 1454 | High | Inline proposed edits stuck on screen |
| 1342 | Medium | Ask mode bug — response not fully visible |
| 1383 | Low | Edit mode throws exception, destroys prompt |

### Marketplace Sentiment
*"Great Idea, Rough Execution"* (2★) — a detailed review listing prompt loss, mode confusion, and workaround-heavy workflows. Login failure also reported for paid subscriptions.

---

## WebStorm (6 issues, 2 reviews)

### Component Hotspots
Agent Mode (3), Model Selection (2), Completions (1), Authentication (1), Chat (1)

### Unique / IDE-Specific Patterns
- **Complete freeze on chat icon click** — Marketplace reviewer reports *"the whole WebStorm application freezes indefinitely"* when clicking the Copilot Chat icon (1★)
- **Context menu/chat menu missing entirely** — Another reviewer reports the Copilot context menu and chat menu are completely absent after an update (0★)
- **NES (Next Edit Suggestions) doesn't clear** (#1386) — Completion suggestions persist after no interaction, specific to WebStorm behavior

### Key Issues
| # | Priority | Title |
|---|---|---|
| 1350 | High | Rate limit errors (premium/Claude) |
| 1182 | High | Extreme terminal output delay in WSL |
| 1372 | Medium | SSL certificate error ("unable to get local issuer certificate") |
| 1341 | Medium | Copying from inline chat doesn't work |

---

## CLion (5 issues, 0 reviews)

### Unique / IDE-Specific Patterns
- **502 errors on agent requests** (#1428) — Repeated server-side failures, tested with Sonnet 4.5/4.6
- **Login failures** (#1367, #1434) — Two separate CLion users unable to sign in, one via CLion/Gateway specifically
- All 5 issues are **currently open** (80% unresolved rate — worst among all IDEs)

### Key Issues
| # | Priority | Title |
|---|---|---|
| 1428 | High | Agent requests repeatedly fail with 502 |
| 1422 | Medium | Cursor-up in chat deletes unsent request |
| 1367 | Medium | Unable to login via CLion/Gateway |

---

## Android Studio (5 issues, 2 reviews)

### Unique / IDE-Specific Patterns
- **Plugin blocks entire IDE from working** (#1331, critical) — The Copilot plugin reportedly prevents Android Studio from functioning at all
- **Model parity gap is particularly frustrating** — Marketplace reviewer asks *"why GPT 5.3-codex and Gemini 3.1 Pro are still not available in Android Studio while they can be accessed in VS Code long ago?"*
- **Code suggestions broken for older Android Studio versions** — "Code suggestions doesn't work for Android Studio Panda 1" (marketplace, 1★)
- **`user.home` platform issue** (#1419) — Home directory path resolution differs on Android Studio, causing configuration failures

### Key Issues
| # | Priority | Title |
|---|---|---|
| 1340 | Critical | Update to 1.5.64 — incomplete/truncated output |
| 1331 | Critical | Plugin blocks Android Studio entirely |
| 1345 | Medium | Full code responses not shown |

---

## Minor IDEs (RustRover, GoLand, DataGrip, DataSpell)

### RustRover (2 issues)
- **Corrupted chat text with Opus 4.6** (#1430, high priority) — Missing characters in output, confirmed with screenshots
- **Prompt crashes, 20 minutes of work lost** (#1196) — Initial request crashes and the entire prompt disappears

### GoLand (2 issues)
- **Gradual degradation from semantic search to grep** (#1446) — Agent stops using intelligent search and falls back to grep, reported specifically in GoLand

### DataGrip (1 issue, 2 reviews)
- **Completely broken with current DataGrip version** — Both marketplace reviewers report total breakage; plugin crashes on startup in DataGrip 2025.3.5
- **Oracle DB line number incorrect** (#1380) — DataGrip-specific bug with database line numbers

### DataSpell (0 issues, 1 review)
- **Freezes DataSpell** — Marketplace reviewer reports it *"freezes DataSpell completely when trying to open Copilot"*

---

## Cross-IDE Themes

### Issues That Affect ALL IDEs
These were heavily reported without IDE specificity and are platform-agnostic:
- Chat output truncation / incomplete code blocks
- Scrolling/UI jitter in chat panel
- Rate limit errors on Pro plans
- Agent mode looping without ability to stop
- Character swallowing with Claude models

### IDE-Specific Patterns Worth Investigating

| Pattern | Affected IDEs | Others Unaffected |
|---|---|---|
| `NoClassDefFoundError: TerminalOptionsProvider` crash | PhpStorm | Others |
| 57-second EDT freeze in `ComponentTreeWatcher` | Rider | Others |
| Chat panel invisible until tab switch | Rider | Others |
| Plugin blocks IDE entirely | Android Studio | Others |
| Plugin crash on startup | DataGrip, PhpStorm | Others |
| Context menu / chat menu missing | WebStorm | Others |
| MCP OAuth with Azure EntraID | PyCharm | Others (less reported) |
| `user.home` path resolution | Android Studio | Others |

### IDE Compatibility Testing Gap
The data suggests insufficient testing across the IDE matrix. PhpStorm and DataGrip have `NoClassDefFoundError` crashes due to missing terminal plugin classes. Android Studio has unique path resolution issues. The plugin appears to be primarily tested against IntelliJ IDEA, with other IDEs encountering integration-specific regressions.

---

## Raw Data

| File | Description |
|---|---|
| `raw_ide_breakdown.json` | Structured JSON: per-IDE issues and reviews with stats |
| `raw_github_issues.json` | All 186 GitHub issues (from general report) |
| `raw_marketplace_reviews.json` | All 83 marketplace reviews (from general report) |

---

*Report generated from GitHub MCP API and JetBrains Marketplace REST API data.*
