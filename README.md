<div align="center">

# Hi, I'm Jérémy Carpentier 👋

**Full Stack Developer — Apprentice Software Engineer @Evian (SAEME), Danone 🇫🇷**

Building business-critical web applications with a strong focus on **software architecture**, **code quality** and **user experience**.

<a href="https://www.linkedin.com/in/j%C3%A9r%C3%A9my-carpentier-762006207/">
  <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>
<a href="https://x.com/CappieOR">
  <img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X"/>
</a>

<img src="https://komarev.com/ghpvc/?username=CappieGold&style=flat-square&color=blue" alt="Profile views"/>

</div>

---

## 🚀 Featured Projects

### 🛂 EasyGate — Visitor Access Management Platform
> Production app used daily at the Evian site (Danone) — **100+ requests & 300+ visitors handled every month**
> *Enterprise project — source code hosted on a private internal repository, not publicly available.*

Full-stack TypeScript application managing visit requests, visitors, companies, access zones and multi-team approval workflows. Built almost entirely solo.

- 🏗️ **Modular DDD & CQRS architecture** (13 business modules) — SRP, DRY, KISS, YAGNI
- ⚙️ **Backend**: AdonisJS 6, PostgreSQL, Kysely — audit trail via triggers, fuzzy search & duplicate detection (pg_trgm)
- ⚛️ **Frontend**: React 19 + Inertia.js — SSR, real-time (SSE), dark mode, i18n FR/EN, end-to-end TypeScript contract
- 🔐 **SSO/OIDC** (Keycloak, PKCE flow), RBAC permissions, GDPR compliance
- ✅ **Quality**: ~700 automated tests, CI, linting, Docker + Nginx deployment

### 🔐 ADHUB — Active Directory Administration Portal
> .NET 9 / Blazor Server app centralizing AD administration without direct server access
> *Enterprise project — source code hosted on a private internal repository, not publicly available.*

- 🏗️ **Clean Architecture** (Domain, Application, Infrastructure, WebUI), DI, Result pattern
- 👥 AD users & groups management (LDAP), account request/approval workflow with notifications
- 🔑 Secure password reset: single-use expiring tokens, cleaned up by a background service
- 📧 Transactional SMTP emails (HTML templates), full audit trail (user, IP, user-agent)
- 🗄️ EF Core + SQLite, versioned migrations, role-based authorization middleware

### 🖥️ Display — Digital Signage for Production Lines
> Fullscreen signage player running on the production line screens of the Evian site, with a fully automated and tested release & deployment pipeline
> *Enterprise project — source code hosted on a private internal repository, not publicly available.*

Python application driving Chromium through Selenium to loop images, PDFs and scripted web pages (a small JSON action language: navigation, login, clicks, conditions), packaged and deployed to a Debian 12 fleet with no Internet access, served only by an internal Debian mirror.

- 🧩 **Architecture**: generic, open-source-ready client separated from a private site-deployment repository that consumes its releases (documented with ADRs)
- 📦 **Packaging**: single native binary (Nuitka), Debian package with safe upgrades (configuration, content and logs preserved), reproducible builds, checksums
- 🔒 **Version control of the browser**: each release is validated with one exact Chromium/chromedriver version, published next to the app in a signed APT repository (aptly) on the internal Debian mirror, and pinned on every station — Debian's newer builds are ignored until tested
- 🧪 **Testing**: smoke tests in clean Debian containers (fresh install, upgrade, unprivileged user, sandbox) and a simulated fleet station using the internal mirror, before anything is published
- 🔄 **CI/CD & GitOps** (Gitea Actions): build once, test that exact file, publish; bots open tested pull requests every week for the newest Chromium and for each new release
- ⚙️ **Infrastructure as Code** (Ansible): signed APT repository publication and kiosk provisioning, rollback by releasing forward
- 🛡️ **Hardening**: Chromium sandbox, enterprise kiosk policies, least-privilege permissions, weekly security update flow

