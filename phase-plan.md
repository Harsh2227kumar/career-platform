# Unified Career Acceleration Platform - Blueprint & Plan

## 1. Project Overview & Vision
Based on the synthesis of `combined_features.md` and `Career_Platform.docx.pdf`, this platform is designed as a **Unified Career Ecosystem** that eliminates market fragmentation by bringing job discovery, tracking, referrals, and mentorship under one roof.

**Core Offerings:**
1. **Job Aggregation & Tracking:** Batch-wise job filters, verified links, and an integrated Kanban board tracker (Wishlist -> Applied -> Interview -> Offer).
2. **Verified Referral Marketplace:** 1-Click referral requests to verified employees, safeguarded by an AI Resume Scoring system (requires 80%+ match to maintain quality).
3. **1-on-1 Consulting & Mentorship:** Instant calendar scheduling with verified professionals for mock interviews and resume reviews.

**Key USPs to Build:**
*   **1-Click Referral Request:** Direct referral requests from within a job card.
*   **Context-Aware Prompts:** System automatically suggests an ex-employee mentor when a user moves a job to the "Interview" stage.
*   **Earn-to-Refer Credit Economy:** A gamified loop where students earn credits to unlock referrals and mentors monetize their time.

---

## 2. Strategy for Zero-Dependency Development (1-Week Sprint)
To ensure seamless and extremely rapid development among **3 members** over a **7-Day timeline**, the project is divided into **Vertical Domains**. 
Each member will operate as a Full-Stack developer for their specific domain, handling their own UI pages, backend routes, and database collections. By assigning specific routes to specific members, development happens entirely in parallel without merge conflicts or blocking dependencies.

*   **Member 1 (Job Engine Domain):** Handles Jobs, Tracking, and Prep Tools. 
    *(Routes: `/jobs`, `/tracker`, `/resume-tools`)*
*   **Member 2 (Mentorship Domain):** Handles Expert Profiles, Scheduling, Video, and Payments. 
    *(Routes: `/mentors`, `/book`, `/sessions`)*
*   **Member 3 (Core & Referral Domain):** Handles User Auth, Referral Flows, Wallets, and Platform Admin. 
    *(Routes: `/auth`, `/profile`, `/referrals`, `/employer`)*

---

## 3. Development Plan (Phase-wise & Member-wise)
*This section defines **WHAT** is being built, the tasks, and aggressive 7-day deadlines.*

### Phase 1: MVP & Core Workflows (Days 1 - 2)
*Goal: Prove core independent features rapidly before connecting them. Every member mocks external data if needed to avoid waiting on others.*

*   **Member 1 (Job Engine & Tracking)**
    *   **Task 1.1 (Deadline: Day 1):** Build Job Aggregation UI (Listings, Filters by batch/role/location) and underlying database schema.
    *   **Task 1.2 (Deadline: Day 2):** Build personal Kanban Board Tracker UI with drag-and-drop functionality.
    *   *Independence Factor:* Member 1 uses a hardcoded dummy user ID to build tracking logic without waiting for Auth.
*   **Member 2 (Mentorship & Consulting)**
    *   **Task 2.1 (Deadline: Day 1):** Build Mentor Public Profile (Storefront) UI and service listing creation flow (setting prices/durations).
    *   **Task 2.2 (Deadline: Day 2):** Build Scheduling flow (availability matrix, slot picking) and a mock checkout page.
    *   *Independence Factor:* Self-contained booking module that assumes the user is authenticated.
*   **Member 3 (Core Auth & Referrals)**
    *   **Task 3.1 (Deadline: Day 1):** Build Multi-role Authentication (Seeker/Referrer/Mentor switcher) and Shared Career Profile UI.
    *   **Task 3.2 (Deadline: Day 2):** Build standalone Referral Request flow (Seeker UI to request -> Referrer Dashboard to accept/decline).
    *   *Independence Factor:* Referral dashboard acts entirely independently from the main job board for now.

### Phase 2: Advanced Features & Cross-Integration (Days 3 - 5)
*Goal: Build domain-specific advanced features and implement gamification.*

*   **Member 1 (Job Engine & Tracking)**
    *   **Task 1.3 (Deadline: Day 4):** Build Resume Builder UI and ATS Checker logic (formatting and keyword checks).
    *   **Task 1.4 (Deadline: Day 5):** Implement automated follow-up reminders and set up WhatsApp/Email job alerts.
    *   *Independence Factor:* Alert scripts run as isolated backend cron jobs.
