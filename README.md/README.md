# 🗂️ Social-Media-Assistant-Agent

> **An Enterprise-Grade, Autonomous AI Multi-Platform Content Generation, Human-in-the-Loop Review & Direct Publishing Orchestrator Built with n8n.**

---

## 📖 System Overview

**Social-Media-Assistant-Agent** is a modular, AI-powered social media automation system built with **n8n**. It transforms simple text prompts or voice notes into ready-to-publish social media content while keeping the user in full control of what gets generated and where it gets published.

Unlike rigid content-generation workflows, this system dynamically adapts to the user's specific request using intelligent routing logic.

### 🎯 Content Generation Types

| Content Type | AI Caption | AI Image | Primary Use Case |
| :--- | :---: | :---: | :--- |
| ✍️ **Caption Only** | ✅ | — | Thought leadership, quick updates, text posts |
| 🎨 **Caption + Image** | ✅ | ✅ | Visual social media posts, promotional content |

After generation, content goes through an interactive **Human-in-the-Loop** approval stage where it can be reviewed, regenerated, or directly published to the selected platform.

---

## 🌐 Supported Platforms

| Platform | Publishing Engine | Status |
| :--- | :--- | :---: |
| 🔵 **Facebook** | Facebook Graph API | ✅ Active |
| 📸 **Instagram** | Instagram Graph API | ✅ Active |
| 💼 **LinkedIn** | LinkedIn REST API | ✅ Active |

---

## ✨ Key Capabilities

* 🎤 **Voice Input Processing**: Converts Messenger voice notes into structured text using OpenAI Whisper.
* 💬 **Text Input Processing**: Accepts natural-language content requests directly.
* 🧠 **AI Copywriting**: Generates platform-ready captions complete with hooks, CTAs, hashtags, and emojis using GPT-4o.
* 🎨 **AI Image Generation**: Creates context-aware visual assets using OpenAI DALL-E when requested.
* 🔄 **Regeneration Loop**: Iteratively rewrites copy or generates new images if the user rejects the draft.
* 👤 **Human Approval**: Keeps full control with the user via Messenger approval buttons before publishing.
* ☁️ **Asset Storage**: Uploads assets to Cloudinary / Google Drive for high-speed delivery.
* 📊 **Content Logging**: Tracks post metadata, statuses, and history in Google Sheets.
* 🚀 **Multi-Platform Publishing**: Direct API-level publishing to Facebook, Instagram, or LinkedIn.
* 🧩 **Modular Architecture**: Decoupled design allowing easy integration of new platforms or models.

---

## 🏗️ System Architecture

The workflow follows a modular pipeline where each layer is responsible for a distinct phase of the content lifecycle:

| Layer | Technology | Responsibility |
| :--- | :--- | :--- |
| 🎤 **Input** | Meta Messenger | Receives voice & text requests via webhooks |
| 🗣️ **Speech** | OpenAI Whisper | Converts audio notes into clean text transcriptions |
| 🧠 **Intelligence** | OpenAI GPT-4o | Copywriting, prompt restructuring, & content decision-making |
| 🎨 **Media** | OpenAI DALL-E | Context-aware visual asset synthesis |
| ⚙️ **Orchestration** | n8n | Core workflow execution, branching logic, & routing |
| ☁️ **Storage** | Cloudinary / Google Drive | CDN media asset hosting |
| 📊 **Database** | Google Sheets | Audit logging, tracking post status, and historical records |
| 🔗 **Publishing (Meta)** | Meta Graph API | Facebook Pages & Instagram Feed publishing |
| 💼 **Publishing (LinkedIn)** | LinkedIn REST API | Binary media upload & feed post dispatching |

---

## ⚙️ Core Features Detail

### 🎤 1. Voice & Text Input
Users interact naturally with the assistant via Meta Messenger:

* **Voice Message** ──► OpenAI Whisper ──► Clean Text ──► Request Pipeline
* **Text Message** ────────────────────────────────────► Request Pipeline

### 🧠 2. Flexible Content Generation Logic
The workflow routes execution dynamically based on request requirements:
* **Caption Only**: Generates copy and immediately skips visual pipeline, saving execution time and API costs.
* **Caption + Image**: Triggers visual synthesis, stores the media asset, and constructs an image-compatible payload.

### ✍️ 3. AI Copywriting Anatomy
Generated social posts follow proven engagement frameworks:
* 🎯 **Hook**: Grabs immediate attention in the feed.
* 📖 **Body / Story**: Delivers core message value clearly.
* 📣 **CTA**: Directs audience toward intended action.
* #️⃣ **Hashtags**: Enhances content discoverability.
* 😊 **Formatting**: Uses emojis and line breaks optimized for modern feeds.

---

## 👤 Human-in-the-Loop Review

Automated generation does not mean unsupervised publishing. Every post enters a review loop:

* **AI Generated Content** ──► **User Review**
  * ──► **Approve** ──► Publishing Pipeline
  * ──► **Regenerate** ──► New Version Flow

| Action | Result |
| :--- | :--- |
| **✅ Approve** | Dispatches payload directly to target platform API |
| **🔄 Regenerate** | Fetches historical context and generates a revised draft |

---

## 🔄 End-to-End Workflow Pipeline

1. **User Request** (Voice / Text via Messenger Webhook)
2. **Request Router** (Determines Content Type)
   * Branch A: **Caption Only**
   * Branch B: **Caption + Image** (Triggers AI Image Generation & Cloud Upload)
3. **Google Sheets Logging** (Saves initial state)
4. **User Review** (Interactive Messenger Buttons)
   * Choice A: **Regenerate** ──► Route back to AI Agent for fresh copy/image
   * Choice B: **Approve** ──► Send to Platform Router
5. **Platform Router & Direct Publishing**
   * Route A: **Facebook Pages**
   * Route B: **Instagram Feed**
   * Route C: **LinkedIn Network**

---

## 🖼️ Workflow Screenshots

### ⚙️ Generating Flow
Processes initial incoming input, determines content type, generates text copy, and optionally synthesizes image assets.

<p align="center">
  <img src="Screenshots/Generating-Flow.png" alt="Generating Flow Workflow" width="100%" />
</p>

### 🔄 Regenerating Flow
Fetches rejected row metadata, applies user feedback or alternative strategy, and produces refined copy/visuals.

<p align="center">
  <img src="Screenshots/Regenerating-Flow.png" alt="Regenerating Flow Workflow" width="100%" />
</p>

### 🚀 Publishing Flow
Dispatches approved payloads to platform APIs (handling media upload containers for Instagram & binary uploads for LinkedIn).

<p align="center">
  <img src="Screenshots/Publishing-Flow.png" alt="Publishing Flow Workflow" width="100%" />
</p>

---

## 📂 Repository Structure

```text
Social-Media-Assistant-Agent
│
├── README.md
│
├── workflow/
│   └── Social-Media-Assistant-Agent.json
│
├── Screenshots/
│   ├── Generating-Flow.png
│   ├── Regenerating-Flow.png
│   └── Publishing-Flow.png
│
└── assets/