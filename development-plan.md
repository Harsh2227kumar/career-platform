# Development Plan (1-Week Sprint)

This document outlines **WHAT** will be built and **WHEN**, mapping the tasks across the 3 team members over a strict 7-day timeline.

## Phase 1: MVP & Core Workflows (Days 1 - 2)
*Goal: Prove core independent features rapidly. Establish base UI and Schemas.*

### Member 1: Job Engine Domain
*   **Day 1:** Build Job Aggregation UI (Listings, Batch/Location Filters) and finalize `Job` database schema. Ensure Mobile-First responsiveness.
*   **Day 2:** Build personal Kanban Board Tracker UI (Wishlist -> Applied -> Interview -> Offer) with drag-and-drop functionality.

### Member 2: Mentorship Domain
*   **Day 1:** Build Mentor Public Profile (Storefront) UI and service listing creation flow (setting prices/durations).
*   **Day 2:** Build Scheduling flow (availability matrix, slot picking UI) and a schema-compliant mock checkout page.

### Member 3: Core & Referral Domain
*   **Day 1:** Build Multi-role Authentication (Seeker/Referrer/Mentor switcher) and Shared Career Profile UI.
*   **Day 2:** Build standalone Referral Request flow (Seeker UI to request -> Referrer Dashboard to accept/decline).

---

## Phase 2: Advanced Features & Cross-Integration (Days 3 - 5)
*Goal: Build domain-specific advanced features, introduce gamification, and integrate domains.*

### Member 1: Job Engine Domain
*   **Day 3:** Build Resume Builder UI and ATS Checker logic (formatting and keyword checks).
*   **Day 4:** Implement automated follow-up reminders.
*   **Day 5:** Set up WhatsApp/Email job alerts (CRON jobs).

### Member 2: Mentorship Domain
*   **Day 3:** Build the Reviews & Testimonials system.
*   **Day 4:** Build Priority DM UI (paid async chat) and Mentorship Packages/Bundles.
*   **Day 5:** Integrate Video API (Zoom/Meet links) and Calendar Sync.

### Member 3: Core & Referral Domain
*   **Day 3:** Build Earn-to-Refer Credit Economy (Wallets, Credits per action logic).
*   **Day 4:** Build gamified Leaderboard.
*   **Day 5:** Build In-App Messaging module between seekers and referrers/mentors.

---

## Phase 3: AI Quality Control & B2B Polish (Days 6 - 7)
*Goal: AI implementation, final polish, and opening the platform to businesses.*

### Member 1: Job Engine Domain
*   **Day 6:** Build AI Resume Scoring for "Closed-Loop Control" (checking resumes against specific job descriptions).
*   **Day 7:** Build Browser Extension for 1-click job import to the Kanban board.

### Member 2: Mentorship Domain
*   **Day 6:** Build Context-Aware Mentorship Prompts (listen to M1's Kanban state changes to dynamically suggest mentors).
*   **Day 7:** Finalize Provider Payout logic, Platform Commission cuts, and Discount Codes.

### Member 3: Core & Referral Domain
*   **Day 6:** Build Employer Dashboard for B2B hiring analytics and verified candidate pools.
*   **Day 7:** Build Referral Status Refund logic, trust signals (employment verification UI), and Admin panel.
