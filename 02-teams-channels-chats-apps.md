---
layout: default
title: "02 — Teams, Channels, Chats & Apps"
nav_order: 4
description: "MS-700 Domain 2 (20–25%) — Create and manage teams, channel types, messaging policies, and app management for Microsoft Teams."
permalink: /02-teams-channels-chats-apps/
mermaid: true
---

# 02 — Manage Teams, Channels, Chats & Apps <span class="domain-badge">20–25%</span>
> - Based on: *[MS-700 Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ms-700)*
> - 📁 [← Back to Home](/ms-700-study-notes/)

---

## 🗺 Domain Overview

```mermaid
mindmap
  root((Domain 2 20–25%))
    Create & Manage Teams
      Teams Advisor
      Create from Admin Center
      Create from M365 Group
      Team Templates
      Template Policies
      Membership & Roles
      Manage Teams in Admin Center
      Teams Settings
      Privacy & Sensitivity
      Frontline Teams
    Channels & Chats
      Standard Channels
      Private Channels
      Shared Channels
      Channel Settings
      Channel Policies
      Messaging Policies
    Apps
      Org-wide App Settings
      App Setup Policies
      App Assignments
      App Store Customization
      Custom App Upload
      Extensibility Options
```

---

## 🏗️ 2.1 Create and Manage Teams

### Teams Advisor

A built-in tool in the Teams admin center (**Planning** → **Teams Advisor**) that helps plan a Teams rollout. Microsoft Learn still calls it **Advisor for Teams**.
- Runs a **tenant readiness assessment** of your Microsoft 365 environment
- Creates a **Deployment team** with a channel for each workload you choose
- Each workload gets a **Planner plan** of rollout tasks and a **Forms user survey**
- Plans: **Chat, teams, channels, and apps**; **Meetings and conferencing**; **Skype for Business upgrade**; **Education** (education tenants only)
- Requires **Teams, Forms, and Planner** licenses (at least **Microsoft 365 Business Basic**)
- Any licensed user can open it, but only a **Teams Administrator** or **Global Administrator** can open the tenant readiness assessments

### Ways to Create a Team

| Method | Best For |
|--------|---------|
| **Teams admin center** | Admin-created teams for org-wide initiatives |
| **Teams client** | End-user self-service creation |
| **PowerShell** (`New-Team`) | Bulk creation, automation, scripting |
| **Microsoft Graph API** | Application-driven creation, workflows |
| **From existing M365 group** | Converting a group that already has members and content |
| **From existing SharePoint site** | Linking a team to a SharePoint team site |
| **From existing team** | Cloning settings, channels, tabs (not content) |
| **From a template** | Standardized team structures |

### Team Templates

Pre-built structures with predefined channels, tabs, and apps:

| Template | Use Case |
|----------|----------|
| **Manage a Project** | Project planning with Planner tab |
| **Manage an Event** | Event coordination channels |
| **Onboard Employees** | New hire onboarding structure |
| **Organize Help Desk** | Ticketing and support channels |
| **Incident Response** | Crisis management structure |
| **Hospital Ward** | Healthcare team structure |
| **Store Operations** (Retail) | Retail frontline teams |

**Template policies** control which templates are visible to specific users or groups.

### Team Roles and Membership

| Role | Capabilities |
|------|-------------|
| **Owner** | Manage settings, add/remove members, manage channels, delete team |
| **Member** | Post messages, add tabs, create channels (if allowed), use apps |
| **Guest** | Limited access — can post, view files, join meetings (permissions configurable) |

| Setting | Options |
|---------|---------|
| **Max owners** | Recommended: 2–5; max: 100 |
| **Max members** | 25,000 per team |
| **Org-wide team** | Auto-includes all users; max 10,000 members (5 org-wide teams limit) |

### Manage a Team in the Teams Admin Center

**Teams admin center** → **Teams** → **Manage teams** lists every team in the organization, with columns for channel counts, members, owners, guests, privacy, status, sensitivity, group ID, and expiration date.

| Action | How |
|--------|-----|
| **Add a team** | **Add** → name, description, privacy, sensitivity |
| **Edit a team** | **Edit** → name, description, privacy, sensitivity, member permissions, guest permissions, fun settings |
| **Members and channels** | Open the team's profile page → add or remove members and owners, add or remove channels (not the General channel) |
| **Archive** | Select the team → **Archive** (read-only) |
| **Restore a deleted team** | **View deleted teams** → select the team → **Restore** |
| **Renew an expiring team** | Filter by **Expiration date** → select the team → **Renew** |

