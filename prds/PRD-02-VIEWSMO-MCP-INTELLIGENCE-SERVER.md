# Product Requirement Document (PRD): Autonomous Creator Intelligence MCP Server
**Product**: Viewsmo AI  
**Author**: Rishav Bhardwaj (Technical Product Manager)  
**Status**: Production / Shipped  
**Target Release**: Q4  

---

## 1. Executive Summary & Problem Statement
Content creators and digital marketing agencies spend 15+ hours weekly manually analyzing YouTube retention drop-offs, metadata tags, and competitor keywords. Existing web dashboards require manual CSV exports and fragmented tab switching.

**Product Objective**: Build an official **Model Context Protocol (MCP)** server that exposes Viewsmo's proprietary video analytics and retention forecasting models directly to AI agents (Claude Desktop, Cursor, Antigravity IDE) via structured JSON-RPC over stdio.

---

## 2. Target Personas
- **Agency Growth Leads**: Automate batch channel audits across 50+ client accounts via natural language prompts.
- **Solo YouTubers**: Draft viral 3-act retention outlines and score thumbnail/title SEO directly inside AI writing workspaces.

---

## 3. Functional Specifications & Tool Endpoints
1. `viewsmo_audit_channel(handle: string)`: Computes SEO health score, tag distribution, and retention velocity.
2. `viewsmo_score_video_seo(title: string, description: string, tags: string[])`: 100-point algorithmic scorecard.
3. `viewsmo_generate_script_outline(topic: string, format: 'short' | 'longform')`: Generates hook and retention bridge.

---

## 4. Monetization & Rate Limiting
- **Free Tier**: 20 MCP queries/month.
- **Pro Tier ($29/mo via Stripe)**: Unlimited MCP queries, automated background video telemetry via static FFmpeg workers.