*   **Member 2 (Mentorship & Consulting)**
    *   **Task 2.3 (Deadline: Day 4):** Build the Reviews & Testimonials system and Priority DM UI (paid async chat).
    *   **Task 2.4 (Deadline: Day 5):** Develop Mentorship Packages/Bundles and custom offering questions file upload feature.
    *   *Independence Factor:* External API integrations don't touch other team members' internal code.
*   **Member 3 (Core Auth & Referrals)**
    *   **Task 3.3 (Deadline: Day 4):** Build Earn-to-Refer Credit Economy (Wallets, Credits per action) and gamified Leaderboard.
    *   **Task 3.4 (Deadline: Day 5):** Build In-App Messaging module between seekers and referrers/mentors.
    *   *Independence Factor:* Wallet system updates are isolated to the User schema; chat is a standalone service.

### Phase 3: AI Quality Control, Polish & Employer B2B (Days 6 - 7)
*Goal: AI implementation, final polish, and opening the platform to businesses.*

*   **Member 1 (Job Engine & Tracking)**
    *   **Task 1.5 (Deadline: Day 6):** Build AI Resume Scoring for "Closed-Loop Control" (checking resumes against specific job descriptions).
    *   **Task 1.6 (Deadline: Day 7):** Build Browser Extension for 1-click job import to the Kanban board.
    *   *Independence Factor:* Extensions and AI microservices are standalone tools.
*   **Member 2 (Mentorship & Consulting)**
    *   **Task 2.5 (Deadline: Day 6):** Build Context-Aware Mentorship Prompts (listening to Member 1's Kanban state changes to dynamically suggest mentors).
    *   **Task 2.6 (Deadline: Day 7):** Finalize Provider Payouts, Platform Commission cuts, and Discount Codes.
    *   *Independence Factor:* Webhooks/Events allow Member 2 to react to Member 1's board without directly modifying Member 1's code.
*   **Member 3 (Core Auth & Referrals)**
    *   **Task 3.5 (Deadline: Day 6):** Build Employer Dashboard for B2B hiring analytics and verified candidate pools.
    *   **Task 3.6 (Deadline: Day 7):** Build Referral Status Refund logic, trust signals (employment verification checks), and Admin panel.
    *   *Independence Factor:* B2B dashboard is an entirely isolated route namespace (`/employer`).

---

## 4. Implementation Plan
*This section defines **HOW** the system will be built architecturally phase-by-phase.*

### Overall Architecture & Rules
*   **Tech Stack:** Next.js (Frontend unified shell), Node.js/Express (Backend API), MongoDB (Database).
*   **Database Strategy (Strict Boundary):**
    *   M1 owns Collections: `jobs`, `kanban_boards`, `resumes`
    *   M2 owns Collections: `mentors`, `bookings`, `sessions`
    *   M3 owns Collections: `users`, `referrals`, `wallets`, `chats`
*   **Git Workflow:** Folder-based ownership. M1 only merges into `/src/jobs`, M2 into `/src/mentorship`, etc.

### Member-Wise Implementation Execution

#### Phase 1 Implementation Setup (Days 1-2)
*   **Member 1:** Write scraping scripts/integrations to populate the `jobs` database. Establish local React state management for dragging/dropping Kanban cards.
*   **Member 2:** Integrate Stripe/Razorpay Sandbox APIs for the checkout flows. Design the complex time-zone aware schema for mentor availability matrices.
*   **Member 3:** Implement JWT Authentication, cookie management, and Role-Based Access Control (RBAC) middleware. Deploy the initial cloud database cluster.

#### Phase 2 Implementation Setup (Days 3-5)
*   **Member 1:** Integrate parsing libraries (e.g., `pdf2json`) for the ATS checker backend. Setup CRON jobs for daily Telegram/Email alerts.
*   **Member 2:** Implement OAuth2.0 for Google Calendar API and video conferencing SDKs (Zoom/Meet) for automated meeting link generation.
*   **Member 3:** Set up a WebSocket (Socket.io) server for real-time messaging. Implement ACID-compliant database transactions for the Credit Wallet system to prevent race conditions during point deductions.

#### Phase 3 Implementation Setup (Days 6-7)
*   **Member 1:** Integrate LLM APIs (OpenAI/Claude) with strict structured JSON output for AI Closed-loop Resume scoring. Develop the `manifest.json` and background workers for the Chrome Extension.
*   **Member 2:** Setup Event Emitters (e.g., Redis Pub/Sub or native Node Events) to listen for Kanban board database updates, triggering Context-Aware mentor suggestions.
*   **Member 3:** Set up distinct authentication guards for B2B Employer routes. Implement secure refund gateways and logging mechanisms for platform compliance.