Changes to Microsoft 365 group settings (name, description, photo, privacy, sensitivity, membership) are recorded in the audit log. Changes to Teams-specific settings are posted to the team's **General** channel.

### Teams Environment Settings

**Teams admin center** → **Teams** → **Teams settings** holds org-wide settings that apply to **every team** in the organization:

| Setting Group | Controls |
|---------------|----------|
| **Notifications and feeds** | Whether suggested feeds can appear in the activity feed |
| **Tagging** | Who can manage tags, suggested and custom tags, whether Shifts can apply tags |
| **Email integration** | Whether users can email a channel address; allowed SMTP domains |
| **Files** | Third-party cloud storage (Citrix files, Dropbox, Box, Google Drive, Egnyte) |
| **Organization** | Whether users see the **Organization** tab (org chart from Entra ID) |
| **Devices** | Surface Hub email, content PIN for Skype for Business users |
| **Search by name** | Scope directory search using an **Exchange address book policy** |
| **Safety and communications** | Role-based chat permissions (supervised chat) |
| **Shared channels** | Link to your support request page for external collaboration |

### Privacy and Sensitivity Settings

| Setting | Options |
|---------|---------|
| **Privacy** | **Private** (invite-only) or **Public** (anyone in org can join) |
| **Sensitivity label** | Controls privacy, guest access, sharing, and unmanaged device access |
| **Team settings** | @mentions, fun features (GIFs, stickers), member permissions |

### Frontline Teams and Experiences

| Feature | Description |
|---------|-------------|
| **Frontline teams** | Deploy teams at scale for shift-based workers |
| **Shifts** | Schedule management built into Teams |
| **Walkie Talkie** | Push-to-talk communication |
| **Tasks** | Centralized task management published from HQ |
| **Approvals** | Request and approve workflows in Teams |

> **⚠️ Exam Caveat:**
> - Creating a team from an **existing M365 group** converts the group but does NOT clone content from another team
> - **Org-wide teams** are limited to **10,000 members** and **5 teams** per tenant
> - **Template policies** determine which templates users see — not which templates exist
> - When a team is created, a **M365 group**, **SharePoint site**, **Exchange mailbox**, and **OneNote notebook** are all auto-provisioned
> - **Teams Advisor** is the study guide's name for **Advisor for Teams** — same tool, under **Planning** in the Teams admin center
> - **Teams settings** are org-wide (every team); **Teams policies** are assigned to users
> - Turning on **Search by name** hides the **Search teams** box and public team listing, and disables `/join`

---

## 💬 2.2 Manage Channels and Chats

### Channel Types Comparison

| Feature | Standard | Private | Shared |
|---------|----------|---------|--------|
| **Visibility** | All team members | Invited members only | Invited members (incl. external) |
| **SharePoint site** | Team's site | Separate site collection | Separate site collection |
| **Owner** | Team owners | Channel creator + designated owners | Channel creator + designated owners |
| **Guest access** | Yes (if team allows) | Yes (if team allows) | No guests — uses B2B direct connect |
| **External users** | Via guest access | Via guest access | Via shared channels (B2B direct connect) |
| **Max per team** | 1,000 (incl. deleted) | 30 | 1,000 |
| **eDiscovery** | Yes | Yes | Yes |
| **DLP** | Yes | Yes | Yes |
| **Tabs/apps** | Full support | Partial (some restrictions) | Partial |

```mermaid
flowchart TD
    DECISION{"Who needs access?"}
    STANDARD["📢 Standard Channel\nAll team members"]
    PRIVATE["🔒 Private Channel\nSubset of team members"]
    SHARED["🔗 Shared Channel\nCross-team or external users"]

    DECISION -->|"All team members"| STANDARD
    DECISION -->|"Subset within team"| PRIVATE
    DECISION -->|"Cross-team or\nexternal org"| SHARED
```

### Channel Settings

| Setting | Description |
|---------|-------------|
| **Moderation** | Control who can start new posts (owners vs. everyone) |
| **Workflows** | Post alerts and webhook messages to the channel (Office 365 connectors were retired in May 2026) |
| **Tabs** | Pin apps, documents, or websites at the top |
| **Auto-favorite** | Show channel in members' channel list by default |

