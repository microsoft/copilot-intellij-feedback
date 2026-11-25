## [Unreleased]

## [1.22.0]

### New Features

- Added feature highlights with rich previews to showcase important feature updates.
- Added Automation (preview) for running automated tasks.
- Added support for Microsoft Foundry and Azure OpenAI models in Copilot agent, including model setup and thinking-effort selection.
- Expanded inline change review with Keep actions for local file changes and read-only comparisons for Cloud Sandbox history.
- Added automatic selection of the first available preferred model for custom agents in Local and Copilot agent chat.
- Added support for environment variables in project MCP server configurations.
- Added support for opening a project's session view in JetBrains IDEs from Copilot app.

### UX Improvements

- Simplified Copilot agent follow-ups: Enter to steer, Ctrl+Enter (Command+Enter on macOS) to queue.
- Improved Copilot Fusion in inline chat with clearer model and token details and a more reliable model picker.
- Improved Voice Dictation settings with a wider microphone picker and clearer device and language information.
- Made completed thinking and subagent activity easier to navigate, opening from the start and remembering the scroll position.
- Moved agent settings to a dedicated `Chat > Agent` page.
- Reorganized settings page with dedicated sub-settings pages.
- Made slash-command suggestions easier to scan with distinct icons for commands and skills.
- Added a View release notes link to plugin update prompts so you can review changes before updating.
- Added a org default label for default models set by the organization.
- Changed the "#" interaction to use the same type-to-filter behavior as "@" and "/" popups.
- Changed command search to use fuzzy match.

### Bug Fixes

- Fixed saved chat history being unexpectedly deleted.
- Fixed files deleted or moved by background agents disappearing from the changed files list.
- Fixed adding and removing customizations and MCP servers in Remote Development.
- Fixed MCP sign-in prompts being blocked by Local's Configure Tools dialog.
- Fixed sign-in and Local chat getting stuck on loading when using an HTTPS proxy.
- Fixed Claude agent startup with previously saved CLI paths on Unix systems.
- Removed the current IDE from the remote Environments picker to prevent connecting to itself.
- Fixed Copilot agent links in Usage Tips opening the wrong environment or chat mode from Cloud Sandbox.
- Fixed Cloud Sandbox conversations not showing an unread indicator when a reply completes after navigating away.
- Fixed Copilot agent Undo restoring deleted files with the wrong filename casing on Windows.
- Restored scrolling in the Copilot chat turn picker on IntelliJ IDEA 2026.3 so messages beyond the first ten are accessible.

### Changed

- Made the built-in JetBrains MCP server integration generally available in JetBrains IDEs 2026.1 and later.
- Restored automatic Maven vulnerability checks that send dependency coordinates to GitHub Advisories when projects open or import.

### Deprecation

- Ended support for JetBrains IDE 2025.2. Upgrade to 2025.3 or later to continue receiving GitHub Copilot updates.

## [1.21.1]

### New Features

- Added on-device voice dictation for Chat on supported native plugin packages with Editor Preview enabled. Dictation requires opt-in and a downloaded model, and keeps transcripts as editable drafts until Send.
- Added cloud sandbox (preview) support to run Copilot sessions in a remote sandbox environment. This feature is rolled out in phases.
- Added remote access (preview) with Mission Control registration while the IDE is open, allowing users to expose Copilot chats remotely. This feature is rolled out in phases.
- Added discovery of shared Copilot sessions from remote accessible computers, and reopening remote sessions from history to continue the conversation (preview). This feature is rolled out in phases.
- Added a browser use setting under Chat > Agent that enables the built-in browser-use plugin after restart (preview).
- Added support for Copilot Access.

### Bug Fixes

- Attempt to fix the issue of sessions being lost sometimes after a restart
- Fixed Local agent changes failing to open in Copilot (Modern Inline) review when the edited file was not already open.
- Fixed failed tool calls showing progress text instead of the actual error message.
- Fixed opening historical Copilot session diffs on newer JetBrains IDE EAP builds.

## [1.21.0]

### New Features

- Added initial support for Split Mode / Remote Development for Copilot agent sessions in JetBrains IDEs 261+. Support for MCP servers, Skills, and Custom Agents remains limited, with improvements coming in the next release.
- Added `/context` to Copilot agent chat to open the context usage popup directly when usage data is available.

### UX Improvements

- Grouped bundled plugin contributions under Built-in in Customizations while keeping user-installed plugin contributions separate.
- Hid installation paths from bundled plugin MCP list rows while preserving version information, diagnostics, and configuration access.
- Added timestamps to Copilot agent prompts and responses.
- Added a Delete button beside Archive in session history.
- Added an option to skip future single-session deletion confirmations.
- Pinned Fusion to the top of Copilot agent model management.
- Kept Fusion enabled in model management, including when deselecting the entire model group.
- Added an "Upgrade for More Models" link above "Manage Models" in the model picker for Copilot Free users.
- Added Chat Usage Tips for Agent Debug Logs, Policy Diagnostics, and the GitHub Copilot App.
- Showed Copilot Access usage in the quota dialog the same way as other organization plans, with organization help links and no upgrade or overage actions.

