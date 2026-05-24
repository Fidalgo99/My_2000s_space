# 📡 Lucas's Corner

Welcome to the central repository for **Lucas's Corner** (`https://fidalgo99.github.io/My_2000s_space/`), a personal web landscape built to explore serverless client-database connections, strict access policies, and low-overhead static hosting architectures.

> Developed locally on a **ThinkPad running Debian**. Uncompromised utility. Zero bloat.

---

## 🛠️ System Architecture Overview

Unlike typical personal sites that rely on resource-heavy monolithic backends or frameworks, this system utilizes a decentralized, modern serverless architecture optimized for high-speed delivery over standard edge networks.

+-----------------------------------+
|       Client Browser Front-End    |
|   (Static HTML / Vanilla CSS / JS) |
+-----------------------------------+
|
| (Secure HTTPS Rest Client Hooks)
▼
+-----------------------------------+
|       Supabase API Gateway       |
+-----------------------------------+
|
| (Enforced Row Level Security / RLS)
▼
+-----------------------------------+
|      PostgreSQL Cloud Database     |
|   (Visitor Odometer / Guestbook)  |
+-----------------------------------+


### Infrastructure Stack:
* **Host Platform:** GitHub Pages (Migrated from Neocities to bypass restrictive platform-level Content Security Policies and arbitrary multi-media MIME-type blocking).
* **Database Engine:** PostgreSQL hosted via Supabase Cloud Matrix.
* **Logic Controller:** Native Vanilla JavaScript DOM API (Event-driven asynchronous connection threads).

---

## 🔒 Security Posture & Database Controls

A primary engineering challenge of this project was connecting a client-side static application directly to a cloud database without a middleman proxy server exposing full database manipulation permissions.

### 1. Row Level Security (RLS) Matrix
The database does not rely on frontend secrecy to shield data. Instead, strict **PostgreSQL Row Level Security Policies** are compiled directly on the database engine. Even if the public `anon` API token is extracted from the client source code, attackers are walled off:
* **`site_stats` Table:** Write policies explicitly validate that incoming packet updates increment the visitor integer by exactly `+1`. Arbitrary state overwriting is dropped at the engine level.
* **`guestbook` Table:** Public users are granted `INSERT` and `READ` vectors only. Malicious table drops, string deletions, or cross-row edits return an immediate `403 Unauthorized` payload block.

### 2. XSS Mitigation
User-generated strings inside the guestbook are routed through a localized HTML entity parser (`escapeHtml()`) before rendering into the DOM, completely neutering remote code execution and Cross-Site Scripting vector risks.

---

## 🚀 Local Development & Deployment

The codebase reflects an intentional choice to step away from modern web compilation bloat (Node.js, Next.js, Webpack, Tailwind). It is maintained using minimal, performant infrastructure workflows.

* **Editor:** Raw text processing. No bulky IDE wrappers.
* **Testing Engine:** Local network loops (`file://` paths and isolated staging parameters).
* **Telemetry Rules:** High-level traffic events are parsed using client-side asynchronous triggers to increment a unified visitor odometer (`site_stats`). User-generated data is submitted as structured rows to a dedicated ledger (`guestbook`) to maintain an active, dynamic community logbook.

---

### 📡 System Maintenance Logs
* **Web Migration Complete:** Pipeline shifted to GitHub Edge CDNs.
* **Audio Matrix Calibrated:** Core audio deck running full MP3 compression natively.
* **Database Reset Active:** Re-seeded core counter registries to handle state maintenance loops.

*Thanks for auditing the system infrastructure.*
