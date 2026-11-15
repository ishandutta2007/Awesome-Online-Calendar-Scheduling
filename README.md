# Awesome-Online-Calendar-Scheduling

# Awesome Online Calendar & Scheduling

> A curated list of top Online Calendar and Scheduling platforms — both SaaS/Hosted commercial solutions and open-source alternatives for managing personal calendars, coordinating meetings, and self-hosting scheduling pages.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Google Calendar](#google-calendar)
  - [Microsoft Outlook Calendar](#microsoft-outlook-calendar)
  - [Calendly](#calendly)
  - [Apple Calendar](#apple-calendar)
  - [Fantastical](#fantastical)
- [Open-Source Software](#-open-source-software)
  - [Cal.com](#calcom)
  - [Tymeslot](#tymeslot)
  - [Radicale](#radicale)
  - [DAVx⁵](#davx⁵)
  - [Tidetime](#tidetime)
  - [Calnode](#calnode)
  - [Calrs](#calrs)
  - [justbookmycal](#justbookmycal)
  - [OpenReception](#openreception)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Online Calendar and Scheduling platforms. These are not open-source but are included as reference points for feature comparison.

### Google Calendar
**Type:** Collaborative calendar with scheduling pages
Google Calendar provides event management, shared calendars, and appointment scheduling pages, integrated with Gmail and Google Workspace. It is the most widely adopted cloud calendar, with real-time sync across devices and native mobile apps.

### Microsoft Outlook Calendar
**Type:** Enterprise calendar within Microsoft 365
Outlook Calendar provides event management, shared calendars, and meeting scheduling with deep integration into Exchange, Teams, and the Microsoft 365 ecosystem. It is the default choice for Microsoft-centric organizations.

### Calendly
**Type:** Meeting scheduling platform with booking pages
Calendly popularized the self-service booking page model, allowing others to book time based on your availability without back-and-forth emails. It is the primary commercial reference for open-source alternatives like Cal.com, Tymeslot, and Tidetime.

### Apple Calendar
**Type:** Native calendar for Apple ecosystem
Apple Calendar provides event management and CalDAV sync across Apple devices, with iCloud integration. It is the natural choice for users within the Apple ecosystem, supporting standard CalDAV for third-party servers.

### Fantastical
**Type:** Premium calendar app with natural language parsing
Fantastical is a polished calendar client for Apple platforms known for its natural language event creation and menu bar access. It supports multiple calendar services and is positioned for users wanting a premium client experience.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Online Calendar and Scheduling tools. The open-source ecosystem spans **full scheduling platforms**, **CalDAV servers**, **Android sync clients**, and **lightweight booking pages**.

### Cal.com
**Stack:** TypeScript / Next.js / PostgreSQL / Prisma | **License:** AGPLv3 (open-core)
Cal.com is the most widely adopted open-source Calendly alternative, with a codebase that is open-source and self-hostable [citation:6]. It provides booking pages, team scheduling, calendar sync, video conferencing integration, and workflows. The project is built on Next.js with Prisma and PostgreSQL, and can be deployed via Docker (though the team notes Docker installations are supported by the user, not officially by Cal.com) . A managed cloud offering is also available, with the open-source core remaining free for self-hosting.
**Best for:** Teams wanting a mature, feature-rich Calendly replacement with strong community adoption and the option to self-host or use the managed cloud.

### Tymeslot
**Stack:** Elixir / Phoenix LiveView / PostgreSQL | **License:** Open Source (self-hostable)
Tymeslot is an open-source, self-hostable alternative to Calendly and Cal.com, built with Elixir and Phoenix LiveView [citation:2]. Key features include:
- **Four booking themes** (Quill, Rhythm, Paper, Folio) with custom colours and white-label options
- **Two-way calendar sync** with Google, Outlook, iCloud, and any CalDAV server (Nextcloud, Radicale, Zimbra, Baikal), with conflict checks across all calendars
- **Automatic video rooms** on Google Meet, Teams, Zoom, Jitsi, MiroTalk, kMeet, or Nextcloud Talk
- **Branded email templates** with `.ics` invites and no-login cancel/reschedule links
- **Webhooks** (HMAC-signed) for n8n, Zapier, and Make
- **Stripe Connect** optional paid bookings, fee-free for self-hosters

Self-hosting requires a single Docker container with PostgreSQL included. The same code powers both the self-hosted and managed cloud versions, with no gated features [citation:2].
**Best for:** Teams wanting a modern, full-featured Calendly alternative with strong CalDAV support and a clean self-hosting story.

### Radicale
**Stack:** Python | **License:** GPL-3.0
Radicale is a simple CalDAV and CardDAV server designed to be lightweight, easy to install, and easy to configure, with few dependencies and out-of-the-box functionality [citation:3][citation:8]. It runs on most UNIX-like platforms (Linux, BSD, macOS) and Windows, and is known to work with Evolution, Lightning, iPhone, and Android clients. It is a **calendar server** rather than a scheduling platform—it stores and syncs calendars but does not provide booking pages or availability logic.
**Best for:** Individuals and teams wanting a minimal, dependency-light CalDAV server to self-host their own calendar data, particularly for syncing with existing clients.

### DAVx⁵
**Stack:** Kotlin / Android | **License:** GPLv3
DAVx⁵ is an open-source CalDAV/CardDAV synchronization app for Android, supporting contacts, calendars, and tasks sync with self-hosted servers [citation:4][citation:9]. It provides live WebDAV file access over the Storage Access Framework, is privacy-focused, and supports easy setup with automatic configuration. It is the standard client for connecting Android devices to self-hosted CalDAV servers like Radicale or Nextcloud.
**Best for:** Android users wanting to sync their calendars and contacts with a self-hosted CalDAV/CardDAV server, accepting the app's focus on sync rather than standalone calendar management.

### Tidetime
**Stack:** Next.js 16 / React 19 / TypeScript / PostgreSQL / Drizzle | **License:** Open Source (self-hosted)
Tidetime is a self-hosted appointment scheduling system for a single company with multiple services and multiple providers [citation:10]. Key features include:
- **Services and providers** with per-service duration, location, intake questions, and optional manual confirmation
- **Provider assignment** where customers can choose a provider or let the system assign the least-busy available one, with bookings created inside a database transaction to prevent double-booking
- **Availability management** with per-provider weekly hours and named schedules
- **Public booking pages** in the customer's own time zone
- **Calendar sync** with Google Calendar and Microsoft 365 for busy-time conflict checks, plus automatic Google Meet link generation
- **Webhooks** (signed, Zapier-compatible) for booking events
- **Branding and custom domain** with automatic HTTPS certificate renewal

Deploys via Docker and Caddy. There is no hosted plan, no per-seat pricing, and no third-party analytics [citation:10].
**Best for:** Small companies wanting a self-hosted, multi-provider booking system with strong calendar sync and no SaaS dependency, accepting the Next.js/PostgreSQL deployment.

### Calnode
**Stack:** Go | **License:** Apache-2.0 (per GitHub topic)
Calnode is a lean, self-hostable scheduling engine built as a single Go binary with SQLite, positioned as a Calendly/Cal.com alternative [citation:6]. Key features include:
- **API-first and MCP-native**: a Model Context Protocol server is compiled into the binary, exposing tools like `get_available_slots`, `create_booking`, and `reschedule_booking`
- **OAuth 2.1 authorization server** for agent connections, plus API keys for scripts
- **HMAC-signed webhooks** for booking lifecycle events
- **Conversational booking** on the booking page itself, with the deterministic engine computing slots (the model never invents times)
- **Google/Microsoft calendar sync** and meeting link generation

It is positioned for teams wanting a small, fast, scriptable, and AI-ready scheduler rather than a feature-maximal platform [citation:12].
**Best for:** Developers and AI-forward teams wanting a lightweight, MCP-native scheduling engine with a single binary and no heavy dependencies.

### Calrs
**Stack:** Rust | **License:** Open Source
Calrs is a fast, self-hostable scheduling platform written in Rust, positioned as a Cal.com alternative [citation:11]. Key features include:
- **Team scheduling** with round-robin (least-busy assignment) or collective (all members must be free) modes
- **Unified Teams** created from OIDC groups or hand-picked users, with public or private visibility
- **Invite links** with tokenized access, expiration, and usage limits for internal or private event types
- **CalDAV calendar sync** for conflict checks, with multi-timezone team support
- **Availability overrides** for specific dates or custom hours

It uses local accounts with Argon2 hashing and supports OIDC/SSO via Keycloak or Authentik [citation:11].
**Best for:** Teams wanting a Rust-based, performance-focused scheduling platform with strong team and invite-link features, accepting a newer ecosystem.

### justbookmycal
**Stack:** Python / Flask | **License:** Open Source (PyPI)
justbookmycal is a lightweight, self-hosted booking page that checks your live calendar via ICS feeds [citation:5]. Key characteristics:
- **ICS feed-based availability**: reads busy times from any published ICS feed, treating `TRANSP:TRANSPARENT` and `CANCELLED` events as free
- **Cache with fallback**: caches feeds and uses the last copy (up to 24 hours old) if a feed cannot be loaded, rather than risking double booking
- **Email invitations** with `.ics` attachments, using a system address as organizer so both parties receive proper invitations
- **Private links** for each side, derived from `SECRET_KEY` and the booking, with only hashes stored in the database
- **Jitsi video links** by default, with configurable templates

It is designed for a single person's booking page rather than team scheduling [citation:5].
**Best for:** Individuals wanting a minimal, self-hosted booking page that works with any ICS feed, accepting a narrower feature set than full platforms.

### OpenReception
**Stack:** (Check repository) | **License:** AGPL v3
OpenReception is an open-source appointment scheduling system specifically designed for **doctor's offices**, positioned as a data-protection-friendly alternative to commercial systems [citation:15]. Key features include:
- **End-to-end encryption** with cryptographic keys exclusively on users' devices—even administrators cannot view sensitive information
- **Dashboard** for practices to manage appointments, absences, and availabilities
- **Patient booking** without sharing data with large platforms
- **Integration interfaces** for existing practice management systems (PVS), with publicly documented APIs
- **Quantum-resistant encryption** considerations for long-term security

Managed hosting starts at €69 net per month, with some features reserved for a premium version. Development was funded by the German Federal Ministry for Research, Technology and Space [citation:15].
**Best for:** Medical practices and healthcare organizations needing a privacy-first, end-to-end encrypted booking system, accepting a healthcare-specific focus.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Booking Pages | CalDAV Sync | Self-Hosted | Best For |
|----------|---------|-------|---------------|-------------|-------------|----------|
| **Google Calendar** | Proprietary | Cloud | ✅ Appointment | ❌ | ❌ | Universal calendar + booking |
| **Calendly** | Proprietary | Cloud | ✅ | (Check) | ❌ | Standard booking pages |
| **Cal.com** | AGPLv3 | Next.js/Postgres | ✅ | ✅ | ✅ | Mature Calendly alternative |
| **Tymeslot** | Open Source | Elixir/Phoenix | ✅ 4 themes | ✅ Any CalDAV | ✅ | Full-featured + CalDAV |
| **Radicale** | GPL-3.0 | Python | ❌ (Server) | ✅ Native | ✅ | Lightweight CalDAV server |
| **DAVx⁵** | GPLv3 | Kotlin/Android | ❌ (Client) | ✅ Sync client | ✅ (App) | Android CalDAV sync |
| **Tidetime** | Open Source | Next.js/Postgres | ✅ Multi-provider | (Google/M365) | ✅ | Multi-provider company booking |
| **Calnode** | Apache-2.0 | Go | ✅ + MCP | (Google/M365) | ✅ | AI-agent bookable scheduler |
| **Calrs** | Open Source | Rust | ✅ Team modes | ✅ CalDAV | ✅ | Team + invite-link scheduling |
| **justbookmycal** | Open Source | Python/Flask | ✅ ICS-based | ✅ ICS feeds | ✅ | Minimal ICS-based booking |
| **OpenReception** | AGPL v3 | (Check) | ✅ Healthcare | (Check) | ✅ | Doctor's offices + E2EE |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Online Calendar or Scheduling tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

**Note on the open-source ecosystem:** The calendar and scheduling space splits between **full booking platforms** (Cal.com for maturity, Tymeslot for feature depth with CalDAV, Tidetime for multi-provider companies, Calrs for Rust-based team scheduling, Calnode for AI-native MCP integration) and **calendar infrastructure** (Radicale for a lightweight CalDAV server, DAVx⁵ for Android sync). **Cal.com** remains the most established open-source Calendly alternative with the largest community [citation:6], while **Tymeslot** offers a compelling modern alternative with four themes, universal CalDAV sync, and no gated features [citation:2]. For teams wanting AI-agent accessibility, **Calnode** uniquely compiles an MCP server into its binary, allowing agents to book meetings directly [citation:12]. **Radicale** is the go-to for self-hosting calendar data itself, particularly when paired with **DAVx⁵** on Android [citation:3][citation:4]. No open-source project fully replicates Google Calendar's ecosystem integration, but the scheduling-specific tools cover the booking workflow comprehensively.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
