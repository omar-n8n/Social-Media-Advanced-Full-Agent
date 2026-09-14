# 🗂️ Social-Media-Assistant-Agent

### An Autonomous AI-Powered Content Creation & Publishing Workflow built with n8n

<p align="center">

[![n8n](https://img.shields.io/badge/Orchestrator-n8n-FF6D5A?style=for-the-badge\&logo=n8n\&logoColor=white)](https://n8n.io/)
[![OpenAI](https://img.shields.io/badge/AI-OpenAI-412991?style=for-the-badge\&logo=openai\&logoColor=white)](https://openai.com/)
[![Google Drive](https://img.shields.io/badge/Storage-Google_Drive-4285F4?style=for-the-badge\&logo=googledrive\&logoColor=white)](https://drive.google.com/)
[![Meta](https://img.shields.io/badge/API-Meta_Graph_API-0866FF?style=for-the-badge\&logo=facebook\&logoColor=white)](https://developers.facebook.com/)
[![LinkedIn](https://img.shields.io/badge/API-LinkedIn-0A66C2?style=for-the-badge\&logo=linkedin\&logoColor=white)](https://www.linkedin.com/)
[![Status](https://img.shields.io/badge/Status-Production_Ready-22C55E?style=for-the-badge)

</p>

<p align="center">

**Generate → Review → Regenerate → Approve → Publish**

</p>

---

## 📖 Overview

**Social-Media-Assistant-Agent** is a modular AI-powered social media automation system built with **n8n**.

It transforms simple **text prompts or voice notes** into ready-to-publish social media content while keeping the user in control of what gets generated and where it gets published.

Unlike a fixed content-generation workflow, the system dynamically adapts to the user's request.

### 🎯 What can the user generate?

|    Content Type    | AI Caption | AI Image | Use Case            |
| :----------------: | :--------: | :------: | ------------------- |
|   ✍️ Caption Only  |      ✅     |     —    | Text-based posts    |
| 🎨 Caption + Image |      ✅     |     ✅    | Visual social posts |

After generation, content can be reviewed, regenerated, approved, and published to the selected platform.

### 🌐 Supported Platforms

| Platform     | Publishing | Status |
| ------------ | :--------: | :----: |
| 🔵 Facebook  |      ✅     | Active |
| 📸 Instagram |      ✅     | Active |
| 💼 LinkedIn  |      ✅     | Active |

---

# ✨ Key Capabilities

| Capability                       | Description                                                             |
| -------------------------------- | ----------------------------------------------------------------------- |
| 🎤 **Voice Input**               | Convert Messenger voice notes into text using OpenAI Whisper            |
| 💬 **Text Input**                | Accept natural-language content requests                                |
| 🧠 **AI Copywriting**            | Generate platform-ready captions with hooks, CTAs, hashtags, and emojis |
| 🎨 **AI Image Generation**       | Create context-aware visuals when requested                             |
| 🔄 **Regeneration**              | Generate a new version when the user rejects the content                |
| 👤 **Human Approval**            | Keep a human in the loop before publishing                              |
| ☁️ **Asset Management**          | Store generated assets in Google Drive                                  |
| 📊 **Content Logging**           | Track generated content using Google Sheets                             |
| 🚀 **Multi-Platform Publishing** | Publish approved content to Facebook, Instagram, or LinkedIn            |
| 🧩 **Modular Architecture**      | Easily extend the workflow with additional capabilities                 |

---

# 🏗️ System Architecture

The system follows a modular pipeline where each stage is responsible for a specific part of the content lifecycle.

| Layer            | Technology     | Responsibility                      |
| ---------------- | -------------- | ----------------------------------- |
| 🎤 Input         | Meta Messenger | Voice & text requests               |
| 🗣️ Speech       | OpenAI Whisper | Voice-to-text transcription         |
| 🧠 Intelligence  | OpenAI GPT-4o  | Content generation & transformation |
| 🎨 Media         | OpenAI Images  | AI image generation                 |
| ⚙️ Orchestration | n8n            | Workflow logic & automation         |
| ☁️ Storage       | Google Drive   | Generated asset storage             |
| 📊 Database      | Google Sheets  | Content & workflow tracking         |
| 🔗 Publishing    | Meta Graph API | Facebook & Instagram publishing     |
| 💼 Publishing    | LinkedIn API   | LinkedIn publishing                 |

---

# ⚙️ Core Features

## 🎤 1. Voice & Text Input

Users can interact with the assistant using either:

```text
🎤 Voice Message
       ↓
OpenAI Whisper
       ↓
Text
       ↓
Content Pipeline
```

or directly send a text request.

This creates a more natural interface for content creation without requiring users to manually interact with the underlying n8n workflow.

---

## 🧠 2. Flexible Content Generation

The workflow does not force every request through the same generation path.

Instead, it determines what the user actually needs.

### ✍️ Caption Only

The system generates a c
