*Calimero — Technical Execution Roadmap*


**CALIMERO**

Technical Execution Roadmap

*Website & Mobile App Development*

|<p>**PROJECT TIMELINE**</p><p>**8 Weeks (2 Months)**</p><p>MVP Launch Ready</p>|
| :-: |

Version 1.0 — December 2025


# **1. Executive Summary**
This document outlines the technical execution plan for building the Calimero digital ecosystem within a **strict 8-week timeline**. The project delivers three core products:

- **kids.calimero.com** — COPPA-compliant children's website with safe AI chat
- **calimero.com** — Adult website with culture, commerce, and AI features
- **Calimero Kids App** — React Native mobile app with voice AI companions

All AI traffic is routed through a centralized NestJS backend with safety filtering, moderation, and session management.

# **2. Assumptions & Constraints (Locked)**
The following assumptions are locked and must be met before development begins:

1. **UX/UI Designs:** All designs finalized and approved in Figma
1. **Two Web Platforms:** kids.calimero.com (COPPA) + calimero.com (adult)
1. **One Mobile App:** Kids-only React Native app (iOS + Android)
1. **AI Provider:** External LLM API (Claude recommended, provider TBD)
1. **Session Context:** In-memory only, no persistent chat history
1. **Backend Routing:** All AI traffic through NestJS backend
1. **Frontend Hosting:** Vercel (Next.js apps)
1. **Backend Hosting:** Dedicated server (NestJS)
1. **Timeline:** 8 weeks total execution

# **3. Target Architecture**
## **3.1 System Overview**

|**Layer**|**Components**|
| :-: | :-: |
|**Clients**|Next.js Kids Web App, Next.js Adult + Kids Web App, React Native Mobile App|
|**Backend**|NestJS API Server (TypeScript)|
|**External APIs**|LLM API (Together AI), Speech-to-Text API, Text-to-Speech API|
|**Infrastructure**|Vercel (Web hosting), Dedicated Server (Backend)|
## **3.2 Backend Core Modules (NestJS)**

|**Module**|**Responsibilities**|
| :-: | :-: |
|**API Gateway**|Auth validation (adult site), rate limiting, request validation|
|**AI Orchestrator**|Character prompt injection, session memory (TTL), LLM abstraction|
|**Safety & Moderation**|Input/output filtering, topic boundaries, emergency detection|
|**Voice Pipeline**|STT adapter, TTS adapter, audio stream normalization|
|**Parental Controls**|Time limits, feature toggles, PIN verification|
|**Content Delivery**|CMS proxy, locale resolution, content caching|
|**Observability**|Structured logs (no PII), error tracking, AI cost metrics|


# **4. AI Interaction Flow**
The following flow applies to both mobile and web AI interactions:

1. **User Input:** User speaks (voice) or types (text)
1. **Client Request:** Client sends request to NestJS backend
1. **Input Safety:** Safety layer validates and filters input
1. **AI Orchestrator:** Injects character persona + session memory
1. **LLM Request:** Request forwarded to LLM API
1. **Output Safety:** Response validated by output filter
1. **Text Response:** Clean text returned to client
1. **Voice (Optional):** Text sent to TTS, audio streamed to client
1. **Animation:** Client triggers Rive animation states

**CRITICAL:** No conversation data is persisted. All sessions are ephemeral.