### Bug Fixes

- Fixed Copilot Chat settings freezing while file safety rules load.
- Fixed Copilot CLI chats appearing stopped after a hook error while the response or Fusion workflow was still running.
- Made MCP server actions in Configure Tools keyboard-accessible, including Start, Stop, Restart, More, and View Error Log.
- Fixed saved chat input failing to persist when a session was updated.
- Fixed a Copilot slash command being cancelled when submitted before a previous Stop request finished.
- Fixed chat initialization failures in standalone IDEs.
- Fixed Local chat startup failing when language-server recovery overlaps an in-progress initialization.
- Fixed Copilot Chat sometimes remaining on "Processing..." after the language server restarts.
- Fixed Add Context search hiding matching actions such as Global Files and Folders and Add All Open Files.
- Fixed inline code rendering in Copilot agent conversations to preserve literal punctuation and prevent unintended formatting.
- Fixed Credits and status text colors in the session sidebar.
- Removed the standalone `/chronicle` command in Copilot agent while keeping its available subcommands selectable and executable.
- Fixed the vertical alignment of the Apply and Cancel buttons in the Configure Tools dialog.
- Fixed the IDE MCP Server banner in Configure Tools opening Customizations when clicking outside its Configure action.
- Fixed chat input losing focus after submitting a message while another input-toolbar control was focused.
- Allowed clearing saved MCP OAuth client registration after an initial sign-in failed or was cancelled.

### Changed

- Made the Chat onboarding tour generally available to eligible users.
- Made Chat Usage Tips available by default while preserving the saved Tips preference.
- Made Java modernization findings in Problems View available on supported IDEs.
- Stopped automatic external dependency scans when opening or importing Maven projects.
- Disabled Claude and Codex under enterprise managed settings unless an administrator policy allows an exception, while preserving saved provider preferences.
- Applied enterprise-managed Copilot Fusion Tier defaults while keeping available tiers selectable and preserving saved choices.
- Switched Code Review to the Copilot agent review engine while keeping results in the existing inline review UI.

### Deprecation

- Added advance notice for JetBrains IDE 2025.2 users to upgrade to 2025.3 or later, with 2026.2 or later recommended for the best experience. Support remains unchanged in this release.

## [1.20.0]

### New Features
- Added support for Copilot Fusion tiers in Copilot agent chat sessions, with a gradual rollout to users.
- Added a setting to configure the default permission mode for new Copilot sessions.
- Added allowed and blocked host rules in Copilot agent sandbox settings, with host validation and read-only organization-managed rules.
- Added a Sandbox setting to exclude MCP server processes started by Copilot and their remote network traffic from the sandbox.
- Added managed permission restrictions for Claude, disabling elevated permission modes and Global Auto Approve when required by policy.
- Enabled session-provided slash commands for Claude, with command descriptions and input hints alongside IDE commands.

### UX Improvements

- Moved GitHub Copilot settings to the top level of IDE Settings for easier access.
- Moved Copilot ahead of Local in the agent picker when both providers are enabled.
- Improved coordination between inline completions and next edit suggestions, including follow-ups after accepting a completion.
- Improved sign-in, sign-out, and account-switch notifications with concise, timed messages, including the authenticated account name for successful switches when available.
- Updated Copilot update prompts to open the Plugins Marketplace filtered to the official GitHub Copilot plugin instead of the general IDE update flow.
- Replaced the Copilot agent's built-in subagent model checkbox with a default / Session model dropdown while preserving existing preferences.
- Moved the subagent restart reminder next to Enable Subagent and grouped its model settings below.
- Added a Copilot agent turn tooltip showing completion time, generation time, and per-model token usage.

### Bug Fixes

- Hid session sidebar history and session actions while signed out.
- Fixed `/rename` and `/session rename` not updating forked Copilot agent session titles.
- Showed the agent name instead of its ID in Copilot agent's `read_agent` and `write_agent` tool calls.
- Made Copilot agent's `read_agent` and `write_agent` tool call details expandable.
- Fixed blocked MCP servers, their tool categories, and individual tools remaining selectable in Copilot's Configure Tools dialog.
- Fixed Cancel in Local's Configure Tools dialog changing mixed MCP tool selections.
- Fixed Apply in Local's Configure Tools dialog not restoring saved MCP tool selections to the language server.
- Fixed Undo and Undo All for Copilot agent inline changes appended to files without a final newline.
- Fixed Copilot (Modern Inline) review falling back to Classic view when a file-edit request used different filename casing on a case-insensitive filesystem.
- Improved Inline Chat Stop recovery when a request was cancelled before execution began, preserving the conversation and pending edits.
- Prevented consecutive Local agent edits to the same file from overwriting earlier changes or using stale file content.
- Fixed million-token context windows displaying an unnecessary decimal zero in model settings.
- Fixed workspace and user prompt templates not returning to chat after the Copilot language server restarts.
- Fixed the **What's New** tab failing to open on IntelliJ 2026.3.
- Fixed the Sandbox badge being truncated at some IDE zoom levels.
- Fixed incorrect selected-code context for selections containing tabs or emoji.
- Fixed tool-call code blocks retaining discarded chat components until the project was closed.
- Fixed user-level skills being cancelled instead of read on Windows when their file paths were supplied as URIs.
- Fixed an IDE error when revealing customization files in the file manager from WSL projects, and prevented file-manager actions from blocking the UI.
- Disabled BYOK add and configuration actions in the Language Models dialog when Bring Your Own Key was turned off.
- Fixed a broken user message layout in Local Agent.

