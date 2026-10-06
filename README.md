# 📄 Tender Document Package Builder

> **AI DevFest 2026 — Solo Vibe-Coding Contest Submission**  
> An executive-grade, client-side web application designed to verify, match, and compile tender submission documents into a single, unified PDF package.

---

## 🌟 Overview

The **Tender Document Package Builder** simplifies the complex tender submission process. It allows bidders to load tender requirement schemas (`requirements.json`), upload supporting PDF documents, automatically detect duplicates using SHA-256 cryptographic hashing, validate document expiry dates in real time, and compile a fully compliant, multi-page submission PDF package complete with a cover page, index table, and dynamic footers.

Built with a **Midnight Slate Executive (Dark Glassmorphism)** UI, the application runs 100% in the browser with zero server dependencies or build steps.

---

## ✨ Key Features

- **📑 Requirement Schema Management:**
  - Load custom `requirements.json` files dynamically.
  - One-click load for built-in sample tender data.

- **🛡️ Secure File Validation & Duplicate Detection:**
  - Strict format validation (rejects non-PDF files with modal alerts).
  - Client-side **SHA-256 hashing** via Web Crypto API to detect and flag identical duplicate PDF files.

- **🎯 Smart 1:1 Matching & Expiry Verification:**
  - Dropdown selector for strict 1:1 document-to-requirement mapping.
  - **Auto-Match Engine:** Automatically assigns uploaded PDFs based on keyword heuristics.
  - Real-time status evaluation (`OK`, `MISSING`, `EXPIRED`, `EXPIRY_NEEDED`, `NOT_PROVIDED`).
  - Automatic validation blocking if any mandatory document is missing, expired, or duplicated.

- **📦 Client-Side Package PDF Generation (`pdf-lib`):**
  - **Cover Page:** Displays Tender ID, Title, Entity, Bidder, Deadline, and an itemized document summary table.
  - **Table of Contents / Index Page:** Lists each document, page counts, and exact starting page numbers.
  - **Document Merging:** Merges matched PDFs sequentially based on requirement order.
  - **Dynamic Footers:** Automatically stamps `<Tender_ID> | Page X of Y` across every compiled page.

- **🌐 Value-Added Capabilities:**
  - **Bilingual Interface:** Instant toggle between English and Bangla (বাংলা).
  - **State Persistence:** Save and restore working progress locally using `localStorage`.
  - **CSV Export:** Export verification checklists into CSV spreadsheets.
  - **AI Tender Assistant:** Optional integration with Gemini API for compliance queries (strictly preserves local API key security).

---

## 🛠️ Tech Stack

- **Frontend:** HTML5, React 18 (Functional Components & Hooks via CDN), Babel Standalone
- **Styling:** Tailwind CSS (Custom Dark Glassmorphism Theme)
- **PDF Processing:** `pdf-lib` (v1.17.1)
- **Security & Hashing:** Web Crypto API (`crypto.subtle`)
- **Persistence:** Web Storage API (`localStorage`)

---

## 🚀 Getting Started

Since this application is completely client-side and requires **no build step or server setup**, you can run it directly in any modern browser.

### Prerequisites

- Any modern Web Browser (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari).

### Running the App

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/tender-document-package-builder.git](https://github.com/your-username/tender-document-package-builder.git)
   cd tender-document-package-builder
