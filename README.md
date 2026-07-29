# 📡 OTX Self-Check — لوحة مراجعة النقل الضوئي

**OTX Self-Check** is a feature-rich, interactive single-page application (SPA) designed for telecom engineers, students, and professionals preparing for **Huawei HCIA-Transmission**, **HCIP-Transmission**, and advanced optical network engineering certifications.

The application serves as a complete study hub, performance tracker, spaced-repetition manager, quiz prompt generator for AI tools (like Google NotebookLM), and interactive Question Bank.

---

## 🌟 Key Features

### 1. 📚 Comprehensive Curriculum Tracks
Curated curriculum covering over 150+ core sub-topics categorized under 5 major learning tracks:
* **HCIA-Transmission (V2.5)**: SDH principles, WDM basics, OTN framing (OTU/ODU/OPU), Ethernet service mapping, network protection (MSP, OLP), and NCE-T/NMS basics.
* **HCIP-Transmission (V2.5)**: ROADM & WSS, Coherent Transmission (100G/400G/Beyond-100G OTUCn), Raman Amplifiers, Liquid OTN/OSU, OSNR/Power budget planning, MPLS-TP, SyncE, IEEE 1588v2, and ASON/WSON control plane.
* **HCIP TX Transcript**: Hardware architecture (OptiX OSN 9800 series shelves, GSP boards, TOM/TDX/TSC transponders), FOADM vs. ROADM grooming, commissioning, client/network protection scenarios, and electrical/optical alarm signal flows.
* **Optical TXN 2023**: Industry landscape (Operators vs. Vendors vs. NOC teams), fiber types (SM/MM), spectrum bands (C/L-band preference), site applications (OTM, OADM, OLA, Regenerator), and 80-channel DWDM system design.
* **Optics Expert Course**: End-to-end network project lifecycle, commissioning parameters, RFC 2544 testing, detailed optical performance monitoring (OSNR, BER, Q-factor), fiber physical standards (G.652 to G.655), and linear/non-linear impairments.

### 2. 📊 Topic Mastery & Spaced Repetition Engine
* **Status Tracking**: Mark topics as `Not Started`, `Weak (🔴)`, `Good (🟡)`, or `Mastered (🟢)`.
* **Dynamic Mastery Pct**: Computes mastery percentages dynamically based on historical quiz performance and manual reviews.
* **Overdue Review Alerts**: Automatic tracking flags topics due for review (7–13 days = Soon 🟡, 14+ days = Overdue 🔴).
* **Daily Streak Tracker (🔥)**: Tracks topics reviewed today to encourage daily study consistency.
* **Priority Study Queue**: Automatically categorizes topics into action lists (Weak items, unstudied core HCIA/HCIP topics, and applied optics topics).

### 3. 🎯 NotebookLM Quiz Prompt Builder
* Select any group of topics across tracks to generate a tailored prompt.
* Includes unique topic identifiers (`[topic: <id>]`), suggested question counts, and difficulty levels (Medium / Hard).
* Copy the prompt with one click to generate structured multi-topic quizzes in **Google NotebookLM**.

### 4. 📝 Quiz Log & Multi-Tier Analytics
* Log quiz scores (`correct / total`), dates, source track, and custom notes.
* Supports pasting full raw markdown quiz text (questions, choices, answers, rationales).
* Structured fields for tracking wrong and skipped question numbers.

### 5. 🧠 Integrated Google Gemini AI Analysis
* Connects directly to Google Gemini API (`gemini-2.0-flash` or custom models) using your own API key.
* Analyzes quiz raw text and student notes to evaluate topic-by-topic performance automatically.
* Provides one-line Arabic explanations for every rating.
* Handles rate-limiting gracefully with auto-retry countdown timers.

### 6. 📚 Interactive Question Bank (بنك الأسئلة)
* Parses raw quiz text into interactive digital Q&A review cards.
* Highlights correct choices, hints, and detailed technical rationales.
* Filter cards by status (`All`, `Correct ✅`, `Wrong ❌`, `Skipped ⏭`) and perform real-time text search.

### 7. 🔍 Real-Time Search & Customization
* Real-time search across topic titles, descriptions, and categories in English or Arabic.
* Inline editing of topic titles and descriptions.
* Add custom topics or new categories to any track.
* Soft-delete with modal confirmation dialogs.

### 8. 💾 Dual Offline Storage & Data Portability
* **Primary Storage**: `localStorage` for fast access.
* **Redundant Backup**: `IndexedDB` fallback to prevent data loss on large datasets.
* **JSON Export & Import**: Backup full state to `.json` files anytime (`otx_selfcheck_backup_YYYY-MM-DD.json`) or restore existing backups.
* **Privacy First**: All user data remains 100% local in the browser. Gemini API keys are saved separately in local storage and never included in data exports.

---

## 🚀 Getting Started

### Prerequisites
* Any modern web browser (Google Chrome, Microsoft Edge, Mozilla Firefox, Safari).
* No Node.js, server, build tools, or external dependencies required.

### How to Run
1. Clone or download this repository.
2. Open `index.html` directly in your browser:
   * **Windows**: Double-click `index.html` or drag it into your browser.
   * **Browser**: File -> Open File -> Select `index.html`.

### Setting Up Gemini AI Integration (Optional)
1. Click **⚙️ Gemini AI** in the topbar.
2. Paste your Google Gemini API key (obtained from [Google AI Studio](https://aistudio.google.com/)).
3. Select your model (default: `gemini-2.0-flash`).
4. Click **🧪 اختبر الاتصال** to test connection, then **✔ حفظ** to save locally.

---

## 📂 Repository Files

| File | Description |
| :--- | :--- |
| `index.html` | The complete application source (HTML5, CSS3, ES6 JavaScript). |
| `ciper.html` | Password-protected / encrypted variant of the application. |
| `README.md` | Documentation and overview of the project. |

---

## 🛠️ Technology Stack
* **HTML5**: Semantic Arabic RTL document structure.
* **CSS3**: Custom design system with CSS variables, dark theme (`#0a0e17`), JetBrains Mono & Inter typography, responsive Flexbox/Grid layouts, and glassmorphism topbar.
* **Pure JavaScript (ES6+)**: Zero framework dependencies. Reactive DOM rendering, async storage handlers, regex-based markdown parsers, clipboard API integration, and RESTful Google Gemini AI client.

---

## 🔒 Privacy & Data Security
* All study progress, quiz logs, and custom notes are stored **strictly in your local browser storage**.
* No external server or tracking scripts are used.
* The Gemini API key is stored locally in `localStorage` under a separate key and is **never** included in exported JSON backups.
