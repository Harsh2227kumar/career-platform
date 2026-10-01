# Implementation Plan (Architecture & Execution)

This document outlines **HOW** the system will be built at a technical level. It defines the rules of architecture, technology choices, and strict boundaries to ensure the 3 members do not overwrite each other's work or encounter massive tech debt on Day 7.

## 1. Overall Tech Stack
*   **Frontend:** Next.js (App Router), React, Tailwind CSS (Mobile-First strictly enforced).
*   **Backend:** Node.js, Express.js (or Next.js API routes if preferred).
*   **Database:** MongoDB (via Mongoose for strict schema validation).
*   **Real-time & Events:** Socket.io (for chat), Redis or native Webhooks (for cross-domain events).

## 2. Database Strategy & Strict Ownership
To avoid merge conflicts and schema chaos, the single MongoDB database is logically partitioned. **No member may write to a collection they do not own.**

*   **Member 1 owns:** `jobs`, `kanban_boards`, `resumes`
*   **Member 2 owns:** `mentors`, `bookings`, `sessions`
*   **Member 3 owns:** `users`, `referrals`, `wallets`, `chats`

*Rule for Cross-Domain Data:* If M1 needs user profile data, M1 fetches it via M3's API or reads the shared JWT, but M1 NEVER directly queries `db.users.find()`.

## 3. Strict API Contracts (Day 1 Requirement)
Before writing any UI or Backend logic, members MUST define their TypeScript Interfaces or Swagger/Postman contracts. 
*Example: Member 3 must define the Wallet Response Schema on Day 1:*
```typescript
interface WalletResponse {
  userId: string;
  creditBalance: number;
  transactions: Transaction[];
}
```
If Member 1 uses mock data, it MUST match this exact shape. This guarantees that when M1 and M3 connect their code on Day 4, the UI does not break.

## 4. Phase-Wise Technical Execution

### Phase 1 Execution (Days 1-2)
*   **Member 1 Setup:** Establish job scraper scripts or standard API ingestions. Create the `jobs` collection schema. Use a local React state matrix for Kanban drag-and-drop before connecting to the DB.
*   **Member 2 Setup:** Integrate Stripe/Razorpay Sandbox SDKs. Design the complex time-zone aware schema for mentor availability matrices.
*   **Member 3 Setup:** Implement JWT Authentication, HTTP-only cookie management, and Role-Based Access Control (RBAC) middleware. Deploy the initial cloud MongoDB cluster and share the `.env` connection string.

### Phase 2 Execution (Days 3-5)
*   **Member 1 Setup:** Integrate `pdf-parse` or `pdf2json` libraries for the ATS backend. Setup `node-cron` for daily Telegram/WhatsApp alerts via Twilio/Telegram bots.
*   **Member 2 Setup:** Implement OAuth2.0 for Google Calendar API. Use Zoom Server-to-Server OAuth apps for automated meeting link generation.
*   **Member 3 Setup:** Establish a WebSocket (Socket.io) server. **CRITICAL:** Implement ACID-compliant Mongoose transactions (using `session.startTransaction()`) for the Credit Wallet system to prevent race conditions during point deductions.

### Phase 3 Execution (Days 6-7)
*   **Member 1 Setup:** Integrate LLM APIs (OpenAI/Claude). Force the LLM to output structured JSON for AI Closed-loop Resume scoring to ensure predictable UI rendering. Develop `manifest.json` for the Chrome Extension.
*   **Member 2 Setup:** Setup cross-domain Event Emitters. When M1 updates a Kanban card to "Interview", M1's backend emits a `KANBAN_UPDATED` event. M2's backend listens to this event to trigger Context-Aware mentor suggestions.
*   **Member 3 Setup:** Add distinct authentication middleware for `/employer` routes. Implement secure refund gateways and audit logging for platform compliance.
