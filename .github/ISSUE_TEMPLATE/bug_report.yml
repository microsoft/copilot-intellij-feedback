name: 🐛 Bug report
description: Create a report to help us improve the GitHub Copilot experience for JetBrains
labels:
  - bug
  - triage-needed

body:
  - type: markdown
    attributes:
      value: |
        Thank you for reporting an issue.

        This issue tracker is for bugs and issues found in **GitHub Copilot for JetBrains**.
        Please fill in as much of the form as possible.

  - type: dropdown
    id: feedback_source
    attributes:
      label: Feedback source
      description: Where did you encounter or discuss this issue?
      options:
        - JetBrains Marketplace
        - GitHub Discussion
        - Internal Enterprise Feedback
        - Reddit
        - X/Twitter
        - Other

  - type: input
    id: plugin_version
    attributes:
      label: GitHub Copilot plugin version
      description: |
        You can check the versions from Settings -> Plugins -> Installed  

  - type: input
    id: ide_version
    attributes:
      label: JetBrains IDE and version
      description: |
        Please specify the JetBrains IDE you are using (e.g., IntelliJ, PyCharm) and its version.

  - type: textarea
    id: platform
    attributes:
      label: Platform
      description: |
        **UNIX:** output of `uname -a`  
        **Windows:** output of  
        `"$([Environment]::OSVersion.VersionString) $(('x86', 'x64')[[Environment]::Is64BitOperatingSystem])"`  
        in PowerShell

  - type: textarea
    id: steps
    attributes:
      label: Steps to reproduce
      description: >
        Describe how to reproduce the issue.  
        If applicable, include a minimal code snippet that can run directly without third-party dependencies.
    validations:
      required: true

  - type: textarea
    id: logs
    attributes:
      label: Logs (optional)
      description: |
        If possible, include debug-level logs.

        **Enable debug logs:**  
        https://github.com/microsoft/copilot-intellij-feedback/wiki/Enable-debug-logging

        **Get log file:**  
        Help → *Show Log in Explorer / Finder* → attach `idea.log`

  - type: textarea
    id: expected
    attributes:
      label: Expected behavior
      description: Please describe what you expected to happen. Textual output is preferred over screenshots.
    validations:
      required: true

  - type: textarea
    id: actual
    attributes:
      label: Actual behavior
      description: Please provide screenshots, videos, or textual output of what you observed.
    validations:
      required: true

  - type: textarea
    id: additional
    attributes:
      label: Additional information
      description: Include anything else you think may help us investigate.