### Changed

- Made Copilot the default agent for all users when available.
- Made Sandbox settings and the `/sandbox` command generally available, and removed the Preview label.
- Removed the confirmation dialog when enabling Sandbox.

## [1.19.1]

### Bug Fixes

- Fixed errors when opening Copilot Chat, Recent Sessions, and the session navigator in JetBrains IDEs 2026.3 EAP.

## [1.19.0]

### New Features

- Added enterprise-managed settings to choose any available Copilot agent model as the default for new conversations.
- Added a Fix action to diagnostic intention menus that opens inline chat to request a repair, using Agent mode when available and Ask otherwise.
- Added an MCP setting to disable automatic server startup for Copilot and Claude while keeping manual Start and Restart available.

### UX Improvements

- Refined signed-in Copilot account controls with clearer account labels, simpler status display, improved long-list navigation, and a Switch Account action.
- Added a one-time reminder beside the Chat icon to help newly installed users discover and open GitHub Copilot Chat.
- Updated the Copilot agent placeholder to highlight questions, edits, context, and commands.
- Refined the Copilot Chat sign-in page with a responsive centered layout, clearer headings, theme-aligned styling, improved provider choices, and a direct Copilot plans link. Added cancellable, non-modal progress while browser authorization is pending.
- Made Go Back open a Copilot home session after an accepted migration command, even when continuing the Local conversation.
- Group chat messages by turns and allow quickly navigating between turns.
- Added action buttons to copy and edit user messages.

### Bug Fixes

- Fixed IDE freezes when switching chat agent providers with large model lists.
- Fixed requests sent during Copilot language server startup failing when initialization took longer than half a second.
- Fixed Customizations Generate and New actions so they replace an existing Copilot agent chat draft with the selected `/create-*` command.
- Corrected displayed line-change counts for Copilot agent file tool calls and Working Set entries.
- Fixed newly created customizations not appearing after adding a module to an open project.
- Fixed the initial blank Copilot agent chat not applying an available enterprise-managed default model after settings loaded, while preserving explicit picker choices.
- Fixed the missing IntelliJ IDEA MCP Server entry in Customizations on IntelliJ IDEA 2026.3 EAP.
- Fixed Settings remaining open when opening MCP configuration files in JetBrains IDEs 2026.2 and later.
- Fixed the horizontal scrollbar intercepting clicks on model groups near the bottom of Manage Models.
- Refreshed organization agents, skills, and instructions in Customizations after their cached content changed outside the IDE.
- Removed edit and delete actions from organization-managed custom agents.
- Fixed Copilot agent sessions ignoring MCP servers configured in a repository-root `.mcp.json` file.
- Improved tool-call details by making Stored Memory details expandable and removing empty `(no input)` placeholders.
- Restored Diff, Undo, and Apply actions for Working Set files referenced with different letter casing on case-insensitive filesystems.
- Fixed an intermittent IDE error when cancelling worktree creation with Go Back.
- Fixed applying worktree changes back to WSL projects on Windows.
- Fixed Copy Changes hiding local edits or changing staged files when creating a Copilot CLI worktree, including when creation was cancelled.
- Fixed cancelling Copy Changes worktree creation leaving temporary worktrees and branches or showing a creation failure.

### Deprecation

- Ended support for JetBrains IDE 2025.1. GitHub Copilot now requires JetBrains IDE 2025.2 or later.

## [1.18.0]

### New Features

- Added a side-by-side chat panel switcher in the session toolbar, so you can chat in the editor while browsing sessions in the tool window.
- Added AI-assisted tool approvals (Assisted Approvals) for Copilot agent sessions (Public Preview), automatically approving low-risk tool calls while continuing to prompt for higher-risk actions.
- Added support for re-editing a previous user message in Copilot agent sessions, rewinding the conversation and file changes before sending the replacement message.
- Added an enabled-by-default setting to turn the built-in GitHub MCP server on or off without changing manually configured MCP servers.
- Added support for organization and enterprise skills in Local and Copilot agent sessions.
- Added organization-managed custom instructions for Local and Copilot agent sessions.
- Added Plan mode for Codex agent, allowing users to review, refine, or approve a plan before implementation.
- Added persistent per-tool controls for MCP servers used by Copilot agent sessions.
- Added browsable Usage Tips above the Chat input to help you discover Copilot features, with shortcuts to commands, customizations, and settings.

