# 🗂️ Social-Media-Assistant-Agent

### An Autonomous AI-Powered Content Creation & Publishing Workflow built with n8n

<p align="center">

[![n8n](https://img.shields.io/badge/Orchestrator-n8n-FF6D5A?style=for-the-badge\&logo=n8n\&logoColor=white)](https://n8n.io/)
[![OpenAI](https://img.shields.io/badge/AI-OpenAI-412991?style=for-the-badge\&logo=openai\&logoColor=white)](https://openai.com/)
[![Google Drive](https://img.shields.io/badge/Storage-Google_Drive-4285F4?style=for-the-badge\&logo=googledrive\&logoColor=white)](https://drive.google.com/)
[![Meta](https://img.shields.io/badge/API-Meta_Graph_API-0866FF?style=for-the-badge\&logo=facebook\&logoColor=white)](https://developers.facebook.com/)
[![LinkedIn](https://img.shields.io/badge/API-LinkedIn-0A66C2?style=for-the-badge\&logo=linkedin\&logoColor=white)](https://www.linkedin.com/)
[![Status](https://img.shields.io/badge/Status-Production_Ready-22C55E?style=for-the-badge)](https://github.com/omar-n8n/Social-Media-Assistant-Agent)

</p>

<p align="center">

**Generate → Review → Regenerate → Approve → Publish**

</p>

---

## 📖 Overview

**Social-Media-Assistant-Agent** is a modular AI-powered social media automation system built with **n8n**.

It transforms simple **text prompts or voice notes** into ready-to-publish social media content while keeping the user in control of what gets generated and where it gets published.

Unlike a fixed content-generation workflow, the system dynamically adapts to the user's request.

### 🎯 Content Generation

| Content Type       | AI Caption | AI Image | Best For                    |
| ------------------ | :--------: | :------: | --------------------------- |
| ✍️ Caption Only    |      ✅     |     —    | Text-based social posts     |
| 🎨 Caption + Image |      ✅     |     ✅    | Visual social media content |

After generation, content can be **reviewed, regenerated, approved, and published** to the selected platform.

### 🌐 Supported Platforms

| Platform     | Publishing | Status |
| ------------ | :--------: | ------ |
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
| 🔄 **Content Regeneration**      | Generate a new version when the user rejects the content                |
| 👤 **Human Approval**            | Keep a human in the loop before publishing                              |
| ☁️ **Asset Management**          | Store generated assets in Google Drive                                  |
| 📊 **Content Logging**           | Track generated content using Google Sheets                             |
| 🚀 **Multi-Platform Publishing** | Publish approved content to Facebook, Instagram, or LinkedIn            |
| 🧩 **Modular Architecture**      | Extend the workflow with additional AI and social media capabilities    |

---

# 🏗️ System Architecture

The system follows a modular pipeline where each stage is responsible for a specific part of the content lifecycle.

| Layer            | Technology     | Responsibility                        |
| ---------------- | -------------- | ------------------------------------- |
| 🎤 Input         | Meta Messenger | Voice and text requests               |
| 🗣️ Speech       | OpenAI Whisper | Voice-to-text transcription           |
| 🧠 Intelligence  | OpenAI GPT-4o  | Content generation and transformation |
| 🎨 Media         | OpenAI Images  | AI image generation                   |
| ⚙️ Orchestration | n8n            | Workflow logic and automation         |
| ☁️ Storage       | Google Drive   | Generated asset storage               |
| 📊 Database      | Google Sheets  | Content and workflow tracking         |
| 🔗 Publishing    | Meta Graph API | Facebook and Instagram publishing     |
| 💼 Publishing    | LinkedIn API   | LinkedIn publishing                   |

---

# ⚙️ Core Features

## 🎤 1. Voice & Text Input

Users can interact with the assistant using either:

```text
🎤 Voice Message
       │
       ▼
OpenAI Whisper
       │
       ▼
     Text
       │
       ▼
Content Pipeline
```

Users can also send a text request directly through Messenger.

This provides a natural interface for content creation without requiring users to interact directly with the underlying n8n workflow.

---

## 🧠 2. Flexible Content Generation

The workflow does not force every request through the same generation path.

Instead, it dynamically determines what the user needs.

### ✍️ Caption Only

The system generates a complete social media caption without generating an image.

### 🎨 Caption + Image

The system generates:

1. AI-written caption
2. AI-generated image
3. Stored image asset
4. Publishing-ready content

This flexible approach avoids unnecessary image generation and gives the user greater control over the final content.

---

## ✍️ 3. AI Copywriting

The AI generates social media copy based on the user's request and the selected content workflow.

| Element               | Purpose                                |
| --------------------- | -------------------------------------- |
| 🎯 **Hook**           | Capture attention                      |
| 📖 **Storytelling**   | Structure the message                  |
| 📣 **Call-to-Action** | Encourage engagement                   |
| #️⃣ **Hashtags**      | Improve discoverability                |
| 😊 **Emojis**         | Add visual structure where appropriate |
| 📱 **Formatting**     | Produce social-ready content           |

---

## 🎨 4. AI Image Generation

When an image is requested, the workflow automatically generates a context-aware visual based on the content.

```text
Content Request
      │
      ▼
AI Caption Generation
      │
      ▼
Image Context
      │
      ▼
AI Image Generation
      │
      ▼
Google Drive
      │
      ▼
Publishing Pipeline
```

---

## ☁️ 5. Automated Asset Management

Generated images are automatically uploaded to **Google Drive**.

The workflow stores the relevant asset information so it can be used by the publishing and tracking stages.

| Asset           | Storage       |
| --------------- | ------------- |
| Generated Image | Google Drive  |
| Image URL       | Google Sheets |
| Caption         | Google Sheets |
| Content Status  | Google Sheets |
| Timestamp       | Google Sheets |

---

## 📊 6. Content Tracking

Every generated content item can be logged in **Google Sheets**.

This provides a centralized record of the content lifecycle.

| Data         | Purpose                      |
| ------------ | ---------------------------- |
| Caption      | Store generated copy         |
| Image URL    | Reference generated media    |
| Platform     | Track publishing destination |
| Content Type | Caption / Caption + Image    |
| Status       | Track workflow state         |
| Timestamp    | Track creation activity      |

---

# 👤 Human-in-the-Loop Approval

AI generation does not automatically mean automatic publishing.

The system introduces a human approval layer that gives the user control over the final content.

### Approval Flow

```text
AI Generated Content
        │
        ▼
    User Review
        │
   ┌────┴────┐
   │         │
Approve   Regenerate
   │         │
   ▼         ▼
Publish   New Version
```

### Available Actions

| Action            | Result                                         |
| ----------------- | ---------------------------------------------- |
| ✅ **Approve**     | Sends the content to the publishing pipeline   |
| 🔄 **Regenerate** | Creates a new version of the requested content |

This creates a balance between **automation, flexibility, and human control**.

---

# 🚀 Multi-Platform Publishing

Once content is approved, the workflow routes it to the selected platform.

| Platform     | API                 | Publishing | Status |
| ------------ | ------------------- | :--------: | ------ |
| 🔵 Facebook  | Facebook Graph API  |      ✅     | Active |
| 📸 Instagram | Instagram Graph API |      ✅     | Active |
| 💼 LinkedIn  | LinkedIn API        |      ✅     | Active |

The publishing layer is separated from the content-generation layer, making future platform integrations easier to add.

---

# 🔄 End-to-End Workflow

```text
                         USER
                          │
                    Voice / Text
                          │
                          ▼
                  Messenger Webhook
                          │
                          ▼
                   Request Router
                          │
                          ▼
                ┌─────────────────┐
                │ Content Request │
                └────────┬────────┘
                         │
                         ▼
                 Select Content Type
                         │
                ┌────────┴────────┐
                │                 │
                ▼                 ▼
          Caption Only      Caption + Image
                │                 │
                │                 ▼
                │          AI Image Generation
                │                 │
                └────────┬────────┘
                         ▼
                   Google Drive
                         │
                         ▼
                   Google Sheets
                         │
                         ▼
                    User Review
                         │
                  ┌──────┴──────┐
                  │             │
               Approve       Regenerate
                  │             │
                  │             └──────► New Version
                  │
                  ▼
              Platform Router
                  │
           ┌──────┼──────┐
           │      │      │
           ▼      ▼      ▼
       Facebook Instagram LinkedIn
```

---

# 🖼️ Workflow Screenshots

## ⚙️ Generating Flow

The generation pipeline processes the user's request, determines the required content type, generates the caption, and optionally creates an AI-generated image.

<p align="center">
  <img src="Screenshots/Generating-Flow.jpeg" alt="Generating Flow" width="100%">
</p>

---

## 🔄 Regenerating Flow

When the user requests a new version, the regeneration flow creates updated content while preserving the existing workflow state.

<p align="center">
  <img src="Screenshots/Regenerating-Flow.jpeg" alt="Regenerating Flow" width="100%">
</p>

---

## 🚀 Publishing Flow

Once the user approves the generated content, the publishing flow routes it to the selected social media platform.

<p align="center">
  <img src="Screenshots/Publishing-Flow.jpeg" alt="Publishing Flow" width="100%">
</p>

---

# 📊 Content Lifecycle

| Stage  | Input                 | Processing            | Output               |
| ------ | --------------------- | --------------------- | -------------------- |
| **01** | 🎤 Voice / Text       | Request parsing       | Structured request   |
| **02** | 🧠 Request            | AI content generation | Caption              |
| **03** | 🎨 Image Request      | Image generation      | Visual asset         |
| **04** | ☁️ Asset              | Google Drive upload   | Stored asset         |
| **05** | 📊 Content            | Google Sheets logging | Tracked record       |
| **06** | 👤 Generated Content  | Human review          | Approve / Regenerate |
| **07** | ✅ Approved Content    | Platform routing      | Publishing request   |
| **08** | 🚀 Publishing Request | Social API            | Published content    |

---

# 🔌 Integrations

| Integration                    | Purpose                | Status |
| ------------------------------ | ---------------------- | :----: |
| ⚙️ **n8n**                     | Workflow orchestration |    ✅   |
| 🤖 **OpenAI GPT-4o**           | AI copywriting         |    ✅   |
| 🎤 **OpenAI Whisper**          | Speech-to-text         |    ✅   |
| 🎨 **OpenAI Images**           | AI image generation    |    ✅   |
| ☁️ **Google Drive API**        | Asset storage          |    ✅   |
| 📊 **Google Sheets API**       | Content database       |    ✅   |
| 💬 **Meta Messenger Webhooks** | User interaction       |    ✅   |
| 🔵 **Facebook Graph API**      | Facebook publishing    |    ✅   |
| 📸 **Instagram Graph API**     | Instagram publishing   |    ✅   |
| 💼 **LinkedIn API**            | LinkedIn publishing    |    ✅   |

---

# 🎯 Use Cases

The system can be adapted for a wide range of content automation scenarios.

| Use Case                       | Example                                 |
| ------------------------------ | --------------------------------------- |
| 👤 **Personal Brands**         | Automated personal content creation     |
| 📣 **Marketing Agencies**      | Content generation for multiple clients |
| 🏢 **Small Businesses**        | Social media content automation         |
| 🛍️ **E-commerce**             | Product-focused social posts            |
| 🎙️ **Podcasts**               | Content repurposing                     |
| 🎥 **Content Creators**        | Faster content production               |
| 💼 **Professional Brands**     | LinkedIn content automation             |
| 📱 **Social Media Management** | Multi-platform publishing               |

---

# 📂 Repository Structure

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

# 🚀 Installation

## 1. Clone Repository

```bash
git clone https://github.com/omar-n8n/Social-Media-Assistant-Agent.git
```

---

## 2. Import Workflow

Open your **n8n** instance.

Navigate to:

```text
Workflows
→ Import from File
```

Import:

```text
workflow/Social-Media-Assistant-Agent.json
```

---

## 3. Configure Credentials

Configure the required credentials:

| Credential                               | Required For              |
| ---------------------------------------- | ------------------------- |
| **OpenAI API**                           | AI generation and Whisper |
| **Google Drive OAuth**                   | Asset storage             |
| **Google Sheets OAuth**                  | Content tracking          |
| **Meta Developer Credentials**           | Facebook / Instagram      |
| **Facebook Page Access Token**           | Facebook publishing       |
| **Instagram Business / Creator Account** | Instagram publishing      |
| **LinkedIn Developer App**               | LinkedIn publishing       |

---

## 4. Activate Workflow

Enable the workflow and start sending content requests through Messenger.

---

# 📦 Requirements

| Requirement                    | Purpose                          |
| ------------------------------ | -------------------------------- |
| **n8n**                        | Workflow execution               |
| **OpenAI API**                 | AI capabilities                  |
| **Google Cloud Project**       | Google integrations              |
| **Google Drive API**           | Asset storage                    |
| **Google Sheets API**          | Content tracking                 |
| **Meta Developer Account**     | Facebook / Instagram integration |
| **LinkedIn Developer Account** | LinkedIn publishing              |

---

# 🗺️ Roadmap

### 🎨 Content Creation

* [x] Speech-to-Text
* [x] AI Copywriting
* [x] Flexible Content Types
* [x] AI Image Generation
* [ ] AI Video Generation

### 🚀 Publishing

* [x] Facebook Publishing
* [x] Instagram Publishing
* [x] LinkedIn Publishing
* [ ] Scheduled Posts
* [ ] Advanced Multi-Platform Publishing

### 💬 Engagement

* [ ] Automated Comment Replies
* [ ] AI-Powered Engagement Assistant
* [ ] Comment Sentiment Analysis

### 📊 Analytics

* [ ] Analytics Dashboard
* [ ] Post Performance Tracking
* [ ] AI Performance Insights

---

# 💡 Tech Stack

| Technology             | Role                            |
| ---------------------- | ------------------------------- |
| **n8n**                | Workflow orchestration          |
| **OpenAI GPT-4o**      | AI content generation           |
| **OpenAI Whisper**     | Speech-to-text                  |
| **OpenAI Images**      | AI image generation             |
| **Google Drive**       | Asset storage                   |
| **Google Sheets**      | Content database                |
| **Meta Graph API**     | Facebook & Instagram publishing |
| **LinkedIn API**       | LinkedIn publishing             |
| **Messenger Webhooks** | User interaction                |
| **REST APIs**          | External service integrations   |

---

# 🧩 Architecture Philosophy

The workflow follows a **modular, event-driven automation architecture**:

```text
INPUT
  │
  ▼
UNDERSTAND
  │
  ▼
GENERATE
  │
  ▼
OPTIONAL ASSET CREATION
  │
  ▼
STORE
  │
  ▼
REVIEW
  │
  ├──────────────► REGENERATE
  │
  ▼
APPROVE
  │
  ▼
ROUTE
  │
  ▼
PUBLISH
  │
  ▼
LOG
```

Each stage is separated into logical components, allowing new capabilities to be added without rebuilding the entire workflow.

The architecture provides a foundation for future capabilities such as:

* 🎥 AI video generation
* 💬 Automated comment responses
* 📅 Content scheduling
* 📊 Analytics
* 🌐 Additional social platforms

---

# 📈 Project Highlights

| Category             | Current Capability              |
| -------------------- | ------------------------------- |
| 🤖 **AI Automation** | End-to-end AI content pipeline  |
| 🎤 **Input**         | Voice + Text                    |
| ✍️ **Content**       | Flexible caption generation     |
| 🎨 **Media**         | AI image generation             |
| 👤 **Control**       | Human approval + regeneration   |
| ☁️ **Storage**       | Google Drive                    |
| 📊 **Tracking**      | Google Sheets                   |
| 🚀 **Publishing**    | Facebook + Instagram + LinkedIn |
| 🧩 **Architecture**  | Modular and extensible          |
| 🔮 **Next Phase**    | Video + Engagement + Analytics  |

---

# 📄 License

This repository is intended for educational and portfolio purposes.

Feel free to explore the workflow architecture and adapt it for your own automation projects.

---

# 👨‍💻 Author

## Omar Ali Osman

**AI Automation Developer**

I build intelligent AI automation systems using:

* AI Agents
* n8n
* OpenAI APIs
* API Integrations
* Workflow Automation
* Webhooks

### Connect with me

**GitHub**

https://github.com/omar-n8n

**LinkedIn**

https://www.linkedin.com/in/omar-ali-007000379/

---

<div align="center">

### ⭐ If you found this project useful, consider giving it a Star!

**Built with ❤️ using n8n & OpenAI**

</div>
