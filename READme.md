# Hi, I'm Nemuri Swetha Lahari 👋

**Software Developer** at **Zenbeta Technologies** | Building server-side systems since March 2025

I'm a Junior Software Developer focused on backend engineering — designing APIs, data models, and file-processing pipelines that hold up in production. I like getting the details right: clean status/state design, proper error handling, and systems that are easy to reason about a year later.

---

## 🧭 About Me

- 🔭 Currently working as a **Backend Developer** at **Zenbeta Technologies** (March 2025 – Present)
- 🌱 Focused on **Node.js**, **REST API design**, and **cloud-integrated backend systems**
- 💡 Interested in data validation pipelines, file processing workflows, and building systems with clear, auditable state transitions
- 📫 Reach me at: **nemuriswetha09@gmail.com**
- 🔗 LinkedIn: **www.linkedin.com/in/swethanemuri**

---

## 🛠️ Tech Stack

**Languages & Runtime**
`JavaScript (Node.js)` `SQL`

**Backend & Frameworks**
`Express.js` `REST APIs` `Multer (file uploads)`

**Databases**
`MySQL` `Relational schema design` `mongodb`

**Cloud & Infrastructure**
`AWS S3` `AWS SDK (@aws-sdk/lib-storage)`

**Data Processing**
`XLSX / CSV parsing` `Spreadsheet validation` `Bulk data ingestion`

**Tools**
`Git` `Postman` `npm`

---

## 💼 Experience

### Junior Software Developer — Zenbeta Technologies
*March 2025 – Present*

- Built and maintained backend services for file upload and case-management workflows, including multipart upload handling, S3 integration, and spreadsheet ingestion
- Designed database schemas with explicit status enums and audit history tables to track how records move through their lifecycle (e.g. `Pending Publish → Published → Processed`)
- Implemented validation layers for uploaded files (size limits, MIME/extension checks, spreadsheet content validation) to keep bad data out of downstream systems
- Wrote defensive error handling to distinguish between recoverable failures (e.g. S3 upload errors — user can retry) and system-level failures requiring investigation
- Collaborated on API design for internal tools consumed by other teams

---

## 🚀 Featured Project: Case File Upload & Status Tracking System

A backend module for uploading case sheets (Excel/CSV), validating them, storing them in S3, and tracking their lifecycle in the database.

**What it does:**
- Accepts case files via multipart upload with strict validation (file type, size, MIME type)
- Uploads validated files to AWS S3 with tenant/client-scoped storage paths
- Persists file metadata in MySQL with a controlled status lifecycle: `PENDING_PUBLISH → PUBLISHED → PROCESSED`
- Maintains a full status-change history (who changed it, when, and from/to what state) for auditability
- Enforces valid state transitions at the repository layer so a file can never skip or reverse states incorrectly
- Handles upload failures gracefully — separates "S3 failed, please retry" from "uploaded but DB write failed" so nothing silently goes missing

**Tech used:** Node.js, Express, Multer, AWS S3, MySQL

**Key design decisions:**
- Separated the *current state* (`case_files.status`) from the *history* (`case_file_status_history`) so the system always answers not just "what's the status now" but "how did it get here"
- Used an explicit transition map (`{ PENDING_PUBLISH: ['PUBLISHED'], PUBLISHED: ['PROCESSED'], PROCESSED: [] }`) to prevent invalid status jumps at the code level, not just in the DB
- Kept S3 upload and DB persistence as two distinct, separately-handled failure points for clearer error messaging to the client

---

## 📊 GitHub Stats

![Your GitHub stats](https://github-readme-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=default)

---

## 📬 Get in Touch

- Email: **nemuriswetha09@gmail.com**
- LinkedIn: **www.linkedin.com/in/swethanemuri**
- GitHub: **https://github.com/nemuriswetha09**

---

*Open to backend engineering opportunities and interesting problems involving APIs, data pipelines, and cloud infrastructure.*