### UX Improvements

- Simplified the Chat welcome screen with a cleaner layout and a direct Share feedback link.
- Labeled the built-in GitHub MCP server in Configure Tools and added a direct link to manage it in Settings.
- Restored shortcuts for updating Agent Instructions and viewing usage-based billing best practices in Chat Usage Tips.
- Clarified the `/init` tip and grouped it under Customizations.

### Bug Fixes

- Classified the IDE-managed debugger skill as a read-only built-in customization instead of a configurable user skill.
- Fixed Codex sessions failing to start when a saved macOS or Linux CLI path was missing its leading slash.
- Fixed an intermittent IDE error when global instructions refreshed while an MCP authentication dialog was open.
- Fixed Escape in the Language Models dialog to clear an active search without closing the dialog, and close it when the search is empty.
- Fixed Inline Chat ignoring the selected Thinking Effort and Context Window settings when using Copilot agent sessions.
- Fixed errors and unresponsive controls when stopping or closing inline chat, including during initial session setup.
- Fixed Inline Chat Ask overwriting user edits when a request ended or the chat was closed.
- Fixed MCP log actions opening the log tool window in a different project when multiple project windows were open.
- Fixed Copilot attention alerts when another project window in the same IntelliJ instance is focused on Windows.
- Restored embedded editors and message re-editing on IntelliJ 2026.3 EAP builds.

### Changed

- Hid inline chat and its entry points in JetBrains Gateway and remote development environments.

### Deprecation

- Added advance notice for JetBrains IDE 2025.1 users to upgrade to 2026.1 or later. Support remains unchanged in this release.

## [1.17.0]

### New Features
- Added support for adding global files and folders as chat context, making it faster to include broader project context in your prompts.
- Added cross-file cursor jump in Next Edit Suggestions to navigate and apply coordinated code suggestions across related files.
- Added support for enterprise-managed sandbox policies (Preview).
- Added enterprise policy diagnostics support, allowing users to verify that enterprise policies are correctly detected and enforced on their device.
- Added support for using IDE terminal environment variables and Python interpreter in Copilot shell commands.
- Added support for activating the project-configured standard local Python venv in Copilot shell commands.
- Added support for connecting terminal Copilot CLI sessions to JetBrains IDE context—including selections, diagnostics, and file references—using '/ide' in GitHub Copilot CLI (Preview)
- Added support for selecting the session model used by built-in subagents in the Copilot agent harness.
- Improved the plugin update reminder experience to make updates more user-friendly and discoverable. 

### UX Improvements
- Improved the ask-user card in Copilot agent harness to better accommodate long questions.
- Improved model and BYOK selection clarity by refining model picker grouping and interaction behavior.
- Improved agent debug logs usability by adding section copy support for faster sharing and troubleshooting.
- Improved MCP configuration navigation by opening MCP configuration in the originating project window.

### Bug Fixes
- Fixed blank local chat sessions after IDE scale changes.
- Fixed incorrect change counts (such as +0 −0) in the Copilot agent working set.
- Fixed working-set zoom and model picker close interactions to reduce UI friction.
- Fixed local agent editing behavior for read-only files.
- Fixed MCP reliability issues by preserving BYOK provider selection, OAuth challenge handling, and restored stopped-state binding.
- Fixed GHE authority propagation in agent flows.
- Fixed Claude plan stop-state behavior.
- Prevented Copilot panel and worktree sessions from receiving misleading IDE diagnostics for files that have not been opened.
- Fixed Agent Customizations showing stale global instruction content after the file was changed outside the IDE.
- Improved chat reliability after automatic compaction, preventing sessions from getting stuck during user interactions.

### Changed
- OpenTelemetry Settings under "GitHub Copilot - Chat" are now Generally Available to all users.

## [1.16.1]

### New Features

- Show guided onboarding tips for Copilot users without prior sessions.

### Bug Fixes

- Fixed Copilot UI panels failing to open since JetBrains IDE `2026.2.2 Preview`.

## [1.16.0]

### New Features
- Added built-in JetBrains MCP server support (Preview).
- Added post-update release discovery by showing a **What's New** tab after plugin updates.
- Added Copilot harness `/review` integrations in JetBrains.
- Added plugin support in Claude agent flows.

### UX Improvements
- Improved model-management usability with stronger search behavior, a clear action in search, resizable **Language Models** table columns, and promo ordering refinements.
- Improved debug-log exploration with event-time sorting, token-usage filters, refined layout behavior.
- Improved chat ergonomics by scrolling long tool output, adding review-plan-card scrolling, and adding shortcuts for send options.
- Improved customization handling in multi-root workspaces by discovering customizations across all folders and honoring client-provided customization locations.