# **5. Web Platforms (Next.js)**
## **5.1 Tech Stack**
- **Framework:** Next.js 14 (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS
- **CMS:** Headless CMS integration (Sanity/Contentful)
- **i18n:** Multi-language routing (IT, FR, EN)
## **5.2 SEO Strategy**
- Static generation (SSG) for all public pages
- Incremental Static Regeneration (ISR) for content updates
- Metadata per locale with Open Graph tags
- Structured data (JSON-LD) for rich snippets
- Optimized Core Web Vitals (LCP, FID, CLS)
## **5.3 Site Separation**

|**kids.calimero.com**|**calimero.com**|
| :-: | :-: |
|Separate repo & deployment|Separate repo & deployment|
|ZERO analytics/cookies|Full analytics (GA4, Meta Pixel)|
|No user accounts|User auth (NextAuth.js)|
|Text-only AI chat|AI character generator|
|COPPA compliant|E-commerce ready|


# **6. Mobile App (React Native)**
## **6.1 Tech Stack**
- **Framework:** React Native (TypeScript)
- **Animation:** Rive for character animations
- **Audio:** Native audio APIs for voice recording/playback
- **Storage:** Secure local storage (settings only, no chat)
- **Platforms:** iOS 15+ and Android 10+
##
## **6.2 Rive Animation Integration**
State machines per character with the following states:

|**State**|**Trigger**|
| :-: | :-: |
|**Idle**|Default state, subtle breathing animation|
|**Listening**|User is speaking, character shows attention|
|**Thinking**|Waiting for AI response|
|**Speaking**|Lip-sync driven by audio amplitude|
|**Happy/Sad**|Emotion states based on conversation context|

#
# **7. Security & Compliance**

|**Requirement**|**Implementation**|
| :-: | :-: |
|**No PII Storage**|No personal data collected or stored on kids platform|
|**No Chat Persistence**|All conversations ephemeral, in-memory only|
|**TLS Everywhere**|HTTPS enforced on all endpoints|
|**Strict CORS**|Only whitelisted origins allowed|
|**COPPA Compliance**|Full audit before kids platform launch|
|**Input Filtering**|All user input sanitized before LLM processing|
|**Output Filtering**|All AI responses validated before delivery|


# **8. Execution Plan (8 Weeks)**

|**Sprint**|**Duration**|**Deliverables**|
| :-: | :-: | :-: |
|**Sprint 0**|3 days|Repo setup, infra provisioning, architecture validation|
|**Sprint 1**|Week 1|Backend skeleton, AI orchestrator MVP, web app scaffolding|
|**Sprint 2**|Week 2|AI text chat E2E, safety layer v1, CMS integration |
|**Sprint 3**|Week 3|Voice pipeline (STT + TTS), mobile app scaffold|
|**Sprint 4**|Week 4|Rive animation integration, mobile AI MVP|
|**Sprint 5**|Week 5|Parental controls, time limits, adult site features|
|**Sprint 6**|Week 6|SEO finalization, i18n, content population|
|**Sprint 7**|Week 7|Hardening, load testing, bug fixes|
|**Sprint 8**|Week 8|**COPPA audit, final QA, LAUNCH 🚀**|

# **9. Risks & Mitigation**

|**Risk**|**Impact**|**Mitigation**|
| :-: | :-: | :-: |
|LLM provider instability|High|Abstraction layer for provider swap|
|Voice latency|Medium|Streaming + text fallback|
|Scope creep|High|Strict MVP enforcement|
|Design delays|High|Designs locked before Sprint 0|
|App Store rejection|Medium|COPPA pre-audit, guidelines review|

# **10. Post-MVP Features (Deferred)**
The following features are explicitly **OUT OF SCOPE** for the 8-week MVP and will be considered for future releases:

1. Persistent user profiles and preferences
1. Advanced AI personalization based on history
1. Self-hosted AI models
1. Advanced analytics dashboard
1. E-commerce integration (Shopify)
1. Push notifications
1. Additional languages beyond IT/FR/EN


# **11. Deliverables Summary**

|**Deliverable**|**Status at Week 8**|
| :-: | :-: |
|**kids.calimero.com**|Live on Vercel, COPPA compliant|
|**calimero.com**|Live on Vercel, user auth ready|
|**Calimero Kids App**|TestFlight + Play Store Beta|
|**NestJS Backend**|Production deployed, monitored|
|**AI Chat (Text)**|Working on all platforms|
|**AI Voice (Mobile)**|Working with Rive animations|
|**Parental Controls**|Time limits, PIN, feature toggles|
|**Documentation**|API docs, deployment guide, handover|

*— End of Document —*

Confidential — Dar Blockchain • Page  of 
