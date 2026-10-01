# Combined Feature List for Our New Platform

**Sources merged (3 websites):**
- **[T] Topmate** – expert/mentor storefront and booking (from `features.md` + `features__1_.md`)
- **[F] FreshersHunt** – jobs, internships, drives, career tools and alerts (from `features.md` + `features__1_.md`)
- **[R] ReferKaro** – referral marketplace, mentors, CV/ATS, tracker, packages (from `ReferKaro_business_model.docx`)


**Tags:** 🟢 MVP · 🟡 Next · 🔵 Later
**Origin:** shows which website(s) the feature comes from. Where two or three sites have it, it is a proven, user-liked feature.

---

## 1. Accounts and Profiles

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 1.1 | Multi-role accounts (Seeker / Referrer / Mentor; one person can hold several roles) | R | 🟢 | Single login, role switcher, separate dashboards |
| 1.2 | Shared Student Career Profile | F+R (idea) | 🟢 | Education, grad year, skills, projects, experience, preferred roles/locations, resume. User controls what is public vs. used only for matching |
| 1.3 | Public Mentor/Expert profile (storefront) | T | 🟢 | Photo, headline, bio, role, company, expertise, social links, services, prices, availability, reviews, shareable URL |
| 1.4 | Referrer profile with performance signals | R | 🟢 | Company, role, response rate, completion rate, ratings |
| 1.5 | Profile themes, highlights and badges | T | 🔵 | Customization and credibility badges |
| 1.6 | Resume/CV upload and storage | R+F | 🟢 | Store one resume per user, reuse across applications |

## 2. Job and Opportunity Discovery

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 2.1 | Job listings with structured fields | F+R | 🟢 | Title, company, location, work mode, role type, experience level, eligibility, salary, deadline, apply link |
| 2.2 | Separate Internship listings | F | 🟢 | Duration, stipend, skills, eligibility |
| 2.3 | Off-campus drives | F | 🟢 | Dedicated category |
| 2.4 | Walk-in drives | F | 🟡 | Date, venue, documents required |
| 2.5 | Search (roles, companies, keywords) | F+R | 🟢 | Global search bar |
| 2.6 | Filters: Batch / Location / Company / Work mode (Remote, Hybrid, On-site, WFH) | F | 🟢 | Combined filter panel; city pages (Bengaluru, Hyderabad, Pune, etc.) |
| 2.7 | Company directory / company pages | F+R | 🟢 | All openings per company, plus referrers available there |
| 2.8 | Eligibility, salary/stipend and deadline display | F | 🟢 | Label "confirmed" vs. "estimated/not provided" |
| 2.9 | Direct/official apply links | F | 🟢 | Label official vs. third-party links |
| 2.10 | Job verification and source checking | F+R | 🟢 | Show source, last-checked date, verification status; report-listing button |
| 2.11 | Personalized, fit-ranked job feed | R | 🔵 | Ranked using the career profile |
| 2.12 | Explainable job matching | F+R (idea) | 🔵 | Show matched/missing requirements and source date. **Do not** show it as hiring probability |
| 2.13 | Non-IT roles (Finance, Marketing, HR, Ops, Sales) | F | 🟡 | Category coverage beyond IT |

## 3. Referral Marketplace

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 3.1 | Verified employee referrers | R | 🟢 | Employment + identity verification |
| 3.2 | Referral request flow (request, accept, submit) | R | 🟢 | Seeker picks a job, referrer accepts/declines, submission confirmed |
| 3.3 | Referral status tracking | R | 🟢 | Requested → Accepted → Submitted |
| 3.4 | Referral credits/tokens | R | 🟢 | Pay per referral; credit packs |
| 3.5 | Intelligent referrer matching | R | 🔵 | Match by company, role, referrer track record |
| 3.6 | Refund windows tied to submission status | R | 🟢 | Refund depends on whether referral was submitted, never on job outcome |
| 3.7 | Leaderboard | R | 🟡 | Top referrers/helpers |
| 3.8 | Messaging between seeker and referrer/mentor | R | 🟢 | In-app chat |

## 4. Mentor / Expert Services (Marketplace)

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 4.1 | One-to-one sessions | T+R | 🟢 | Mentor sets format, duration, description, price |
| 4.2 | Discovery / intro calls | T | 🟡 | Short free or low-cost first call |
| 4.3 | Mock interviews | T+R | 🟢 | Role/company focus, feedback included |
| 4.4 | Resume and profile reviews by humans | T+R | 🟢 | Upload resume, get written feedback |
| 4.5 | Career guidance sessions | T+R | 🟢 | Career switch, growth, portfolio feedback |
| 4.6 | Priority DM (paid async question) | T | 🟡 | Question + response-time promise |
| 4.7 | Group sessions and webinars | T | 🟡 | Multi-attendee events |
| 4.8 | Courses and digital products | T | 🔵 | Guides, templates, downloadable resources |
| 4.9 | Packages and bundles of services | T+R | 🟡 | Several sessions/reviews sold as one offer |
| 4.10 | Cohorts / structured programs | T | 🔵 | Multi-week programs with sessions and assignments |
| 4.11 | Custom offering questions and file upload | T | 🟢 | Mentor asks questions/requests resume before a call |
| 4.12 | Mentor discovery/marketplace search | T | 🟢 | Browse by topic, role, price |
| 4.13 | Job-to-Mentor connection | F+T (idea) | 🟡 | On a job page, suggest mentors for that role/interview type |