### Bug Fixes
- Fixed account and sign-in reliability issues, including account-state detection, account ordering in picker flows, and sign-in settings-page interaction issues.
- Fixed MCP reliability issues, including invalid registry-schema handling, stale tool checks after account switches, and UI freezes during auto-enable flows.
- Fixed BYOK and model-refresh reliability issues.
- Fixed Copilot Agent continuity issues, including model switching after resume and complete model-info propagation for resumed sessions.
- Fixed editor and message-rendering defects.
- Fixed Worktree sessions failing to start for projects opened from WSL.
- Restored file and folder `#` references in Copilot, Claude, and Codex chat inputs.
- Fixed MCP tool auto-approve configuration for servers running only in Copilot.

### Changed
- Copilot harness is now GA.
- Plugins support is now GA.
- Autopilot is now GA.
- Changed routing for reasoning-capable BYOK OpenAI models to use the Responses API.
- Changed Copilot harness `/review` availability so it is limited to agent mode.

## [1.15.0]

### New Features
- Added Ollama as a BYOK provider across backend and JetBrains UI flows, including provider wiring and model handling.
- Added Copilot CLI auto-install support in JetBrains IDE integrated terminals on macOS, Linux, and Windows.
- Added support for server-based Enterprise Managed Policy:
    - plugin settings: enabledPlugins, extraKnownMarketplaces, strictKnownMarketplaces
    - MCP settings: allowedMcpServers and deniedMcpServers
    - permission setting: permissions.disableBypassPermissionsMode
    - OpenTelemetry settings: telemetry
- Added Codex-focused capabilities, including session visibility in Agent Debug Logs, permission-mode catalog updates, and customization support for instructions and skills.
- Added Copilot Memory support in the Copilot CLI chat experience to persist and recall information across sessions, managed via toggle in the Copilot settings portal.

### UX Improvements
- Improved account management flows by supporting account switch/removal and polishing account-deletion interactions.
- Improved model and settings usability by capping long model-name width in the model picker and refining model view/todo list panel behavior.
- Improved background-agent workflows with drag-and-drop support, copy-agent-message support, and clearer autopilot completion summaries.
- Restored file and folder `#` references in Copilot, Claude, and Codex chat inputs.

### Bug Fixes
- Fixed MCP execution and approval issues, including preserving gateway refreshes after CLS restart and correcting auto-approve behavior for Copilot-only servers.
- Fixed terminal and command-output issues, including ANSI escape rendering, deterministic scrollbar reservation, and terminal auto-approve/reset behavior in Chat.
- Fixed customization and cloud-agent reliability issues.
- Fixed diff/edit stability issues.

### Changed
- Changed user-facing naming from “Copilot CLI” to “Copilot” in product strings.
- Changed support permission requests and permission modes selection for Codex.

## [1.14.2]

### Bug Fixes

* Fixed a model support issue.

## [1.14.1]

### New Features

* Added MCP and custom agent support in Claude agent flows.
* Added OpenTelemetry export settings for agent workflows in JetBrains IDEs.
* Added default token limits and support for configuring `maxInputTokens` and `maxOutputTokens` for BYOK and custom endpoints.
* Added model-management controls to disable or enable all built-in Copilot models.
* Added fork support to the Copilot CLI chat experience.
* Added `/rubber-duck` command to the Copilot CLI chat experience.
* Added todo list display in Copilot CLI chat experience.
* Added the display of number of AI credits a user has consumed for users in organizations that don't set a [User-level budget](https://docs.github.com/copilot/concepts/billing/budgets-for-usage-based-billing#user-level-budget).

### UX Improvements

* Improved model and action picker consistency.
* Improved customization usability.
* Improved session clarity by rendering ask-user questions as Markdown and adding explicit user attention notifications.
* Improved inline chat and model-picker layout behavior.
* Improved MCP diagnostics.
* Improved bare URL rendering in Copilot CLI chat experience.

### Bug Fixes

* Fixed path-case preservation issues in Copilot CLI working-set and snapshot recording flows on macOS and Linux.

## [1.13.1]

### Bug Fixes

* Fixed an auth issue
* Fixed a few minor UI issues

## [1.13.0]

### New Features

* Added BYOK custom provider support.
* Added support for exporting agent debug logs for Copilot CLI sessions.
* Added support for Claude agent customization.
* Added plugin and plugin marketplace management in the customization panel (Preview).
* Added support for local sandboxing (Preview).
* Added agent-driven debugger skill for Copilot CLI sessions (Preview).

### UX Improvements

* Improved model picker controls in chat and inline chat.
* Improved readability for Copilot CLI thinking and ask-user cards.
* Improved UI clarity for custom agents, customization, and provider settings.
* Improved authentication UX messaging.

### Bug Fixes

* Fixed auth recovery for token reuse failures.
* Fixed provider and session persistence regressions.
* Fixed BYOK degraded-model warnings, pending-save refresh races, provider-add gating when mappings were missing, and disabled-model retention.
* Fixed MCP customization stability and trust behavior.
* Fixed stability issues in editor and chat flows.
* Fixed workspace-trust enforcement for prompts and hooks.
* Fixed a regression where plugins were omitted in list conversation mode.
* Fixed custom-agent validation handling.

