---
layout: default
title: "04 — Monitor, Report & Troubleshoot"
nav_order: 6
description: "MS-700 Domain 4 (15–20%) — Monitor voice and meeting quality, usage reporting, alert rules, client-side troubleshooting, and diagnostics for Microsoft Teams."
permalink: /04-monitor-report-troubleshoot/
mermaid: true
---

# 04 — Monitor, Report & Troubleshoot Teams <span class="domain-badge">15–20%</span>
> - Based on: *[MS-700 Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ms-700)*
> - 📁 [← Back to Home](/ms-700-study-notes/)

---

## 🗺 Domain Overview

```mermaid
mindmap
  root((Domain 4 15–20%))
    Monitor & Report
      Call Quality Dashboard
      Real-Time Analytics
      Usage Reports
      Alert Rules
      Team Activity
      App Usage
      Active Users
      Per-Meeting Metrics
      Storage Usage
      Guest Access Reports
      Network Connectivity
      Feedback Policies
    Troubleshoot
      Client-Side Logs
      Cache Clearing
      Self-Help Diagnostics
      Installation Issues
      Update Issues
      Teams Client Health
      Sign-In Issues
      Copilot & AI Issues
      Meeting Join Issues
```

---

## 📊 4.1 Monitor and Report on Teams

### Call Quality Dashboard (CQD)

The primary tool for monitoring **voice and meeting quality** across the tenant:

| Feature | Description |
|---------|-------------|
| **Access** | cqd.teams.microsoft.com or Teams admin center |
| **Data** | Call and meeting quality metrics — up to 30 days |
| **Building data** | Upload building/subnet data for location-based reporting |
| **Reports** | Pre-built and custom reports on audio, video, and screen sharing quality |
| **Dimensions** | Filter by date, user, building, network, client, device |

### Key CQD Metrics

| Metric | Good Threshold | Description |
|--------|---------------|-------------|
| **Packet loss** | < 1% | Percentage of packets lost during transmission |
| **Jitter** | < 30 ms | Variation in packet arrival time |
| **Latency (round-trip)** | < 100 ms | Time for packet to travel to destination and back |
| **Audio poor stream rate** | < 3% | Percentage of audio streams classified as poor |

### Real-Time Analytics

Available in **Teams admin center** → Analytics & reports → Real-time analytics:
- View **active meetings** happening now
- See per-participant quality (audio, video, screen sharing)
- Identify issues during live meetings
- Available for meetings with **3+ participants**

### Per-User Call Analytics

| Role | Access Level |
|------|-------------|
| **Teams Communications Support Specialist** | Per-user data only — sees individual user call history |
| **Teams Communications Support Engineer** | All user data — advanced troubleshooting and analytics |
| **Teams Administrator** | Full access to all analytics |

```mermaid
flowchart TD
    ISSUE["❓ Quality Issue\nReported"]
    WHO{"Who is\ninvestigating?"}
    SPEC["👤 Support Specialist\n(Per-user only)"]
    ENG["🔍 Support Engineer\n(All users)"]
    ADMIN["🔧 Teams Admin\n(Full access)"]
    
    CQD["📊 Call Quality\nDashboard\n(Tenant-wide trends)"]
    PERUSER["👤 Per-User\nCall Analytics\n(Individual sessions)"]
    REALTIME["⚡ Real-Time\nAnalytics\n(Live meetings)"]

    ISSUE --> WHO
    WHO --> SPEC --> PERUSER
    WHO --> ENG --> PERUSER
    WHO --> ADMIN
    ADMIN --> CQD
    ADMIN --> PERUSER
    ADMIN --> REALTIME
```

### Usage Reports

Available in **Teams admin center** → Analytics & reports → Usage reports:

| Report | Shows |
|--------|-------|
| **Teams usage** | Active users, active teams, guests, messages, channels |
| **Team activity** | Per-team metrics — messages, active users, guests |
| **App usage** | Which apps are installed and actively used |
| **Active users** | Daily, weekly, monthly active users |
| **Per-meeting metrics** | Duration, participants, audio/video quality per meeting |
| **Storage usage** | How much storage each team is consuming |
| **Guest access** | Guest activity, guest count, teams with guests |
| **PSTN usage** | Call minutes, cost, number usage (if using Calling Plans) |
| **PSTN blocked users** | Users blocked from making PSTN calls |

