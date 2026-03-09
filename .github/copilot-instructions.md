# Copilot Instructions — copilot-intellij-feedback

## Repository Purpose

This is a **feedback-only** repository for the GitHub Copilot Plugin for JetBrains IDEs. It contains no application source code — only issue templates, automation policies, and triage tooling. All work here revolves around issue management, labeling, and community engagement.

## Repository Structure

- `.github/ISSUE_TEMPLATE/` — Issue templates: `bug_report.yml` (structured YAML form) and `feature_request.md` (freeform markdown)
- `.github/policies/` — Automated issue/comment management rules (resourceManagement, issueCommentManagement, scheduler)
- `.github/workflows/stale.yml` — Stale issue bot (7-day inactivity → stale, 3-day → close; only targets `needs-more-info` issues)
- `.github/label-instructions.md` — Canonical label taxonomy and triage rules
- `.github/sla.md` — SLA evaluation criteria and escalation flow

## Labeling System (Critical Convention)

Every issue must receive **exactly three labels** — one from each category:

| Category | Labels |
|----------|--------|
| **Type** | `bug`, `feature-request`, `type: regression`, `type: docs`, `type: question` |
| **Component** | `component: agent-mode`, `component: chat`, `component: completions`, `component: authentication`, `component: mcp`, `component: ui`, `component: performance`, `component: remote-dev`, `component: context`, `component: model-selection` |
| **Priority** | `priority: critical` (blocking/crashes), `priority: high` (major breakage), `priority: medium` (workarounds exist), `priority: low` (cosmetic) |

- Choose the **single most relevant** component when an issue spans multiple areas
- **Never** apply `needs more info` via automation — that label is human-only
- New issues auto-receive `needs attention` and a greeting reply via policy

## Issue Lifecycle & Automation

1. **On open**: Auto-labeled `needs attention`, greeter reply posted
2. **Non-member comment**: `needs attention` added (if not already present); `needs more info` replaced with `needs attention`
3. **Member comment**: `needs attention` removed
4. **7 days idle** with `needs more info` (non-feature-request): Labeled `no recent activity`, warning comment posted
5. **3 days after stale warning**: Auto-closed
6. **SLA**: 7-day grace period → must have parent link and no `needs attention` label, else SLA violation

## SLA Evaluation

- **Exempt**: Issues with `need more info` or `need log` labels (match case-insensitively, including hyphenated variants)
- **Grace period**: 7 days from open or exempt-label removal
- **Good**: Has parent link AND no `needs attention` label
- **Violation**: Missing parent link OR has `needs attention` after grace period

## Feedback Sources

Users provide feedback through two channels:

1. **This repository** — Issues filed here using the bug report or feature request templates; this is the primary channel for detailed feedback and tracking
2. **JetBrains Marketplace reviews** — Ratings and comments at the [plugin review page](https://plugins.jetbrains.com/plugin/17718-github-copilot--your-ai-pair-programmer/reviews); when engaging with marketplace reviewers, encourage them to open an issue in this repository for detailed discussion and tracking

## Bug Report Template Fields

The bug template (`bug_report.yml`) collects: feedback source, plugin version, JetBrains IDE + version, platform info (`uname -a`), steps to reproduce, logs (link to [debug logging wiki](https://github.com/microsoft/copilot-intellij-feedback/wiki/Enable-debug-logging)), expected behavior, actual behavior, and additional info.

## When Editing This Repo

- Policy files in `.github/policies/` use the microsoft-github-policy-service schema — preserve `payloadType`, `isAction`, `hasLabel`, and permission-check structure
- The stale workflow only targets issues with `needs-more-info`; do not broaden without explicit approval
- Label names are exact-match in automations — any rename must be synchronized across all policy files, the stale workflow, and `label-instructions.md`