## 5. Booking, Scheduling and Payments

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 5.1 | Availability setup and self-service booking | T | 🟢 | Choose service → view price → pick slot → details → pay → confirmation |
| 5.2 | Calendar sync | T | 🟡 | Google/Outlook calendar |
| 5.3 | Video meeting integration | T | 🟡 | Auto-generated Zoom/Meet link |
| 5.4 | WhatsApp reminders/communication | T+F | 🟡 | Booking reminders and alerts |
| 5.5 | Integrated checkout | T+R | 🟢 | One flow from discovery to payment |
| 5.6 | Provider payouts and platform commission | T+R | 🟢 | Platform fee per transaction; payouts to referrers/mentors |
| 5.7 | Discount codes | T | 🟡 | Promo codes |
| 5.8 | Follow-up emails (buy-again, cart abandonment) | T | 🔵 | Automated re-engagement |

## 6. Resume, CV and Application Tools

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 6.1 | Resume Builder | F | 🟡 | Guided fields and templates |
| 6.2 | ATS Checker / CV scoring | F+R | 🟢 | Keyword, structure, formatting checks. Present score as an **estimate** |
| 6.3 | CV analysis against a job description | R | 🟡 | Explain gaps for a chosen role |
| 6.4 | Job-specific CV customization | R | 🟡 | AI suggests edits; user confirms |
| 6.5 | Cover Letter Generator | F | 🟡 | Draft from profile + job; user reviews |
| 6.6 | HR Email Templates | F | 🟡 | Follow-ups, application emails |
| 6.7 | LinkedIn profile review | R | 🟡 | Mentor service or tool |
| 6.8 | Salary Calculator | F | 🟡 | Take-home estimate; show assumptions |

## 7. Preparation Resources

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 7.1 | Interview questions library | F | 🟡 | By company, role, topic |
| 7.2 | Aptitude tests (timed) | F | 🟡 | Practice test engine |
| 7.3 | Career advice articles and guides | F | 🟢 | Blog/guide section |
| 7.4 | Free courses and learning resources | F | 🔵 | Curated links/courses |
| 7.5 | Free tools without signup | F | 🟢 | Lets visitors try tools before registering |
| 7.6 | Preparation plan linked to a target job | F+R (idea) | 🟡 | Checklist: learn skill, practice, review resume, book mentor |
| 7.7 | Interview prep (AI-assisted) | R | 🔵 | Practice and feedback |

## 8. Tracking and Retention

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 8.1 | Save jobs | F+R | 🟢 | Bookmark listings |
| 8.2 | Application Tracker | R+F (idea) | 🟢 | Saved → Applied → Referral → Assessment → Interview → Offer → Closed, with deadlines, notes, interview dates, links |
| 8.3 | Unified journey record | R | 🟡 | One view of jobs, referrals, mentor sessions and status |
| 8.4 | Job alerts (Telegram / WhatsApp / email) | F | 🟢 | Free channels; user controls topics and frequency |
| 8.5 | Daily updates | F | 🟢 | New listings every morning |
| 8.6 | Premium/curated alerts | F | 🔵 | Paid, faster, ad-free curated alerts (avoid job-guarantee claims) |
| 8.7 | Career roadmap and progress dashboard | F+R (idea) | 🔵 | Milestones and progress |
| 8.8 | AI Career Agent | R | 🔵 | Proactively recommends jobs, referrers and next steps |

## 9. Trust, Safety and Transparency

| # | Feature | Origin | Priority | What to build |
|---|---------|--------|----------|---------------|
| 9.1 | Reviews and testimonials with moderation | T | 🟢 | Only from real completed bookings |
| 9.2 | Employment and identity verification for referrers/mentors | R | 🟢 | Show what was verified, how and when |
| 9.3 | Visible performance signals | R | 🟢 | Response rate, completion rate, ratings |
| 9.4 | No-guarantee language | R | 🟢 | Clear copy: no guaranteed job or referral outcome |
| 9.5 | Report suspicious listing/profile | F (idea) | 🟢 | Reporting button and review queue |
| 9.6 | Labeled paid promotions | F (idea) | 🟢 | Clearly mark sponsored content |
| 9.7 | Affiliate disclosure, Privacy Policy, Terms, About, Contact | F | 🟢 | Standard legal/info pages |

