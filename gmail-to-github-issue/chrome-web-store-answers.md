# Chrome Web Store answers: Gmail to GitHub Issue

Checked against manifest.json (version 0.1.0, Manifest V3) and src\ on 2026-10-16.

## Store listing
- Name: Gmail to GitHub Issue
- Summary (132 max): Turn any Gmail thread into a GitHub issue in one click.
- Category: Productivity
- Language: English
- Developer: Sonith. Support email: sonythm@gmail.com.
- Privacy policy URL: DECISION: public URL of privacy-policy.md (for example the project's GitHub repo or GitHub Pages).
- Website: DECISION: public repo or page, optional.

### Description
```
Gmail to GitHub Issue adds a "GitHub issue" button next to the subject of the email you are reading. Click it, pick a repository, check the title and body, and create the issue.

WHAT IT DOES
- Prefills the title from the email subject and the body from the latest message, or the whole thread if you choose.
- Adds the sender, the date and a link back to the Gmail thread.
- Lists your repositories and loads each repository's labels as chips. Remembers your last repository.
- You can edit everything before anything is sent.

HOW IT WORKS
You create a GitHub personal access token and paste it into the extension settings. The extension reads the open email only when you click the button, and sends the issue to api.github.com only when you click Create issue. There is no server of ours, no account, no analytics and no ads.

NEEDS
- A GitHub token: fine-grained with Issues read and write plus Metadata read, or a classic token with repo scope.
- Works on mail.google.com in Chrome. GitHub.com only.

PRIVACY
The token and your settings are stored in Chrome's local storage on your computer. The email text you see in the dialog is sent to GitHub when you create the issue, and nowhere else. If the repository is public, the issue is public.
```

## Single purpose statement
Create a GitHub issue from the Gmail email the user is currently reading.

## Permission justifications (manifest.json)

| Permission | Justification to paste |
| --- | --- |
| storage | Stores the user's GitHub token, default repository, default labels, "include whole thread" choice, the last repository used and a short-lived cached list of repository names, in chrome.storage.local. Needed so the user does not re-enter them each time. |
| scripting | Used with chrome.scripting.insertCSS and executeScript to add the extension's own bundled button and dialog script to Gmail tabs that were already open when the extension was installed or updated, and when the user clicks Activate in the popup, so Gmail does not have to be reloaded. Only bundled files are injected and only into mail.google.com tabs. |
| activeTab | DECISION: remove it. Every use is on a mail.google.com tab, which the mail.google.com host permission already covers, so activeTab adds nothing and reviewers flag unused permissions. If you keep it, the justification is: "The popup's Activate button injects the extension into the tab the user is looking at." VERIFY: after removing it, the popup Activate button and automatic injection still work in Gmail. |
| host: https://mail.google.com/* | The content script and styles run on Gmail to add the "GitHub issue" button next to the subject and to read the open thread (sender, date, text) when the user clicks it. Also needed to find open Gmail tabs for injection. |
| host: https://api.github.com/* | The service worker calls the GitHub REST API: GET /user (check the token), GET /user/repos (list repositories), GET /repos/{repo}/labels (labels) and POST /repos/{repo}/issues (create the issue). No other host is contacted. |

No "tabs", "cookies", "history", "webRequest" or "identity" permission is requested. The extension does not use the Gmail API or OAuth.

## Privacy practices tab

| Field | Answer |
| --- | --- |
| Remote code | No. All scripts ship in the package (searched src\ for eval, new Function, importScripts and remote script tags: none). |
| Data collected | Personal communications (the email text, sender and date the user chooses to send). Authentication information (the GitHub token). |
| Not collected | Personally identifiable information beyond the above, health, financial, location, web history, user activity, website content other than the open email. DECISION: confirm "Website content" is not also ticked. Gmail text read from the page is covered by Personal communications. |
| Is data sold? | No |
| Used for purposes unrelated to the single purpose? | No |
| Used for creditworthiness or lending? | No |

Certify all three: not sold to third parties, not used or transferred for unrelated purposes, not used for credit or lending.

The older guide (docs\gmail-extension-publishing-guide.md) says "Website content and Authentication information". "Personal communications" fits the email text better. Use it.

Where the data goes: GitHub, at the user's click, under the user's token. It is not sent to the developer. Stated in privacy-policy.md and in the description.

## Reviewer test instructions
The extension needs a Gmail account and a GitHub token. DECISION: create a throwaway Gmail and a throwaway GitHub account with a private test repository and a fine-grained token (Issues read and write, Metadata read). Put the steps in the "Test instructions" field. Never commit the token.
1. Install, open the settings page, paste the token, click Test, then Save.
2. Open https://mail.google.com, open any email. A "GitHub issue" button appears next to the subject (a floating button appears if Gmail's markup changed).
3. Click it, choose the test repository, click Create issue, then open the link.

## Risks to know before submitting
- Reads email text from the page. Reviewers look closely at this. The policy and description say it clearly and it is limited to the user's click.
- Gmail's page markup can change and break the button. Selectors live in src\gmail.js.
- The permissions in the existing zip (store\gmail-to-github-issue\gmail-to-github-issue-0.1.0.zip) should match manifest.json. VERIFY by rebuilding with package.ps1 after any manifest change (for example removing activeTab).
- PRIVACY.md in the project is shorter than privacy-policy.md and does not say the email text goes into a public repository's issues. Replace it with this policy at the public URL.

## Assets needed
- Icon 128x128 (store\gmail-to-github-issue\icon-512.png exists; the package uses icons\icon128.png).
- At least one 1280x800 screenshot (the guide asks for three: the button, the dialog, the created issue). None are in store\gmail-to-github-issue yet.
- Optional small promo tile 440x280.
- $5 developer registration fee if the account is new.