### M365 Admin Center Reports

Additional Teams reporting available via **M365 admin center** → Reports → Usage:
- **Microsoft 365 usage analytics** — Power BI template for deeper analysis
- Cross-service reports (Teams + Exchange + SharePoint activity)

### Alert Rules

Configure notifications for specific events in **Teams admin center** → Notifications & alerts:

| Alert Type | Trigger |
|-----------|---------|
| **Device health** | Teams device goes offline or has issues |
| **Meeting quality** | Audio quality drops below threshold |
| **External access** | Changes to external access settings |
| **App events** | App installation or permission changes |

### Monitor Team Creation and Deletion

| Method | Description |
|--------|-------------|
| **Audit log** | Microsoft Purview → Audit — search for TeamCreated, TeamDeleted events |
| **Activity log** | Teams admin center — recent admin actions |
| **Microsoft Graph** | Query change notifications for group lifecycle events |
| **PowerShell** | `Get-Team` with filters for creation date |

### Feedback Policies

| Setting | Description |
|---------|-------------|
| **Give feedback** | Allow/block users from sending feedback to Microsoft |
| **Surveys** | Allow/block in-app surveys after calls/meetings |
| **Log collection** | Allow users to send logs with feedback |
| **Feature suggestions** | Allow/block feature suggestion submissions |

> **⚠️ Exam Caveat:**
> - **CQD** shows tenant-wide trends; **per-user call analytics** shows individual session details — know when to use each
> - **Building/subnet data** must be uploaded to CQD for location-based quality reporting
> - **Support Specialist** role can ONLY see per-user data (they must search by user) — they cannot see tenant-wide reports
> - **Real-time analytics** requires meetings with **3+ participants** — not available for 1:1 calls
> - **Usage reports** have a data latency of **24–48 hours** — they are not real-time

---

## 🔧 4.2 Troubleshoot Audio, Video, and Client Issues

### Client-Side Logs

| Log Type | Location (Windows) | Purpose |
|----------|-------------------|---------|
| **Desktop client logs** | `%appdata%\Microsoft\Teams\logs.txt` | General client activity and errors |
| **Media logs** | `%appdata%\Microsoft\Teams\media-stack\*.blog` | Audio, video, and screen sharing diagnostics |
| **Debug logs** | Ctrl+Alt+Shift+1 in Teams | Generate debug log package |
| **Calling logs** | Exported from call history | Per-call quality details |

### Clear Teams Client Cache

Steps to clear the cache (Windows):
1. Fully quit Teams (right-click tray icon → Quit)
2. Navigate to `%appdata%\Microsoft\Teams`
3. Delete contents of: `Cache`, `blob_storage`, `databases`, `GPUcache`, `IndexedDB`, `Local Storage`, `tmp`
4. Restart Teams

### Self-Help Diagnostics

Available in **Microsoft 365 admin center** → Support → Run diagnostics:

| Diagnostic | Tests |
|-----------|-------|
| **Teams sign-in** | Validates user account, license, and service health |
| **Teams meeting** | Checks meeting policies, licenses, and connectivity |
| **Teams calendar** | Validates Exchange mailbox and calendar integration |
| **Teams call quality** | Analyzes recent call quality data for a user |
| **Teams presence** | Checks presence status and coexistence mode |

### Client Installation and Update Issues

| Issue | Troubleshooting Steps |
|-------|----------------------|
| **Installation fails** | Check .NET prerequisites, run as admin, check proxy/firewall |
| **Updates not applying** | Verify update policy, check network connectivity to CDN |
| **New Teams migration** | Check update policy settings, OS requirements |
| **Side-by-side install** | Classic Teams and new Teams can coexist during transition |

### Teams Client Health in the Teams Admin Center

The **Teams client health** dashboard (Teams admin center → **Teams client health**) gives admins data, insights, and fixes for Teams app problems before users escalate them:

