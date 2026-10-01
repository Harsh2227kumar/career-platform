# Team Development Rules: Do's and Don'ts

**CRITICAL DIRECTIVE:** Do not build with hardcoded data, arbitrary JSON, or incomplete schemas just to "make it work for now". Doing so will cause immense technical debt, merge conflicts, and synchronization efforts at the end of the 1-week sprint. 

All 3 members must strictly follow these rules to guarantee a seamless launch.

## 1. The Zero Hardcoding Policy
*   **DON'T** hardcode User IDs, Mentor IDs, Job descriptions, or Credit balances directly into your UI components or backend controllers.
*   **DON'T** use arbitrary JSON shapes for frontend state.
*   **DO** define the exact TypeScript interfaces (or Data Schemas) for your API responses **before** you write the UI. 
*   **DO** use a shared `mock-data.ts` file if you are waiting for an API to be finished. This mock data MUST strictly conform to the final database schema, so dropping in the real API later requires zero UI changes.

## 2. API & Schema Contracts
*   **DON'T** alter a shared database model (like the `User` object) without explicitly getting approval from the other 2 members.
*   **DON'T** assume what data another member's API will return.
*   **DO** treat your Vertical Domain like a public API. If Member 1 (Jobs) needs to know if a User has enough credits, Member 3 (Core) must provide a documented endpoint or context hook: `GET /api/wallets/balance`.
*   **DO** document your expected request/response payloads on Day 1.

## 3. Responsive by Default (No "Later")
*   **DON'T** build a page for Desktop only and say "I'll make it responsive on Day 6." There is no time for a separate responsive phase in a 7-day sprint.
*   **DON'T** use fixed pixel widths (e.g., `width: 800px`) that will break on mobile.
*   **DO** use Mobile-First styling (e.g., Tailwind CSS base classes for mobile, with `md:` and `lg:` prefixes for larger screens).
*   **DO** test every single component in Chrome DevTools mobile view *while* you are building it.

## 4. Strict Domain Isolation
*   **DON'T** edit files inside another member's folder. If you are Member 1, you never touch `/src/mentorship` or `/src/auth`.
*   **DON'T** write complex spaghetti code to bridge two domains. 
*   **DO** communicate via standard API calls, shared JWT tokens, or database Event Webhooks.

## 5. UI/UX Consistency
*   **DON'T** introduce random color hex codes or custom font sizes in your domain.
*   **DO** rely on a shared global CSS theme (e.g., `tailwind.config.js` or global CSS variables). Button paddings, hover states, and input borders must be identical across all 3 domains.
