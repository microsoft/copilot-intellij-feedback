# SLA Strategy for Copilot IntelliJ

This document defines the default SLA criteria for Copilot IntelliJ product.

## SLA Criteria

### Exempt Statuses (SLA automatically Good)

Issues with these labels are exempt from SLA checks because they are waiting on external input:

| Label | Description |
|-------|-------------|
| `need more info` | Waiting for reporter to provide additional information |
| `need log` | Waiting for reporter to provide logs or diagnostic data |

### Tolerance Period

Issues have a **7-day tolerance window** from the time they are opened (or from the time an exempt label is removed) before SLA conditions are enforced. During this grace period, the SLA status is always **GOOD**, giving assignees time to triage and address the issue.

### Required Conditions (for non-exempt issues)

For issues that are not exempt and have exceeded the 7-day tolerance period, **all** of these conditions must be met:

| Condition | Requirement | Rationale |
|-----------|-------------|-----------|
| Parent link | Must exist | Ensures issue is tracked in a larger work item or epic |
| No "need attention" label | Must NOT have this label | This label indicates the issue requires immediate action |

## Evaluation Flow

```
┌─────────────────────────────────────┐
│ Start: Evaluate Issue SLA           │
└─────────────────┬───────────────────┘
                  │
                  ▼
┌─────────────────────────────────────┐
│ Has "need more info" or "need log"? │
└─────────────────┬───────────────────┘
                  │
         ┌───────┴───────┐
         │ YES           │ NO
         ▼               ▼
┌─────────────┐  ┌─────────────────────┐
│ SLA: GOOD   │  │ Within 7-day        │
│ (Exempt)    │  │ tolerance window?   │
└─────────────┘  └─────────┬───────────┘
                           │
                  ┌────────┴────────┐
                  │ YES             │ NO
                  ▼                 ▼
           ┌───────────┐  ┌─────────────────────┐
           │ SLA: GOOD │  │ Check parent link   │
           │ (Grace)   │  │ and "need attention"│
           └───────────┘  └─────────┬───────────┘
                                    │
                           ┌────────┴────────┐
                           │                 │
                  Parent exists AND     Otherwise
                  no "need attention"
                           │                 │
                           ▼                 ▼
                    ┌───────────┐    ┌─────────────┐
                    │ SLA: GOOD │    │ SLA: VIOLATION│
                    └───────────┘    └─────────────┘
```

## Label Matching

Labels should be matched case-insensitively. Common variations to check:

- `need more info`, `needs more info`, `need-more-info`, `needs-more-info`
- `need log`, `needs log`, `need-log`, `needs-log`
- `need attention`, `needs attention`, `need-attention`, `needs-attention`

## Parent Link Detection

Check for parent links using:

1. GitHub sub-issues API (if available)
2. Issue body for "tracked by" or "parent" references
3. Linked issues with tracking relationship

## Notification Requirements

When SLA is violated, the notification should include:

1. **Issue identifier**: Number, title, and URL
2. **Repository**: Owner and repo name
3. **Failed criteria**: Specific conditions that were not met
4. **Recommended actions**: What the assignee should do to resolve