| Area | Shows |
|------|-------|
| **Client health** widget | Devices with **crashes** and **launch failures** per day over the last **28 days** (Windows non-VDI and Mac) |
| **Top issues** | Devices that reported **crashes**, **launch failures**, and **update failures** in the last 7 and 28 days |
| **Issues** table | Each issue with an **Insight** (likely cause), impacted devices and users, and **Suggested actions** |
| **Issue details** | Affected users with client version, **version status** (for example **Outdated**), update ring, and device |

For a single user, go to **Users** → **Manage users** → select the user → **Client health** tab. There you can **Request client logs** to collect diagnostic logs remotely without interrupting the user (Windows non-VDI and Mac). The Global Administrator, Teams Administrator, Teams Communications Support Engineer, and Teams Communications Support Specialist roles can use it.

| Insight Example | Fix |
|-----------------|-----|
| **Launch failure** — can't reach or timed out waiting for Teams endpoints | Check firewall and proxy rules for Teams endpoints |
| **Launch failure** — script error | User signs out of Teams and back in |
| **Launch failure** — unsupported OS version | Update Windows or macOS to a supported version |
| **Client crash** | Make sure antivirus and DLP tools allow Teams and WebView2 |
| **Update failure** — root cause undetermined | Force an update, collect Teams and Windows logs, contact support |
| **VDI optimization failure** | Check the error code against the VDI troubleshooting table |

### Sign-In Issues

```mermaid
flowchart TD
    SIGNIN["❌ Sign-in Failed"]
    LICENSE{"Has Teams\nlicense?"}
    NOLICENSE["Assign Teams\nlicense"]
    CA{"Conditional\nAccess blocking?"}
    CAFIX["Review CA policy\nin Entra admin center"]
    CACHE{"Stale\ncache?"}
    CLEAR["Clear Teams\nclient cache"]
    NETWORK{"Network\nblocking?"}
    NETFIX["Check proxy/firewall\nAllow Teams URLs"]
    SUPPORT["Escalate to\nMicrosoft Support"]

    SIGNIN --> LICENSE
    LICENSE -->|No| NOLICENSE
    LICENSE -->|Yes| CA
    CA -->|Yes| CAFIX
    CA -->|No| CACHE
    CACHE -->|Maybe| CLEAR
    CLEAR --> NETWORK
    NETWORK -->|Yes| NETFIX
    NETWORK -->|No| SUPPORT
```

| Common Cause | Resolution |
|-------------|-----------|
| **No Teams license** | Assign license in M365 admin center |
| **Conditional Access** | Review policies in Entra — may block non-compliant devices |
| **Cached credentials** | Clear Teams cache and re-sign in |
| **Proxy/firewall** | Allow Teams URLs and IPs (see Microsoft 365 URLs and IP address ranges) |
| **SSO issues** | Check Entra ID sign-in logs for error codes |
| **MFA enrollment** | User may need to complete MFA registration |

### Troubleshoot Microsoft 365 Copilot and AI Experiences in Teams

The **Copilot** setting in the meeting policy (**Meetings** → **Meeting policies** → **Recording & transcription**) sets what organizers can choose in their meeting options:

| Policy Value | PowerShell (`-Copilot`) | Organizer's Default |
|--------------|-------------------------|---------------------|
| **On** | `Enabled` | **Only during the meeting** — can change to During and after, or Off |
| **On with saved transcript required** *(default)* | `EnabledWithTranscript` | **During and after the meeting** — can't be changed |
| **On with transcript saved by default** | `EnabledWithTranscriptDefaultOn` | **During and after the meeting** — can change to Only during, or Off |
| **Off** | `Disabled` | **Off** — can change to Only during, or During and after |

- **Only during the meeting** uses temporary speech-to-text data that isn't saved after the meeting
- **During and after the meeting** needs someone to **start transcription**
- When an organizer sets Copilot to **Off** for a meeting, **recording and transcription are also turned off**