### 📹 BreakWatch — Machine Stoppage Recording on Raspberry Pi
> Embedded Python application that records industrial machines on a Raspberry Pi and keeps the footage around every stoppage
> *Enterprise project — source code hosted on a private internal repository, not publicly available.*

The camera records continuously into a ring buffer. When a machine stops (signal received through a REST API), the application keeps the seconds before and after the fault, merges the segments with ffmpeg, archives the clip with its metadata and notifies operators by email.

- 🏗️ **Hexagonal architecture** (ports & adapters): domain and application layers tested with fakes, no hardware needed — thread-safe state machine, prioritized command queue, single worker owning the camera
- 🎥 **Embedded**: Picamera2 ring-buffer recording with configurable pre/post-fault window, GPIO status LEDs, Wi-Fi link monitor, crash recovery at startup
- 🔌 **REST API** (Flask + Gunicorn): bearer authentication, HMAC-signed download links, strict Pydantic validation, live configuration through `GET`/`PUT`/`PATCH /config`
- 🔍 **Audit & hardening**: documentation-vs-code audit (22 discrepancies resolved), fixed race conditions (double camera open, start/stop window), path traversal and a silent config reset, safe-by-default startup (refuses weak API keys in production)
- ✅ **Quality**: 140+ automated tests running on any PC, ruff linting, structured JSON logs with size-based rotation
- 📦 **Delivery**: arm64 Debian package with bundled dependencies for offline install, released and deployed to the Raspberry Pi units with Gitea Actions and Ansible

---

## 🛠️ Tech Stack

**Languages**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![C#](https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

**Backend**

![AdonisJS](https://img.shields.io/badge/AdonisJS-5A45FF?style=flat-square&logo=adonisjs&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![.NET 9](https://img.shields.io/badge/.NET%209-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Blazor](https://img.shields.io/badge/Blazor-512BD4?style=flat-square&logo=blazor&logoColor=white)
![EF Core](https://img.shields.io/badge/EF%20Core-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)

**Frontend**

![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Inertia.js](https://img.shields.io/badge/Inertia.js-9553E9?style=flat-square&logo=inertia&logoColor=white)
![Blazor](https://img.shields.io/badge/Blazor-512BD4?style=flat-square&logo=blazor&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![UnoCSS](https://img.shields.io/badge/UnoCSS-333333?style=flat-square&logo=unocss&logoColor=white)

**Databases**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=databricks&logoColor=white)

**Tools & Infrastructure**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Gitea Actions](https://img.shields.io/badge/Gitea%20Actions-609926?style=flat-square&logo=gitea&logoColor=white)
![Debian](https://img.shields.io/badge/Debian-A81D33?style=flat-square&logo=debian&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Keycloak](https://img.shields.io/badge/Keycloak%20(OIDC)-4D4D4D?style=flat-square&logo=keycloak&logoColor=white)
![Active Directory](https://img.shields.io/badge/Active%20Directory-0078D4?style=flat-square&logo=windows&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=flat-square&logo=selenium&logoColor=white)
![aptly](https://img.shields.io/badge/aptly%20(APT%20mirror)-2C3E50?style=flat-square&logo=debian&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-A22846?style=flat-square&logo=raspberrypi&logoColor=white)
![FFmpeg](https://img.shields.io/badge/FFmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![uv](https://img.shields.io/badge/uv-DE5FE9?style=flat-square&logo=uv&logoColor=white)

**Architecture & Practices**

`DDD` · `CQRS` · `Clean Architecture` · `Hexagonal Architecture` · `SOLID` · `ADR` · `Automated Testing` · `CI/CD` · `GitOps` · `Infrastructure as Code` · `Reproducible Builds` · `Embedded Systems` · `State Machines` · `i18n` · `RBAC` · `GDPR`

---

## 📊 GitHub Stats

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=CappieGold&theme=dark&background=000000)](https://git.io/streak-stats)

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=CappieGold&layout=compact&theme=vision-friendly-dark)](https://github.com/anuraghazra/github-readme-stats)

</div>
