# Contributing to MS-700 Study Notes

Thanks for helping keep these notes accurate. They cover **Microsoft Exam MS-700: Managing Microsoft Teams**, and Microsoft Teams changes fast: policies get renamed, settings move from one admin center to another, and features are retired between one revision of the study guide and the next. Reports from people studying with the notes are the best way for me to catch that.

> [!IMPORTANT]
> **This repo takes issues, not pull requests.** Pull requests are turned off because I write every change myself and check it against the official Microsoft documentation, so the notes keep one voice from page to page. If you know exactly how something should read, put your proposed wording in the issue instead. It helps just as much.

---

## Contents

- [Ways to Help](#-ways-to-help)
- [Before You Open an Issue](#-before-you-open-an-issue)
- [Opening an Issue](#-opening-an-issue)
- [Out of Scope](#-out-of-scope)
- [What Happens Next](#-what-happens-next)
- [Code of Conduct](#-code-of-conduct)
- [Security](#-security)

---

## 🙌 Ways to Help

The issue template has five types of report. Pick the one that fits best:

| Type | What it covers | For example |
|------|----------------|-------------|
| 🐞 **Bug** | Something on the site is broken: search, navigation, a dead link or a diagram that won't render | A Mermaid diagram shows up as plain code, search finds nothing for a term that's on the page, or a Microsoft Learn link returns 404 |
| ❌ **Incorrect content** | A fact, table or exam tip in the notes is wrong | A table gives the wrong limit for a team or channel, or an exam tip names the wrong admin center or least-privilege admin role for a task |
| 📅 **Outdated content** | Teams or the exam has changed since the page was written | A policy or setting was renamed or moved to another admin center, a feature was retired, or the study guide was revised and a skill was added, moved or reworded |
| 📱 **Device issue** | A page looks or behaves wrong on a specific device or browser | A wide comparison table can't be scrolled sideways on a phone, or the navigation menu won't open on a tablet |
| 💬 **Something else** | Anything the other types don't cover, including suggestions | A topic that would be clearer as a comparison table or a diagram, such as external access vs. guest access, or an exam trap worth adding to the cheatsheet |

---

## 🔎 Before You Open an Issue

- **Search the existing issues, [open and closed](https://github.com/marcogrimaldi29/ms-700-study-notes/issues?q=is%3Aissue).** If someone has already reported it, add a 👍 reaction, or a comment if you have something new to add, rather than opening a duplicate.
- **Check the study guide's date.** The notes are written against the study guide as updated in **April 2026**, the date shown in the README's domain breakdown. The [official study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ms-700) shows its current revision in the **Skills measured as of** heading, and its **Change log** section lists what moved. If the date there is later than April 2026, include it in the issue so I know which revision to compare against.
- **Check the current docs.** A quick look at the [Microsoft Teams admin documentation](https://learn.microsoft.com/en-us/microsoftteams/) usually confirms whether something has changed, and gives you the source link the issue asks for. If a feature looks different in your own tenant, it may still be rolling out: Microsoft's [roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap) shows its status.
- **One problem per issue.** Separate issues are easier to track, fix and close. A few typos on the same page can share one issue.
- **For a site bug, hard-refresh first** (Ctrl+F5, or Cmd+Shift+R on a Mac), in case your browser is showing an older copy of the page.

---

## 📝 Opening an Issue

1. Open a new issue with the [🐞 Report a problem with the study notes](https://github.com/marcogrimaldi29/ms-700-study-notes/issues/new?template=ISSUE_TEMPLATE.md) template. The **Spotted a mistake?** link at the bottom of every page on the site leads to the same place.
2. Give it a title that names the page and the problem, such as *"03 — Meetings & Calling: Call Queues table uses an old policy name"* rather than *"Mistake on page"*.
3. Fill in the template's sections, and delete any that don't apply.

> [!TIP]
> To link straight to a section, hover over its heading on the site and click the link icon that appears to the left of it. Your browser's address bar then shows the section's address, ready to copy.

### What Makes a Report Easy to Fix

- **A link to the exact section**, not just the page
- **The text as the notes have it**, quoted, so I can find it even if the page has changed since
- **An official source** for any content change, ideally a Microsoft Learn page or the study guide. A report without one can take longer, because I check every change against the documentation before it goes in
- **Where you saw the setting**, if the report is about one: the Teams admin center, the Microsoft 365 admin center, the Microsoft Entra admin center or PowerShell. The same feature can look different in each
- **For bugs and device issues:** the steps to reproduce it, what you expected and what happened instead, your device, operating system and browser, and a screenshot if it shows the problem
- **Your proposed wording**, if you have it. With pull requests turned off, this is the most direct way to suggest an edit

---

## 🚫 Out of Scope

To keep the notes accurate and the issue tracker useful, please don't open issues for:

- **Live exam content.** Questions, answers or topics remembered from a real exam break the non-disclosure agreement you accept before the exam and [Microsoft's exam security policy](https://learn.microsoft.com/en-us/credentials/support/exam-and-assessment-lab-security-policies). I'll close issues that include them and remove the content.
- **Exam booking, scores or retakes.** [Microsoft Credentials support](https://learn.microsoft.com/en-us/credentials/support/help) can help with those.
- **Help with your own tenant, or with Teams itself.** For a policy that won't apply, a licensing question, call quality in your organization or a bug in Teams, ask on [Microsoft Q&A](https://learn.microsoft.com/en-us/answers/tags/777/office-teams) or [open a support request](https://learn.microsoft.com/en-us/microsoft-365/admin/get-help-support) from the Microsoft 365 admin center.
- **Anything private.** Issues are public, so leave out tenant names and IDs, domains, user names, phone numbers, meeting links and call data, including in screenshots.
- **Unofficial sources.** Practice-test sites, exam dump sites and answers from AI chat tools aren't accepted as the source for a content change.
- **Promotion.** I don't add links to courses, products or services, affiliate links or paid placements.
- **Security vulnerabilities.** Please [report these privately](https://github.com/marcogrimaldi29/ms-700-study-notes/security/advisories/new), as the [security policy](SECURITY.md) describes, not in a public issue.

---

## 🔄 What Happens Next

- I maintain these notes on my own, in my spare time, so replies are best effort and there's no fixed response time.
- I check each report against the official documentation. If I need more detail, I'll ask on the issue, so keep an eye on your GitHub notifications.
- When a fix goes in, I close the issue with a note on what changed. The live site updates shortly after.
- If nothing changes, I close the issue with the reason, such as out of scope, can't be verified, or already correct.
- An issue left waiting for a reply may be closed after a while. Comment with the missing details and I can reopen it.

---

## 🤝 Code of Conduct

By opening, commenting on or reacting to issues here, you agree to follow the [Code of Conduct](CODE_OF_CONDUCT.md). Comments that are abusive, spam or share live exam content may be hidden, edited or locked.

---

## 🔒 Security

Found a security problem with the site or this repo? Please don't report it in a public issue. Use the [private report form](https://github.com/marcogrimaldi29/ms-700-study-notes/security/advisories/new) instead, so only you and I can see it. The [security policy](SECURITY.md) has the details.

---

If the notes helped you, the README's [💚 Support](https://github.com/marcogrimaldi29/ms-700-study-notes#-support) section has a couple of ways to show it. Thanks for helping make them better for the next MS-700 candidate.
