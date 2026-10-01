# Universal AI Prompts for Development

This file contains standardized prompts that any of the 3 members can copy and paste into their AI coding assistants (e.g., Copilot, ChatGPT, Claude, Cursor) to ensure perfectly aligned development, automated checks, and adherence to team rules.

Whenever you see `[Member X]`, replace it with your assigned member number (1, 2, or 3) and domain.

---

## 1. Project Onboarding & Context Setting
*Use this prompt at the very beginning of a new AI chat to give the AI complete context about the project, the zero-dependency strategy, and your specific role.*

**Prompt:**
> "Read all the `.md` files in this directory (`combined_features.md`, `team-rules.md`, `development-plan.md`, `implementation-plan.md`, `CONTRIBUTING.md`). Understand the vision for the Unified Career Acceleration Platform, the 'Vertical Domains' zero-dependency strategy, and the strict rules against hardcoding. 
> 
> I am **[Member X: e.g., Member 1 - Job Engine Domain]**. Please analyze my specific responsibilities, my tech stack ownership, and my tasks for this 7-day sprint. Output a summary of my exact scope, the database collections I own, and a detailed execution plan for my Day 1 tasks."

---

## 2. Generate Detailed Code-Writing Prompt
*Use this when you are about to start a new task and want the AI to generate a highly detailed sub-prompt for Codex/Cursor to write the actual code perfectly.*

**Prompt:**
> "Using the context from the MD files, prepare a highly detailed prompt that I can copy-paste into another AI chat to write the code for **[Task Name / Number, e.g., Task 1.2 Kanban Board]**. 
>
> Ensure the generated prompt instructs the coding AI to:
> 1. Restrict its scope ONLY to my domain.
> 2. strictly enforce mobile-first Tailwind CSS responsiveness.
> 3. Refuse to use hardcoded dummy data; instead, it must define and use strict TypeScript schemas/interfaces.
> 4. Include the exact tech stack components required for this specific task."

---

## 3. Phase / Task Completion Checker
*Use this prompt before you consider a task "done" to have the AI audit your codebase and find missing requirements.*

**Prompt:**
> "Checklist before Push: Read my uncommitted changes and scan the current state of my domain's codebase. Cross-reference this with my specific tasks for **[Phase X / Day Y]** as defined in `development-plan.md` and the rules in `team-rules.md`. 
> 
> Create a strict checklist. Are all my tasks for this phase completed? Tell me exactly what things are left. Specifically check for:
> - Any missing features or UI components.
> - Any hardcoded data that needs to be replaced with a schema-compliant mock or API call.
> - Any components that lack responsive mobile-first Tailwind classes."

---

## 4. Update Project Change Tracker
*Use this prompt right after finishing a feature and before pushing to Git, to keep a running log of all team changes.*

**Prompt:**
> "Update the Tracker MD file: Please read the `project-change-tracker.md` file (create it if it does not exist). Read the existing checkpoints first and do NOT duplicate older entries. 
> 
> Add one new checkpoint ONLY for the uncommitted changes I have made right now. Include the following format:
> - **Date:** 
> - **Member Name:** [Member X]
> - **Branch:** [Current Branch]
> - **Summary:** 
> - **Completed Tasks:** 
> - **Code/File Changes:** (Brief list of modified files)
> - **Features added/updated/removed:** 
> - **Issues fixed:** 
> - **Notes for the next push / Next steps:**"

---

## 5. GitHub Push & Contribution Rules Checker
*Use this prompt as the absolute final step before committing and pushing your code to GitHub.*

**Prompt:**
> "Github Push: I want to commit and push my changes. First, strictly read and follow the rules in `CONTRIBUTING.md` and `team-rules.md`. 
> 
> 1. Verify that my current branch name follows the required naming conventions (e.g., `feature/...`, `fix/...`) and maps to my correct domain base branch.
> 2. Make sure to update `.gitignore` and add necessary files/folders for the backend and frontend if and only if required (e.g., `node_modules`, `.env`).
> 3. Verify I have not altered another member's domain folders.
> 4. Generate the exact `git add`, `git commit` (using Conventional Commits), and `git push` commands I need to run to safely push my work."
