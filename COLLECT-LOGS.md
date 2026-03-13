# How to Collect Logs
Thank you for providing steps to help us reproduce the issue. Sometimes it can still be unclear what is actually happening. In these cases, log files are crucial for troubleshooting. Please collect relevant log files and attach them to your issue. There are three places where you can find logs: exceptions, freezes, and log files.

## 1. Exceptions
Please pay attention to this kind of notifications at the bottom right corner.  
![Screenshot](https://github.com/user-attachments/assets/a14753e8-bcdb-4b2f-b1f9-eb572b5c8e2e)  
Whenever you see them, please click to show this dialog.  
![Screenshot](https://github.com/user-attachments/assets/3a8a64d4-4155-497c-87de-912a259bdd1d)  
Please attach all the stack traces in the GitHub issue you open. Note that there can be multiple exceptions, please navigate and send all to us.

## 2. Freeze Events
Freeze event shows up as a notification in the editor area as below, please click "Report problem".  
![Screenshot](https://github.com/user-attachments/assets/da331f91-394e-4cc0-8b05-880641846b1b)  
Please do the following:
1. Open an issue with stack trace attached
2. Click "Report to plugin owner" to send a copy of the stack trace directly to us
![Screenshot](https://github.com/user-attachments/assets/95bd44f6-0ff4-4ed4-86ff-c1008b94db1e)

## 3. Log Files
> Please turn ON debug mode to enable verbose log collection. Thank you!  
> https://github.com/microsoft/copilot-intellij-feedback/wiki/Enable-debug-logging

To show where the logs persist, click "Help -> Show Log in Explorer (Finder)". Then find the file named `idea.log`.  
You can selectively share log snippets with us. Or feel free to attach all log files in the issue.  
![Screenshot](https://github.com/user-attachments/assets/152780a7-75a7-45fd-ab12-48bdeb074db9")

## ⚠️ Privacy Warning: Sensitive Data in Logs

**Please review all logs and screenshots before attaching them** — they may contain sensitive information such as:

- File paths and project names
- Repository URLs (including private repos)
- Usernames, email addresses, or auth tokens
- Code snippets or file contents from your workspace
- ...

**Remove or redact any sensitive data before posting.** Once submitted, issue contents are publicly visible and cannot be fully retracted.