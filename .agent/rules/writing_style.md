---
trigger: always_on
description: Writing style, structure, and quality standards for technical portfolio posts and engineering case studies.
---

# Technical Portfolio Writing Standards

Engineering writing guidelines for portfolio case studies and project breakdowns. Written to provide clear, high-signal technical depth for recruiters, engineering managers, and technical peers.

## 1. Tone, Style, and Anti-Fluff Standards

- **Zero AI Emoticons and Emojis**: Do not use decorative emojis (e.g., 🚀, ✨, 💡, 🛠️, 📌, 🔥) in titles, section headers, bullet lists, or inline copy.
- **Strict Anti-Slop (No Empty Vocabulary)**: Avoid machine-generated buzzwords and marketing fluff, including _delve, elevate, empower, testament, game-changer, robust, cutting-edge, revolutionize, seamless, landscape, journey_.
- **Direct Technical Voice**: Present technical information concisely and factually. Focus on exact architectural designs, data models, state handling, network interactions, and measurable engineering trade-offs.
- **Evidence Over Adjectives**: Replace qualitative praise ("ultra-fast", "bulletproof") with specific mechanics (e.g., "Dexie.js IndexedDB local write buffer", "B-tree index with `varchar_pattern_ops`", "Playwright headless E2E verification").

## 2. Article Structure

Every product or project case study must follow this standardized hierarchy:

1. **Frontmatter**:
   ```yaml
   ---
   title: 'Project Name'
   pubDate: 'YYYY-MM-DD'
   category: 'product' # 'product' | 'work' | 'volunteer' | 'certification'
   techStack: ['Language/Framework', 'Database', 'Tool']
   ---
   ```
2. **Hero Asset & Operational Status**:
   - Primary screenshot, architecture diagram, or banner.
   - Status checklist:
     ```markdown
     - [x] Server Alive
     - [x] Production System in Active Operation
     ```
   - Live URL directive if deployed: `::link{url="https://..."}`.
3. **Overview & Problem Statement**:
   - Clear 1-2 paragraph description of what the system does, who uses it, and the domain challenges it solves.
4. **Architecture & Implementation Details**:
   - **Frontend & Client State**: Framework, build tooling, local persistence (IndexedDB, local storage), offline synchronization strategies.
   - **Backend & Data Storage**: HTTP runtime/framework, database schema design, index strategies, transaction isolation, idempotency.
   - **Hardware & Protocol Integration**: Barcode scanners, thermal printers, Web APIs (Web Audio, WebSerial, WebUSB, ESC/POS) if applicable.
5. **Data Integrity & Performance Optimizations**:
   - Query optimizations, batching, caching, concurrency control, and schema evolution.
6. **Testing, Reliability & Observability**:
   - Unit and integration tests, mutation testing, end-to-end (E2E) automated workflows, load/performance testing (k6), error tracking (Sentry), and structured logging (`log/slog`).
7. **Repository & Artifacts**:
   - Repository component tag: `::github{repo="organization/repo"}` or clear attribution if private/proprietary.
