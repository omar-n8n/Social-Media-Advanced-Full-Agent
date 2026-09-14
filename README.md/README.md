# 🗂️ Social-Media-Assistant-Agent

### An Autonomous AI-Powered Content Creation & Publishing System built with n8n

<p align="center">

[![n8n](https://img.shields.io/badge/Orchestrator-n8n-FF6D5A?style=for-the-badge\&logo=n8n\&logoColor=white)](https://n8n.io/)
[![OpenAI](https://img.shields.io/badge/AI-OpenAI-412991?style=for-the-badge\&logo=openai\&logoColor=white)](https://openai.com/)
[![Google Drive](https://img.shields.io/badge/Storage-Google%20Drive-4285F4?style=for-the-badge\&logo=googledrive\&logoColor=white)](https://drive.google.com/)
[![Cloudinary](https://img.shields.io/badge/Media-Cloudinary-3448C5?style=for-the-badge\&logo=cloudinary\&logoColor=white)](https://cloudinary.com/)
[![Meta](https://img.shields.io/badge/Publishing-Meta-1877F2?style=for-the-badge\&logo=meta\&logoColor=white)](https://developers.facebook.com/)
[![LinkedIn](https://img.shields.io/badge/Publishing-LinkedIn-0A66C2?style=for-the-badge\&logo=linkedin\&logoColor=white)](https://www.linkedin.com/)
[![Status](https://img.shields.io/badge/Status-Production_Ready-22C55E?style=for-the-badge)](https://github.com/omar-n8n/Social-Media-Assistant-Agent)

</p>

<p align="center">
  <b>Generate → Review → Regenerate → Approve → Publish</b>
</p>

---

## 📸 Workflow Preview

<p align="center">
  <img src="Screenshots/Generating-Flow.jpeg" alt="Generating Flow" width="100%">
</p>

<p align="center">
  <img src="Screenshots/Regenerating-Flow.jpeg" alt="Regenerating Flow" width="100%">
</p>

<p align="center">
  <img src="Screenshots/Publishing-Flow.jpeg" alt="Publishing Flow" width="100%">
</p>

---

## 🚀 Overview

**Social-Media-Assistant-Agent** is a modular AI-powered social media automation system built with **n8n, OpenAI, Cloudinary, Google Drive, Google Sheets, Meta, and LinkedIn APIs**.

The system transforms a simple **text prompt or voice note** into ready-to-publish social media content through an automated workflow that combines:

* AI content generation
* AI image generation
* Media management with Cloudinary
* Human approval
* Content regeneration
* Multi-platform publishing
* Content tracking

Instead of manually writing, designing, downloading, uploading, and publishing every post, the workflow handles the entire process through one automated pipeline.

---

## ✨ What It Can Generate

The system supports flexible content generation depending on the user's needs.

| Content Type    | AI Caption | AI Image | Best For                  |
| --------------- | ---------: | -------: | ------------------------- |
| Caption Only    |          ✅ |        ❌ | Text-based posts          |
| Caption + Image |          ✅ |        ✅ | Visual social media posts |

This makes the workflow flexible instead of forcing every request into the same content format.

---

## 🌐 Supported Publishing Platforms

| Platform  | Status    | Publishing |
| --------- | --------- | ---------- |
| Facebook  | 🟢 Active | Automated  |
| Instagram | 🟢 Active | Automated  |
| LinkedIn  | 🟢 Active | Automated  |

The publishing layer is modular, allowing additional platforms to be integrated without redesigning the entire workflow.

---

# 🧠 Core Capabilities

| Capability                   | Description                                               |
| ---------------------------- | --------------------------------------------------------- |
| 🎙️ Voice Input              | Convert voice instructions into text using OpenAI Whisper |
| 💬 Text Input                | Accept direct content instructions                        |
| ✍️ AI Copywriting            | Generate platform-ready captions using OpenAI             |
| 🖼️ AI Image Generation      | Generate visual assets when requested                     |
| 🔄 Content Regeneration      | Regenerate content when the user is not satisfied         |
| ☁️ Cloud Media Management    | Upload and manage generated media through Cloudinary      |
| 📁 File Storage              | Store workflow assets through Google Drive                |
| 📊 Content Database          | Track generated and published content using Google Sheets |
| 👤 Human Approval            | Keep a human in control before publishing                 |
| 🌐 Multi-Platform Publishing | Publish to Facebook, Instagram, and LinkedIn              |
| ⚙️ Workflow Orchestration    | Coordinate the complete process through n8n               |

---

# 🏗️ System Architecture

The workflow follows a modular event-driven architecture:

| Layer            | Technology     | Responsibility                           |
| ---------------- | -------------- | ---------------------------------------- |
| Input            | Meta Messenger | Receive text and voice requests          |
| Speech-to-Text   | OpenAI Whisper | Convert voice into text                  |
| AI Intelligence  | OpenAI GPT     | Understand requests and generate content |
| Image Generation | OpenAI Images  | Create visual content                    |
| Media Management | Cloudinary     | Upload, host, and manage generated media |
| File Storage     | Google Drive   | Store workflow assets                    |
| Database         | Google Sheets  | Track content and publishing status      |
| Orchestration    | n8n            | Connect and automate all components      |
| Publishing       | Meta Graph API | Facebook & Instagram publishing          |
| Publishing       | LinkedIn API   | LinkedIn publishing                      |

---

# 🔥 Key Features

## 🎙️ 1. Voice & Text Content Requests

Users can provide either:

* A normal text instruction
* A voice message

Voice requests are transcribed using **OpenAI Whisper** before being passed into the AI content pipeline.

Example:

> "Create a professional post about AI automation for businesses."

The workflow automatically processes the request and prepares the required content.

---

## ✍️ 2. AI-Powered Copywriting

OpenAI generates social-media-ready captions based on the user's instructions.

The generation layer can adapt the content according to:

* Topic
* Tone
* Platform
* Content requirements
* User instructions

---

## 🖼️ 3. AI Image Generation

When the user requests visual content, the workflow generates an AI image alongside the caption.

The system can therefore handle:

**Caption only**

or

**Caption + AI-generated image**

without requiring separate workflows.

---

## ☁️ 4. Cloudinary Media Pipeline

**Cloudinary** is a core part of the media-management layer.

Generated images are uploaded to Cloudinary so they can be:

* Hosted remotely
* Accessed through stable URLs
* Passed between workflow steps
* Used by publishing APIs
* Managed independently from the local workflow environment

### Media Flow

```text
AI Image Generation
        ↓
   Cloudinary
        ↓
   Hosted Media URL
        ↓
Publishing Layer
        ↓
Facebook / Instagram / LinkedIn
```

This makes the workflow much more suitable for production environments where publishing platforms need accessible media URLs.

---

# 👤 Human-in-the-Loop Approval

The system does not blindly publish every generated post.

The user remains in control of the final content.

```text
        AI Generates Content
                 ↓
          User Reviews
             ↙       ↘
        Regenerate    Approve
             ↓          ↓
        New Content   Publish
```

The user can:

| Action          | Result                          |
| --------------- | ------------------------------- |
| ✅ Approve       | Continue to publishing          |
| 🔄 Regenerate   | Generate a new version          |
| ❌ Reject / Stop | End the current publishing flow |

This creates a practical balance between **AI automation and human control**.

---

# 🔄 End-to-End Workflow

```text
┌───────────────────────┐
│   Text / Voice Input  │
└───────────┬───────────┘
            ↓
┌───────────────────────┐
│   Speech-to-Text      │
│     if required       │
└───────────┬───────────┘
            ↓
┌───────────────────────┐
│     AI Processing     │
│       OpenAI          │
└───────────┬───────────┘
            ↓
     ┌──────┴──────┐
     ↓             ↓
 Caption Only   Caption + Image
     │             │
     │       ┌─────▼─────┐
     │       │ AI Image  │
     │       └─────┬─────┘
     │             ↓
     │       ┌───────────┐
     │       │Cloudinary │
     │       └─────┬─────┘
     │             │
     └──────┬──────┘
            ↓
      Human Review
        ↙       ↘
   Regenerate   Approve
        ↓          ↓
      AI Loop   Publishing
                   ↓
        ┌──────────┼──────────┐
        ↓          ↓          ↓
     Facebook   Instagram  LinkedIn
```

---

# 📊 Content Lifecycle

| Stage          | System Action                          |
| -------------- | -------------------------------------- |
| 1️⃣ Input      | Receive text or voice request          |
| 2️⃣ Understand | Process user instructions with AI      |
| 3️⃣ Generate   | Create caption and optional image      |
| 4️⃣ Store      | Manage files and media                 |
| 5️⃣ Review     | Send content for human approval        |
| 6️⃣ Regenerate | Create a new version if requested      |
| 7️⃣ Approve    | Confirm final content                  |
| 8️⃣ Publish    | Publish to selected platforms          |
| 9️⃣ Track      | Log content and publishing information |

---

# 🔗 Integrations

| Service            | Role                                      | Status    |
| ------------------ | ----------------------------------------- | --------- |
| **n8n**            | Workflow orchestration                    | 🟢 Active |
| **OpenAI**         | AI processing, Whisper & image generation | 🟢 Active |
| **Cloudinary**     | Media hosting & management                | 🟢 Active |
| **Google Drive**   | File storage                              | 🟢 Active |
| **Google Sheets**  | Content tracking & database               | 🟢 Active |
| **Meta Graph API** | Facebook & Instagram publishing           | 🟢 Active |
| **LinkedIn API**   | LinkedIn publishing                       | 🟢 Active |

---

# 💼 Practical Use Cases

| Use Case                  | Example                                                    |
| ------------------------- | ---------------------------------------------------------- |
| 🏢 Business Content       | Generate and publish company posts                         |
| 📣 Marketing Teams        | Automate repetitive content production                     |
| 👤 Personal Brands        | Maintain consistent social media activity                  |
| 🚀 Startups               | Reduce manual content operations                           |
| 📱 Social Media Managers  | Generate, review, and publish from one workflow            |
| 🤖 AI Automation Services | Use as a foundation for client-specific automation systems |

---

# 📁 Repository Structure

```text
Social-Media-Assistant-Agent
│
├── README.md
│
├── workflow
│   └── Social-Media-Assistant-Agent.json
│
├── Screenshots
│   ├── Generating-Flow.jpeg
│   ├── Regenerating-Flow.jpeg
│   └── Publishing-Flow.jpeg
│
└── assets
```

---

# ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/omar-n8n/Social-Media-Assistant-Agent.git
```

### 2. Open n8n

Import:

```text
workflow/Social-Media-Assistant-Agent.json
```

### 3. Configure Credentials

Connect the required services:

* OpenAI
* Cloudinary
* Google Drive
* Google Sheets
* Meta
* LinkedIn

### 4. Configure Environment

Update the workflow with your own credentials, IDs, pages, accounts, and required configuration.

### 5. Activate

Once credentials and platform settings are configured, activate the workflow and start sending content requests.

---

# 🔐 Requirements

| Requirement              | Purpose                         |
| ------------------------ | ------------------------------- |
| n8n                      | Workflow automation             |
| OpenAI API               | AI processing and generation    |
| Cloudinary Account       | Media hosting and delivery      |
| Google Drive             | File storage                    |
| Google Sheets            | Content database                |
| Meta Developer Setup     | Facebook & Instagram publishing |
| LinkedIn Developer Setup | LinkedIn publishing             |

---

# 🗺️ Roadmap

## Content Creation

| Feature                | Status      |
| ---------------------- | ----------- |
| Speech-to-Text         | ✅ Completed |
| AI Copywriting         | ✅ Completed |
| Flexible Content Types | ✅ Completed |
| AI Image Generation    | ✅ Completed |
| AI Video Generation    | 🔜 Planned  |

## Publishing

| Feature                            | Status      |
| ---------------------------------- | ----------- |
| Facebook Publishing                | ✅ Completed |
| Instagram Publishing               | ✅ Completed |
| LinkedIn Publishing                | ✅ Completed |
| Scheduled Posts                    | 🔜 Planned  |
| Advanced Multi-Platform Publishing | 🔜 Planned  |

## Engagement

| Feature                    | Status     |
| -------------------------- | ---------- |
| Automated Comment Replies  | 🔜 Planned |
| AI Engagement Assistant    | 🔜 Planned |
| Comment Sentiment Analysis | 🔜 Planned |

## Analytics

| Feature                   | Status     |
| ------------------------- | ---------- |
| Analytics Dashboard       | 🔜 Planned |
| Post Performance Tracking | 🔜 Planned |
| AI Performance Insights   | 🔜 Planned |

---

# 🧰 Tech Stack

| Technology         | Usage                                    |
| ------------------ | ---------------------------------------- |
| **n8n**            | Automation & orchestration               |
| **OpenAI**         | AI reasoning, Whisper & image generation |
| **Cloudinary**     | Image hosting & media management         |
| **Google Drive**   | Asset storage                            |
| **Google Sheets**  | Content database                         |
| **Meta Graph API** | Facebook & Instagram                     |
| **LinkedIn API**   | LinkedIn publishing                      |

---

# 🧩 Architecture Philosophy

The workflow is designed around a **modular automation architecture**.

Each major responsibility is separated into its own logical layer:

```text
Input
  ↓
AI Processing
  ↓
Content Generation
  ↓
Media Management
  ↓
Human Approval
  ↓
Publishing
  ↓
Tracking
```

This approach makes the system easier to:

* Maintain
* Debug
* Extend
* Reuse
* Customize for different clients
* Add new platforms and AI capabilities

---

# ⭐ Project Highlights

| Highlight                 | Implementation  |
| ------------------------- | --------------- |
| AI Content Generation     | OpenAI          |
| Voice-to-Text             | OpenAI Whisper  |
| AI Visual Creation        | OpenAI Images   |
| Media Infrastructure      | Cloudinary      |
| Human Approval Loop       | n8n             |
| Content Regeneration      | n8n + OpenAI    |
| Multi-Platform Publishing | Meta + LinkedIn |
| Content Tracking          | Google Sheets   |
| File Management           | Google Drive    |
| Automation Engine         | n8n             |

---

# 📄 License

This project is provided for portfolio and educational purposes.

---

# 👨‍💻 Author

**Omar Ali Osman**

AI Automation Developer

Specializing in:

* AI Automation
* n8n Workflow Development
* AI Agents
* API Integrations
* RAG Systems
* Social Media Automation

**GitHub:**
https://github.com/omar-n8n

**LinkedIn:**
https://www.linkedin.com/in/omar-ali-007000379/

---

<p align="center">

### ⭐ If you found this project useful, consider giving it a Star!

**Built with ❤️ using n8n, OpenAI & Cloudinary**

</p>
