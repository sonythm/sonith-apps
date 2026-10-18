# Privacy Policy: Gmail to GitHub Issue

Developer: Sonith. Contact: sonythm@gmail.com. Effective date: 2026-10-16.

Gmail to GitHub Issue is a Chrome extension. It adds a "GitHub issue" button to Gmail so you can turn the email you are reading into a GitHub issue.

## Summary
- No server of ours. We do not receive your data.
- The extension reads an email only when you click "GitHub issue".
- The email text goes only to GitHub, only when you click "Create issue", under your own token.
- No ads, no analytics, no tracking, no remote code.

## What the extension reads
- On Gmail pages (mail.google.com) it looks at the page to find the subject of the open email, so it can place the button. It does not read or store your inbox.
- When you click "GitHub issue", it reads the open thread on the page: sender name and address, date and text of the latest message, or of every message in the thread if you tick "Include the whole thread". It fills the issue dialog with that text so you can edit it.
- It does not use the Gmail API. It does not read other emails, labels, contacts or attachments.

## What it sends, and to whom
- When you click "Create issue", the title, body (the email text you see in the dialog, with the sender, date and a link to the Gmail thread) and the labels you picked are sent to the GitHub API at api.github.com, into the repository you chose.
- Other GitHub requests: check your token (/user), list your repositories (/user/repos), list a repository's labels.
- Requests carry your GitHub token in an Authorization header.
- Nothing is sent anywhere else. If the repository is public, the issue text is public. Check what you send.
- GitHub handles this data under its own privacy statement.

## What it stores
In Chrome's local extension storage on your computer (chrome.storage.local):
- Your GitHub token and username.
- Your settings: default repository, default labels, "include whole thread".
- The last repository you used and a cached list of your repository names (refreshed after 10 minutes).

Nothing is stored on a server of ours. The token is not synced by the extension. Chrome handles the storage on your device.

## Permissions
- storage: to keep the token and settings above.
- scripting: to put the button and dialog into Gmail tabs that were already open when the extension was installed or updated.
- Access to mail.google.com: to add the button and read the open email when you ask.
- Access to api.github.com: to create the issue and list repositories and labels.

## Sharing
We do not sell your data, share it with third parties, or use it for advertising, credit or lending decisions.

## Removing your data
- Settings page: clear the token field and click Save. Your username and cached repository names stay until you uninstall.
- Uninstall the extension. Chrome deletes its stored data.
- Revoke the token at github.com/settings/tokens.
- Issues you created stay on GitHub. Delete them there.

## Children
Not directed at children under 13.

## Changes
A changed policy will be published at the same address with a new effective date.

## Contact
sonythm@gmail.com
