# Security Policy

MS-700 Study Notes is a static site built with Jekyll and the Just the Docs theme, and published to GitHub Pages. It has no accounts, no sign-in and no forms, it sets no cookies, and it stores nothing in your browser. Search runs entirely in your browser against an index downloaded from the site, so what you type in the search box isn't sent anywhere. Diagrams are drawn by Mermaid, loaded from the jsDelivr CDN, and page views are counted with cookieless analytics through [Umami](https://umami.is/). That leaves a small attack surface, but security reports are still welcome, and I'd rather hear about a problem privately before it's public.

---

## 🛡️ Supported Versions

There are no releases. Only what's live is maintained.

| Version | Supported |
|---------|-----------|
| The live site at [marcogrimaldi29.com/ms-700-study-notes](https://marcogrimaldi29.com/ms-700-study-notes/) and the `main` branch | ✅ |
| Older commits, forks and copies hosted elsewhere | ❌ |

---

## 📮 Reporting a Vulnerability

**Please don't open a public issue or comment.** Report it privately through GitHub instead: open the repo's **Security** tab and choose **Report a vulnerability**, or go straight to the [private report form](https://github.com/marcogrimaldi29/ms-700-study-notes/security/advisories/new). Only you and I can see the report, and we can discuss and fix the problem there before anything is made public.

It helps to include:

- The affected URL, or the file in this repo
- What the problem is and what someone could do with it
- The steps to reproduce it, or a short proof of concept

Please don't include real secrets, credentials or anyone else's personal data in the report, and only test against things you own.

If you can't use GitHub, send me a private message on [LinkedIn](https://www.linkedin.com/in/marco-grimaldi29/) instead, starting it with **"Security: MS-700 Study Notes"** so it's easy to spot.

---

## 🎯 Scope

**In scope:**

- The published site, including its pages, scripts, styles and assets
- This repository's source and its GitHub Actions workflow
- A dependency version used here that has a known vulnerability, such as a Ruby gem in the `Gemfile`, a GitHub Action, or the Mermaid version set in `_config.yml`

**Out of scope:**

- **Microsoft Teams, Microsoft 365 or any other Microsoft product.** Report these to the [Microsoft Security Response Center](https://msrc.microsoft.com/create-report).
- **A vulnerability in Jekyll, Just the Docs, Mermaid, Lunr or another dependency itself.** Report it to that project. If this repo uses an affected version, let me know as well.
- **HTTP response headers set by GitHub Pages.** The repo can't change them.
- **Automated scanner output** with no demonstrated impact on this site.
- **An insecure pattern in the notes**, such as a PowerShell sample that signs in with a plain-text password, or a tip that assigns a broader admin role than the task needs. That's a content issue, so it's welcome as a public issue: see the [contributing guide](CONTRIBUTING.md).

---

## ⏱️ What to Expect

I maintain this repo on my own, so responses are best effort. I'll confirm I've received your report, keep you updated in the private report while I look into it, and let you know when it's fixed. If you'd like credit, say so and I'll credit you in the security advisory or the fix.

Dependabot alerts and security updates are turned on for this repo, so known vulnerabilities in its dependencies are usually flagged and patched without a report.
