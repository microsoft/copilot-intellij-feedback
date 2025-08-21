# GitHub Copilot Plugin for JetBrains IDEs

[GitHub Copilot Plugin for JetBrains IDEs](https://plugins.jetbrains.com/plugin/17718-github-copilot) is your AI-powered coding assistant, designed to enhance your development experience. Leveraging advanced language models, it provides intelligent code completions and chat-based assistance directly within your JetBrains IDEs.

This repository is for providing feedback on the GitHub Copilot Plugin for JetBrains IDEs, including Copilot Chat, completions and other features. You can use this repository to report issues or submit feature requests related to the user experience and interface of either extension.

Learn more about [GitHub Copilot](https://github.com/features/copilot) in our [docs](https://docs.github.com/en/copilot/quickstart?tool=jetbrains).

## Providing Feedback

You can use this repository to file issues for Copilot Chat and completions in JetBrains IDEs:

* Up-vote a feature or request a new one.
* Search for existing issues already reported for potential workarounds.
* Report a problem if you don't find what you are looking for.

## Troubleshooting Common Issues

Before filing a new issue, try these common solutions:

### Copilot tool window stuck on "Initializing..."

This often indicates a compatibility or dependency issue:

1. **Check plugin compatibility**: Ensure your IDE version is compatible with your Copilot plugin version
2. **Update to stable version**: If using a nightly build, try the latest stable release
3. **Verify dependencies**: Ensure the Kotlin plugin is enabled and up-to-date
4. **Restart IDE**: Sometimes a simple restart resolves initialization issues
5. **Check logs**: Enable [debug logging](https://github.com/microsoft/copilot-intellij-feedback/wiki/Enable-debug-logging) to identify specific errors

### ClassNotFoundException or NoClassDefFoundError

These errors typically indicate missing dependencies or version incompatibilities:

1. **Update IDE**: Ensure your JetBrains IDE is fully updated
2. **Update plugin**: Use the latest stable plugin version from the [JetBrains Marketplace](https://plugins.jetbrains.com/plugin/17718-github-copilot)
3. **Check Kotlin plugin**: Verify the Kotlin plugin is installed and enabled
4. **Clear caches**: Try File → Invalidate Caches and Restart

### Plugin not working after update

1. **Restart IDE**: Always restart after plugin updates
2. **Check authentication**: Verify you're still signed in to GitHub Copilot
3. **Re-enable plugin**: Try disabling and re-enabling the Copilot plugin
4. **Downgrade if needed**: If issues persist, consider reverting to a previous stable version

For more detailed troubleshooting steps, see our [Support Guide](SUPPORT.md).

## Getting Help

If troubleshooting doesn't resolve your issue:

1. **Search existing issues** for similar problems and solutions
2. **File a bug report** using our [issue template](.github/ISSUE_TEMPLATE/bug_report.md)
3. **Include debug logs** following our [logging guide](https://github.com/microsoft/copilot-intellij-feedback/wiki/Enable-debug-logging)