### Teams Policies for Channels

| Policy Area | Controls |
|-------------|----------|
| **Teams policy** | Who can create private channels, who can create shared channels |
| **Channel creation** | Allow/block members from creating channels |
| **Channel sharing** | Allow/block shared channels with external orgs |

### Messaging Policies

| Setting | Description |
|---------|-------------|
| **Delete sent messages** | Allow users to delete their sent messages |
| **Edit sent messages** | Allow users to edit after sending |
| **Read receipts** | User-controlled, on for everyone, or off for everyone |
| **Chat** | Enable or disable private chat |
| **Giphy** | Allow animated GIFs (with content rating filter) |
| **Memes** | Allow meme creation in conversations |
| **Stickers** | Allow stickers in messages |
| **URL previews** | Auto-generate previews for pasted links |
| **Translate messages** | Allow inline message translation |
| **Immersive Reader** | Enable reading mode for accessibility |
| **Priority notifications** | Urgent messages with repeated notifications |
| **Voice messages** | Allow recording voice messages in chat |

> **⚠️ Exam Caveat:**
> - **Private channels** have their own **separate SharePoint site collection** — not the team's default site
> - **Shared channels** do NOT support guest access — they use **B2B direct connect** exclusively
> - **Standard channels** — max 1,000 per team (including soft-deleted channels within 30-day retention)
> - **Private channels** — max 30 per team
> - **Messaging policies** are assigned per-user, not per-team — a user's policy follows them across all teams

---

## 📱 2.3 Manage Apps for Teams

### App Management Hierarchy

```mermaid
flowchart TD
    ORG["🏢 Org-wide App Settings\n(Master switch)"]
    ASSIGN["🔐 App Status & Assignments\n(Allow/Block, who can use each app)"]
    SETUP["📋 App Setup Policies\n(Pin & install apps)"]
    USER["👤 User Experience"]

    ORG --> ASSIGN --> SETUP --> USER
```

### Org-wide App Settings

**Teams admin center** → **Teams apps** → **Manage apps** → **Actions** → **Org-wide app settings**:

| Setting | Description |
|---------|-------------|
| **Tailored apps** | Show the tailored frontline app experience to users with an **F license** |
| **Microsoft apps** | Let users install and use available Microsoft apps by default |
| **Third-party apps** | One control for the availability of all new and existing third-party apps |
| **Custom apps** | Let users install and use available custom (LOB) apps by default |

**Built-in Teams agents** such as **Facilitator** and **Channel Agent** aren't controlled by the Microsoft apps setting. You manage them on **Teams apps** → **Built-in Teams agents**.

### App Assignments (App Centric Management)

**App centric management** replaces **app permission policies**, which are deprecated. Tenants have been migrated automatically since **April 2025**, and a migration **can't be reverted**. Instead of building policies, you set **who can use each app**:

| Availability | Who Gets the App | Old Equivalent |
|--------------|------------------|----------------|
| **Everyone** | All users in the org, new users, and guests | App allowed in the Global permission policy |
| **Specific users or groups** | Only the selected users and groups (no guests) | Custom permission policy |
| **No one** | Nobody | Blocked app |

- Supported groups: **security groups**, **Microsoft 365 groups**, **dynamic membership groups**, **nested groups**, and **distribution lists**
- Auto-migration creates **one security group per custom permission policy** and adds that policy's users to it
- Bulk changes use PowerShell (`Update-M365TeamsApp`); the admin center can't change availability in bulk

### App Setup Policies

Control **how apps appear** for users (**Teams apps** → **Setup policies**):

| Setting | Description |
|---------|-------------|
| **Pinned apps** | Pin apps and set their order in the **app bar**, **messaging extensions**, **meeting extensions**, and **calling extensions** |
| **Installed apps** | Install apps for users (in app centric management tenants, installing moves to the app centric management UI) |
| **User pinning** | Allow users to pin their own apps and change the order (admin pins always come first) |
| **Upload custom apps** | Allow the user to upload custom app packages |