### Changed

* Copilot CLI agent harness now remains available regardless of the enterprise Copilot CLI policy.
* Changed model availability by plan.
* Changed model controls to support Gemini thinking-effort configuration.

## [1.12.1]

### New Features

* Added: Codex as Agent Provider in public preview.
* Added: Hooks support for Agent Customizations editor.
* Added: Create customization files enhancements, including manual creation capabilities and new slash commands.
* Added: Enhanced MCP Server management with workspace-level support and richer configuration options.
* Added: Support for custom models in JetBrains IDEs (configured by GitHub Copilot Business and Enterprise administrators in GitHub settings).
* Added: Approval settings for Copilot CLI sessions.
* Added: PermissionMode selection in Claude Code agent sessions.
* Added: Agent debug log support for Claude sessions.
* Added: Model view management support.

### User Experience

* Improved: Added best practice tips for usage-based billing.
* Improved: Stability and performance when loading the panel.
* Improved: Added NES suggestion caching and improved performance.
* Improved: File watcher performance and reduced memory usage.

### Bug Fixes

* Fixed: an issue where BYOK sessions could trigger Copilot subagents and consume Copilot usage. The subagent logic now respects the active BYOK provider.
* Fixed: Multiple UI freeze issues.


### Changed

* Inline chat is generally available.


## [1.12.0]

### New Features

* Added: Codex as Agent Provider in public preview.
* Added: Hooks support for Agent Customizations editor.
* Added: Create customization files enhancements, including manual creation capabilities and new slash commands.
* Added: Enhanced MCP Server management with workspace-level support and richer configuration options.
* Added: Support for custom models in JetBrains IDEs (configured by GitHub Copilot Business and Enterprise administrators in GitHub settings).
* Added: Approval settings for Copilot CLI sessions.
* Added: PermissionMode selection in Claude Code agent sessions.
* Added: Agent debug log support for Claude sessions.
* Added: Model view management support.

### User Experience

* Improved: Added best practice tips for usage-based billing.
* Improved: Stability and performance when loading the panel.
* Improved: Added NES suggestion caching and improved performance.
* Improved: File watcher performance and reduced memory usage.

### Bug Fixes

* Fixed: an issue where BYOK sessions could trigger Copilot subagents and consume Copilot usage. The subagent logic now respects the active BYOK provider.
* Fixed: Multiple UI freeze issues.


### Changed

* Inline chat is generally available.

## [1.11.2]

### Bug Fixes

* Resolved: An issue that blocks users from signing in.

## [1.11.1]

### New Features

* Added: support for "Add to Queue", "Steer with Message", and "Stop and Send" options in CLI sessions
* Added: support for organization and enterprise agents from GitHub
* Added: Agent debug logs summary view
* Added: Claude Agent in public preview
* Added: /migrate slash command to migrate Local sessions to CLI sessions
* Added: /models slash command to open the model picker, with support for both Copilot CLI and Claude Agent
* Added: per-turn AI credits indicator in Local, CLI and Claude Agent sessions
* Added: support for selecting larger context window from model picker
* Added: recently used model section in the Local agent model picker

### User Experience

* Improved: chat input layout for better reliability
* Improved: inline chat experience by ensuring state resets when closed during a response
* Improved: code block rendering performance
* Improved: NES by adding richer code diagnostic information for better suggestions

### Bug Fixes

* Fixed: an issue where diff views would open for every agent edit
* Fixed: an issue that could cause no completion models to be shown in settings
* Fixed: multiple UI freeze issues

### Changed

* Cloud agent is generally available

## [1.11.0]

### New Features

* Added: support for "Add to Queue", "Steer with Message", and "Stop and Send" options in CLI sessions
* Added: support for organization and enterprise agents from GitHub
* Added: Agent debug logs summary view
* Added: Claude Agent in public preview
* Added: /migrate slash command to migrate Local sessions to CLI sessions
* Added: /models slash command to open the model picker, with support for both Copilot CLI and Claude Agent
* Added: per-turn AI credits indicator in Local, CLI and Claude Agent sessions
* Added: support for selecting larger context window from model picker
* Added: recently used model section in the Local agent model picker

### User Experience

* Improved: chat input layout for better reliability
* Improved: inline chat experience by ensuring state resets when closed during a response
* Improved: code block rendering performance
* Improved: NES by adding richer code diagnostic information for better suggestions

### Bug Fixes

* Fixed: an issue where diff views would open for every agent edit
* Fixed: an issue that could cause no completion models to be shown in settings
* Fixed: multiple UI freeze issues

### Changed

* Cloud agent is generally available

## [1.10.1]

### Bug Fixes

* Resolved: An issue where Plan mode (in Local agent) could modify files instead of staying read-only.

## [1.10.0]

### New Features