| Issue | Check |
|-------|-------|
| **Copilot not available at all** | User has a **Microsoft 365 Copilot** license |
| **Copilot missing in one meeting** | Meeting is **end-to-end encrypted** (Copilot isn't supported) or the organizer set Copilot to **Off** |
| **Copilot works only during the meeting** | Meeting option is **Only during the meeting** — start a transcript to keep Copilot available afterward |
| **Copilot can't be used although the policy allows it** | Transcription policy is **Off** and the option is **During and after the meeting** — someone allowed to transcribe must start transcription |
| **No intelligent recap** | User has **Teams Premium** or **Microsoft 365 Copilot**, and **transcription** is allowed; allow **recording** too for the full recap (speakers, topics, chapters) |
| **Recap missing with no transcript** | **Intelligent recap without saving transcripts** works for **scheduled meetings** only, needs a Copilot license, and can be turned off with `-AllowIntelligentRecap` |
| **Facilitator missing** | Copilot license, Facilitator availability on **Teams apps** → **Built-in Teams agents**, and **Loop experiences in Teams** turned on |

### Meeting Join and Feature Issues

| Issue | Troubleshooting |
|-------|----------------|
| **Cannot join meeting** | Check meeting policy, anonymous join settings, lobby policy |
| **No audio/video** | Check device permissions, media ports (UDP 3478–3481), drivers |
| **Cannot share screen** | Check meeting policy (content sharing), bandwidth |
| **Recording unavailable** | Check recording policy, OneDrive/SharePoint storage quota |
| **Missing features** | Check Teams client version, license, meeting policy |
| **Lobby issues** | Review meeting policy lobby bypass settings |

> **⚠️ Exam Caveat:**
> - **Debug logs** are generated by pressing **Ctrl+Alt+Shift+1** — know this keyboard shortcut
> - **Self-help diagnostics** are in the **M365 admin center**, not the Teams admin center
> - **Cache clearing** resolves many client issues — it's a standard first troubleshooting step
> - **Sign-in log analysis** should be done in **Entra admin center** → Sign-in logs
> - **Copilot doesn't always need a saved transcript** — **Only during the meeting** uses temporary speech-to-text; a transcript is needed only to use Copilot **after** the meeting
> - **Copilot isn't available in end-to-end encrypted meetings**
> - **Teams client health** is in the **Teams admin center**; **self-help diagnostics** are in the **M365 admin center**

---

## 📝 Domain 4 — Quick-Reference Scenarios

| Scenario | Answer |
|----------|--------|
| Users report poor audio quality across the org | **Call Quality Dashboard** (CQD) — check audio poor stream rate |
| Manager needs to see an employee's call quality | **Per-user call analytics** (Support Specialist or Engineer role) |
| Monitor a live all-hands meeting for quality | **Real-time analytics** in Teams admin center |
| Find out which Teams apps are most used | **Usage reports** → App usage |
| Investigate who deleted a team | **Audit log** in Microsoft Purview — search TeamDeleted |
| User cannot sign in to Teams on a new device | Check **Conditional Access** policies + **Teams license** |
| Teams client is slow and glitchy | **Clear Teams client cache** |
| Generate a debug log for Microsoft support | Press **Ctrl+Alt+Shift+1** in Teams |
| CQD shows poor quality for a specific building | Upload **building/subnet data** to CQD, then filter by building |
| Intelligent recap doesn't appear | Verify a **Teams Premium** or **Copilot** license and that **transcription** is allowed in the meeting policy |
| Copilot is greyed out in one meeting only | Check for **end-to-end encryption** or the organizer setting Copilot to **Off** |
| Teams fails to launch on many devices | **Teams client health** dashboard → Issues → check the **Insight** |
| Need logs from a user's client without disturbing them | User's **Client health** tab → **Request client logs** |

---

[← Previous: Meetings & Calling](/ms-700-study-notes/03-meetings-and-calling/){: .btn .btn-outline .fs-5 .mr-2 }
[Next → 05 — Quick Reference Cheatsheet](/ms-700-study-notes/05-quick-reference-cheatsheet/){: .btn .btn-primary .fs-5 }

[🏠 Home](/ms-700-study-notes/){: .btn .btn-outline .fs-3 }