Built-in policies: **Global (Org-wide default)** and **FirstlineWorker** (can't be customized).

### Blocking Apps

| Scope | How |
|-------|-----|
| **One app, whole org** | **Manage apps** → select the app → **Block**, or set its availability to **No one** |
| **One app, some users** | Set availability to **Specific users or groups** |
| **All third-party apps** | **Org-wide app settings** → turn off third-party apps |
| **Microsoft-built apps** | App centric management can also block apps created by Microsoft |

Users can **request** an app that isn't available to them, and admins get a notification to review it.

### App Consent and Permissions

| Consent Type | Description |
|-------------|-------------|
| **Resource-specific consent (RSC)** | App requests permissions to specific team resources |
| **Admin consent** | Admin grants permissions on behalf of all users |
| **User consent** | Users can consent to apps themselves (if allowed by policy) |

### Teams App Store Customization

| Customization | Description |
|---------------|-------------|
| **Logo** | Custom org logo on the app store |
| **Background** | Custom background image |
| **Text color** | Brand-aligned text color |
| **Featured apps** | Highlight specific apps for users |

### Extensibility Options

| Option | Description | Best For |
|--------|-------------|----------|
| **Apps (personal apps & bots)** | Full apps pinned to the app bar, or conversational bots | Q&A, notifications, line-of-business tools |
| **Tabs** | Embed web apps or content in channels/chats | Dashboards, tools, documents |
| **Meeting apps** | Apps that enhance the meeting experience | Polls, Q&A, whiteboarding |
| **Messaging extensions** | Search and share content from within compose box | Quick lookups, ticket insertion |
| **Workflows** | Power Automate flows in Teams, including the **When a Teams webhook request is received** trigger | Approvals, alerts from external services |

**Office 365 connectors** in Teams, including connector-based **incoming webhooks**, were **retired in May 2026**. Use the **Workflows** app instead.

### Upload Custom Apps

| Method | Description |
|--------|-------------|
| **Sideloading** | Upload app package directly (must be enabled in policy) |
| **Org app catalog** | Publish to your organization's app store |
| **Microsoft Partner Center** | Publish to the public Teams app store |

> **⚠️ Exam Caveat:**
> - **Org-wide settings override** app assignments and setup policies — if third-party apps are disabled org-wide, no assignment can allow them
> - **App assignments** (app centric management) control what apps users CAN use; **app setup policies** control what apps users SEE by default
> - **App permission policies** are deprecated — app centric management replaced them, and the migration can't be undone
> - Guests can't use an app that is assigned to **Specific users or groups**, even if they're added to it
> - **Connectors** are retired — if a scenario needs alerts posted to a channel, the answer is **Workflows**
> - **Custom app upload** (sideloading) must be enabled in **both** org-wide settings AND the user's app setup policy
> - **Purchasing apps** from the Teams store requires **admin approval** if cost is involved — configured in the Teams admin center

---

## 📝 Domain 2 — Quick-Reference Scenarios

| Scenario | Answer |
|----------|--------|
| Need a channel visible only to 5 team members | **Private channel** |
| Need to collaborate with users in another M365 tenant | **Shared channel** (B2B direct connect) |
| Standardize new team structures across the org | **Team templates** + template policies |
| Block a specific third-party app for all users | **Manage apps** — block the app (or set availability to **No one**) |
| Make an app available only to the HR department | **App assignment** — availability **Specific users or groups** |
| Post monitoring alerts into a channel | **Workflows** with the Teams webhook trigger (connectors are retired) |
| Plan a Teams rollout with Planner tasks per workload | **Teams Advisor** |
| Rename a team and change it to private as an admin | **Teams admin center** → Manage teams → **Edit** |
| Force-pin an app to every user's sidebar | **App setup policy** — add to pinned apps |
| Prevent users from deleting their sent messages | **Messaging policy** — disable delete sent messages |
| Deploy teams for 5,000 retail store workers | **Frontline team** deployment |
| Convert an existing SharePoint site into a team | Create team **from existing SharePoint site** |
| Allow users to upload custom-built apps | Enable **custom apps** in org-wide settings + app setup policy |
| Control which templates users see when creating teams | **Template policies** |

---

[← Previous: Configure & Manage Environment](/ms-700-study-notes/01-configure-manage-environment/){: .btn .btn-outline .fs-5 .mr-2 }
[Next → 03 — Meetings & Calling](/ms-700-study-notes/03-meetings-and-calling/){: .btn .btn-primary .fs-5 }

[🏠 Home](/ms-700-study-notes/){: .btn .btn-outline .fs-3 }