* Added: Agent picker support for Copilot CLI sessions, with Agent (default), Ask, Plan, and Custom agent modes.
* Added: Support MCP configuration for Copilot CLI sessions.
* Added: Support BYOK for Copilot CLI sessions.
* Added: /compact slash command for Copilot CLI sessions.
* Added: /chronicle slash command for Copilot CLI sessions.
* Added: /plan slash command for Copilot CLI sessions.
* Added: Agent debug panel in public preview.
* Added: Cloud Agent integrated into the unified sessions view.
* Added: Thinking effort configuration for supported models.
* Added: Agent customizations editor.
* Added: More sign-in choices with Google and Apple.

### User Experience

* Improved: Smoother NES experience with improved trigger strategy and detection logic.
* Improved: Unified session views with improved layout and readability.
* Improved: Account/session isolation between different editors.

### Bug Fixes

* Resolved: An issue where the stop button was missing during CLI agent execution.
* Improved: Unified session persistence and state management.
* Improved: Overall UI freeze handling and stability.

### Changed

* Agent skills are generally available.
* Agent hooks are generally available.
* Prompt files are generally available.
* Anthropic Thinking is generally available.
* BYOK is available without the Editor Preview feature flag, and availability for Copilot Business and Enterprise is controlled by GitHub policy.

## [1.9.1]

### New Features

* Added /remote command to control Copilot CLI sessions, allowing you to view and steer from GitHub.com and the GitHub mobile app. Enable from Settings > Tools > GitHub Copilot > Chat > Enable Copilot CLI Remote.
* Added internal support for upcoming usage-based billing, including billing updates for the usage panel, usage notifications, and model picker. This will be visible to the user once usage-based billing rolls out.

### Changed

* MCP Registry (Experimental) is available without the Editor Preview feature flag
* MCP Allowlist (Experimental) is available without the Editor Preview feature flag

## [1.9.0]

### New Features

* Added: GitHub Copilot CLI support for delegating tasks to a locally running Copilot CLI (preview)
* Added: Unified session view to manage local and GitHub Copilot CLI sessions
* Added: Ask question tool in agent mode
* Added: GitHub Enterprise Server (GHES) support in the sign-in flow
* Added: Global .agent.md file support under ~/.copilot/agents, with UI support coming soon

### User Experience

* Improved: Added confirmation when starting a new command to cancel the active one
* Improved: Sub-agent rendering and current file as context styling
* Improved: Auto‑approval panel UI
* Improved: Hover and pressed states for code‑block actions
* Improved: Code review apply behavior with full‑line replacements

### Bug Fixes

* Fixed: Code completions not working on a second screen
* Fixed: Shift+Home / Shift+End issues for inline selection
* Fixed: Drag-and-drop issues when adding files to Copilot Chat
* Fixed: Multiple UI freezes and responsiveness issues

### Changed

* Changed: Plan agent is no longer auto-invoked in sub-agent workflows, and remains available from the mode picker

### Deprecation

* Removed: Edit mode support

## [1.8.2]

### What's New

- **We’ve made updates to help you better understand and manage your Copilot session usage:**
* Improved: Clearer messages when you hit usage limits, with more details on what happened and what to do next.
* Improved: More accurate and transparent reset times, so you know exactly when your usage will refresh.
* Added: Proactive notifications when you’re approaching your limits, helping you avoid unexpected interruptions.

## [1.8.1]

### What's New

- **We’ve made updates to help you better understand and manage your Copilot session usage:**
* Improved: Clearer messages when you hit usage limits, with more details on what happened and what to do next.
* Improved: More accurate and transparent reset times, so you know exactly when your usage will refresh.
* Added: Proactive notifications when you’re approaching your limits, helping you avoid unexpected interruptions.

## [1.8.0]

### New Features

* Added: Inline agent mode (preview).
* Added: Next Edit Suggestions enhancements, including inline edit previews and far-away edits.
* Added: Global auto‑approve and granular controls for terminal commands and file edits.

### User Experience

* Improved: Chat context resets automatically after sending messages.
* Improved: Chat history rendering performance for large conversations.
* Improved: Stability and quality of chat code blocks.
* Improved: Inline code review panel supports automatic resizing.
* Improved: Refined login experience with a smoother device code flow.
* Improved: UX enhancements across sign‑in, tooltips, and focus behavior.

### Bug Fixes

* Fixed: Chat spinner hanging during responses.
* Fixed: Esc key failing to dismiss selections and IDE popups.
* Fixed: Improved state handling in the Configure Tools window.
* Fixed: Multiple UI freeze issues.

## [1.7.1]

### User Experience

* Improved: Chat input history syncs across sessions.
* Improved: Model picker reliability with better caching and degradation warnings.
* Improved: Thinking panel layout for readability.
* Improved: Auto‐approve flow, including confirmation before resetting rules.
* Improved: Tool‑result code blocks are read‑only and large outputs load smoothly.
* Improved: Settings management for pre‑login confirmation, proxy validation, and safer revert behavior.
* Improved: Copilot status bar displays GitHub username and sign‑in state.