## 10. Monetization Model

| # | Feature | Origin | Priority |
|---|---------|--------|----------|
| 10.1 | Referral commission (platform fee per paid referral) | R | 🟢 |
| 10.2 | Mentor commission (per session) | T+R | 🟡 |
| 10.3 | Career packages: Free / Starter / Pro / Premium | R | 🟡 |
| 10.4 | Custom Career Plan (pick and choose services) | R | 🟡 |
| 10.5 | Credit/token packs | R | 🟢 |
| 10.6 | Weekly / Monthly / Lifetime alert subscription | F | 🔵 |
| 10.7 | AI tools subscription | R | 🔵 |
| 10.8 | Employer/B2B tools (referral campaigns, hiring analytics) | R | 🔵 |

Suggested package tiers (from ReferKaro, illustrative and needs validation):

| Tier | For | Includes | Indicative price |
|------|-----|----------|------------------|
| Free | Browsers | Job discovery, basic profile | ₹0 |
| Starter | Early search | ATS/CV analysis, 1 referral credit | ₹299–499 |
| Pro | Active seekers | CV customization, 3 referral credits, tracker | ₹999–1,499 |
| Premium | Interview stage | Mentor session, mock interview, priority referrals | ₹2,499–3,499 |
| Custom | Specific needs | Pick components | Sum of parts |

## 11. Employer / Recruiter Side (Later)

| # | Feature | Origin | Priority |
|---|---------|--------|----------|
| 11.1 | Employer dashboard | R | 🔵 |
| 11.2 | Referral program management and campaigns | R | 🔵 |
| 11.3 | Hiring analytics and sourcing | R | 🔵 |
| 11.4 | Hiring challenges | F+R (idea) | 🔵 |

---

## Best Features per Website (Quick View)

**From Topmate (T):** shareable expert storefront, service listings with price and duration, easy self-service booking, priority DM, group sessions, bundles/packages, calendar + video integration, testimonials, discount codes.

**From FreshersHunt (F):** structured job/internship/drive listings, batch + location + company + work-mode filters, deadline and eligibility clarity, official apply links, Telegram/WhatsApp alerts, free tools with no signup (resume builder, ATS checker, salary calculator, cover letter generator), aptitude tests, interview questions, HR email templates, career guides.

**From ReferKaro (R):** verified referrers, referral request and status flow, referral credits, mentor marketplace, ATS scoring and CV customization, application tracker, tiered packages and custom plan, leaderboard, no-guarantee and refund rules, trust signals.

## Features Found on Multiple Sites (Highest Confidence)

| Feature | Sites |
|---------|-------|
| Career-focused mentor/expert services (CV review, mock interview, guidance) | Topmate + ReferKaro |
| Resume/CV tools and ATS checking | FreshersHunt + ReferKaro |
| Company/job search and discovery | FreshersHunt + ReferKaro |
| Paid products/credits/packages | Topmate + FreshersHunt (Pro) + ReferKaro |
| Trust and verification signals | All three |
| Alerts/notifications | FreshersHunt + Topmate (WhatsApp) + ReferKaro (status) |

## Recommended Build Order

**Phase 1 – MVP (prove paid transactions)**
Accounts and roles, career profile, job/internship listings with search + filters, job detail with source/deadline/apply link, save jobs, referral request flow with credits and payments, mentor profiles and services, booking, in-app messaging, basic ATS checker, verification badges, reviews, free alerts, legal pages.

**Phase 2 – Career Platform**
Application tracker, packages and custom plans, resume builder, CV customization, cover letter and HR email tools, salary calculator, interview questions, aptitude tests, priority DM, group sessions, calendar/video/WhatsApp integrations, discount codes, leaderboard, job-to-mentor recommendations, prep checklists.

**Phase 3 – AI Career Agent**
Personalized job feed, explainable matching, AI referrer matching, AI interview prep, roadmap and progress dashboard, premium curated alerts, courses/cohorts.

**Phase 4 – Employer / B2B**
Employer dashboard, referral campaigns, hiring analytics, hiring challenges.

## Implementation Notes

1. **Show the source of each feature:** in the UI, do not copy site names; use your own branding. If you want to credit inspiration, put it in an internal doc, not the public site.
2. **Original design and text:** the source documents advise building original branding, content and interface, not copying protected design or text.
3. **No guarantees:** never promise a job or referral outcome; ATS scores and match scores are estimates.
4. **Verify before building:** Topmate/FreshersHunt details come from public marketing pages and may change; ReferKaro items marked "proposed" are plans, not live features. Pricing and commission figures (e.g., Topmate 10%/20%, FreshersHunt Pro ₹69/₹199/₹499, ReferKaro 25% illustrative) need validation for your own model.
5. **User control:** let users choose which alerts they get and which profile details are public.
