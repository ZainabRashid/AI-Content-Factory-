# AI Content Factory 🚀

An AI-powered content automation system designed to streamline the creation,
repurposing, organization, scheduling, and tracking of marketing content
across multiple digital platforms.

The project combines an n8n automation workflow with a web-based dashboard
to create an end-to-end AI content production pipeline.

## 🌐 Live Dashboard

[Open AI Content Factory Dashboard](https://ai-content-factory-s-0lu0.bolt.host/)

---

## 📌 Project Overview

Creating content for multiple platforms can be time-consuming, especially
when businesses need different formats for blogs, social media, video
descriptions, email campaigns, and other marketing channels.

AI Content Factory automates this process by taking basic content
requirements such as topic, target audience, business type, language,
tone, and content length, and transforming them into a complete marketing
content package.

The generated content can then be repurposed, stored, scheduled, delivered,
and tracked through connected services.

---

## ✨ Key Features

### 🤖 AI Content Generation

The system generates a complete content package including:

- SEO-optimized blog article
- LinkedIn post
- Instagram caption
- Facebook post
- Twitter/X content
- YouTube description
- SEO title
- Meta description
- Focus keywords
- Hashtags
- Call-to-action (CTA)

### 🔄 Content Repurposing

The generated blog content can be transformed into additional marketing
formats, including:

- Reel scripts
- Carousel content
- Newsletter content
- Email copy
- Short-form social media posts

### 🎨 AI Image Generation

The workflow generates a marketing image based on the content topic and
target audience and stores the generated image in Google Drive.

### 📅 Content Scheduling

Generated content can be scheduled through Google Calendar with publishing
information and platform details.

### 📊 Analytics Tracking

The system maintains content and engagement metrics such as:

- Views
- Likes
- Comments
- Shares
- Reach
- Clicks

The workflow also includes a YouTube statistics integration for retrieving
video statistics.

### 📧 Automated Email Delivery

A complete generated content package can be delivered through Gmail in a
structured HTML email containing the generated marketing assets.

### 💾 Data Storage

Generated content and related information can be stored using:

- Google Sheets
- Supabase

---

## 🏗️ Workflow Architecture

```text
                    ┌─────────────────────┐
                    │   Web Dashboard     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   n8n Webhook        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Validate & Defaults │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   AI Content Engine │
                    │    Groq / Llama     │
                    └──────────┬──────────┘
                               │
                    ┌──────────┴──────────┐
                    │                     │
                    ▼                     ▼
          ┌──────────────────┐   ┌──────────────────┐
          │ Content Package  │   │ Content          │
          │ Generation       │   │ Repurposing      │
          └────────┬─────────┘   └────────┬─────────┘
                   │                      │
                   └──────────┬───────────┘
                              ▼
                    ┌─────────────────────┐
                    │ AI Image Generation │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Google Drive        │
                    └─────────────────────┘

                              │
              ┌───────────────┼────────────────┐
              ▼               ▼                ▼
       ┌────────────┐  ┌────────────┐  ┌────────────┐
       │ Gmail      │  │ Google     │  │ Supabase   │
       │ Delivery   │  │ Sheets     │  │ Storage    │

       └────────────┘  └────────────┘  └────────────┘

                              │
                              ▼
                    ┌─────────────────────┐
                    │ Google Calendar     │
                    │ Scheduling          │
                    └─────────────────────┘

| Technology       | Purpose                        |
| ---------------- | ------------------------------ |
| n8n              | Workflow automation            |
| Groq             | AI model inference             |
| Llama 3.3 70B    | Content generation             |
| Supabase         | Content data storage           |
| Google Sheets    | Content and analytics tracking |
| Google Drive     | Generated image storage        |
| Google Calendar  | Content scheduling             |
| Gmail            | Automated content delivery     |
| YouTube Data API | Video statistics               |
| Bolt             | Web dashboard                  |