### Bug Fixes

* Fixed: Reduced multiple UI freezes.
* Fixed: Chat scroller flicker and HiDPI scaling issues.
* Fixed: Chat panel stuck on the loading page.
* Fixed: Markdown file links in the chat panel failed to open.
* Fixed: Incomplete copied response content in Ask mode.
* Fixed: Inconsistent UI appearance when switching themes, fonts, or modes.


### Deprecation

* Updated: GitHub Copilot will end support for JetBrains IDEs versions 2024.2 and 2024.3.

## [1.7.0]

### User Experience

* Improved: Chat input history syncs across sessions.
* Improved: Model picker reliability with better caching and degradation warnings.
* Improved: Thinking panel layout for readability.
* Improved: Auto‐approve flow, including confirmation before resetting rules.
* Improved: Tool‑result code blocks are read‑only and large outputs load smoothly.
* Improved: Settings management for pre‑login confirmation, proxy validation, and safer revert behavior.
* Improved: Copilot status bar displays GitHub username and sign‑in state.

### Bug Fixes

* Fixed: Reduced multiple UI freezes.
* Fixed: Chat scroller flicker and HiDPI scaling issues.
* Fixed: Chat panel stuck on the loading page.
* Fixed: Markdown file links in the chat panel failed to open.
* Fixed: Incomplete copied response content in Ask mode.
* Fixed: Inconsistent UI appearance when switching themes, fonts, or modes.


### Deprecation

* Updated: GitHub Copilot will end support for JetBrains IDEs versions 2024.2 and 2024.3.

## [1.6.1]

### New Features

* Added: Sub-agents, Custom Agents, and Plan Agent are generally available.
* Added: Auto model selection is generally available.
* Added: Agent hooks support is in public preview.
* Added: Auto-approve support for MCP at both server and tool levels.
* Added: Thinking panel for extended‑reasoning models (e.g., Codex), with configurable Anthropic thinking budgets.
* Added: Support for AGENTS.md and CLAUDE.md instruction files, including generating initial instructions and prompting updates.
* Added: /memory slash command to open Customization settings.
* Added: Context window usage indicator in the chat panel.

### User Experience

* Improved: Smoother login experience for GitHub Enterprise users.
* Improved: Automatically open the chat panel after signing in for easier access.
* Improved: Support for prioritizing device code flow authentication via a config entry in settings.
* Improved: NES trigger timing and popup dismissal logic.
* Improved: More responsive chat panel layout across different window sizes.
* Improved: Cleaner auto-approve UI for a more intuitive approval workflow.
* Improved: Chat panel context UX with cleaner and more consistent file attachments.
* Improved: Windows ARM platform support.

### Bug Fixes

* Fixed: Improved stability when reading terminal output.
* Fixed: The replace_string_in_file tool did not update file content correctly.
* Fixed: "Keep All/Undo All" buttons remained after switching windows.
* Fixed: UI hangs in chat and inline completions caused by blocking EDT calls.
* Fixed: Blank chat panel when the terminal plugin was unavailable.
* Fixed: MCP code vision appeared when signed out.
* Fixed: File icons flickered when the selected code range changed.

### Deprecation

* Updated: Edit mode is now marked as deprecated.

## [1.6.0]

### New Features

* Added: Sub-agents, Custom Agents, and Plan Agent are generally available.
* Added: Auto model selection is generally available.
* Added: Agent hooks support is in public preview.
* Added: Auto-approve support for MCP at both server and tool levels.
* Added: Thinking panel for extended‑reasoning models (e.g., Codex), with configurable Anthropic thinking budgets.
* Added: Support for AGENTS.md and CLAUDE.md instruction files, including generating initial instructions and prompting updates.
* Added: /memory slash command to open Customization settings.
* Added: Context window usage indicator in the chat panel.

### User Experience

* Improved: Smoother login experience for GitHub Enterprise users.
* Improved: Automatically open the chat panel after signing in for easier access.
* Improved: Support for prioritizing device code flow authentication via a config entry in settings.
* Improved: NES trigger timing and popup dismissal logic.
* Improved: More responsive chat panel layout across different window sizes.
* Improved: Cleaner auto-approve UI for a more intuitive approval workflow.
* Improved: Chat panel context UX with cleaner and more consistent file attachments.
* Improved: Windows ARM platform support.

### Bug Fixes

* Fixed: Improved stability when reading terminal output.
* Fixed: The replace_string_in_file tool did not update file content correctly.
* Fixed: "Keep All/Undo All" buttons remained after switching windows.
* Fixed: UI hangs in chat and inline completions caused by blocking EDT calls.
* Fixed: Blank chat panel when the terminal plugin was unavailable.
* Fixed: MCP code vision appeared when signed out.
* Fixed: File icons flickered when the selected code range changed.

### Deprecation

* Updated: Edit mode is now marked as deprecated.
