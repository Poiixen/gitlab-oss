# Phase I: Issue Selection

**AI Corps x GitLab — Open Source Contribution Learning Path, Spring 2026**

---

## What This Phase Is About

Phase I is where your contribution journey begins. You have three jobs this week:

1. **Get set up as a GitLab contributor** so you have access to the tools and systems you'll use for the rest of the program.
2. **Create your Contribution README** — the living document that will track your entire journey through the program.
3. **Find one live GitLab issue** that you will work on for the next several weeks — and demonstrate that you understand what it's actually asking for.

This might sound like a lot, but each piece is straightforward. The onboarding takes about 30 minutes. The README takes 15 minutes to set up. The real work of Phase I is choosing your issue thoughtfully.

Your issue selection is the decision that shapes everything that follows. A well-chosen issue leads to a clear plan, productive build time, and a strong merge request. A poorly chosen issue leads to weeks of frustration, scope creep, and starting over.

GitLab's platform contains roughly **44,700 open issues** right now. You are not expected to read all of them. You are expected to use the resources below to narrow the field quickly and choose thoughtfully.

**Target duration: 1–3 days.** All three tasks should be complete by the end of your first week.

---

## What "Done" Looks Like

To complete Phase I, you need to do five things:

**1. Complete GitLab contributor onboarding** so you have access to community forks and the `@gitlab-bot` system.

**2. Create your Contribution README** by setting up a new public GitLab project and copying in the provided template.

**3. Update your README with:**

- A link to your chosen issue
- A 2–4 sentence problem summary explaining what the issue is, why it matters, and why you chose it

**4. Tag a Merge Request Coach on your chosen issue** by commenting `@gitlab-bot help` on the GitLab issue page.

**5. Submit your check-in form and indicate "Phase I Complete."**

No code. No local environment setup. No fork cloning. That all happens in Phase II. Phase I is about getting onboarded, setting up your README, choosing well, and establishing early contact with GitLab's review system.

---

## Step-by-Step Procedure

### Step 1: Complete GitLab Contributor Onboarding (30 minutes)

Before you can do anything else, you need to register as a GitLab contributor. This is a one-time setup that grants you access to the tools you'll use for the rest of the program.

**Go to [contributors.gitlab.com](https://contributors.gitlab.com) and start the onboarding process.**

When you do this:
- You'll receive an **onboarding issue** — a checklist in a GitLab project that walks you through the setup steps. Follow it to completion.
- You'll get access to **community forks** — shared repositories where all community contributions are made. This is important: GitLab does not use personal forks like you may be used to from GitHub. Everyone works in the same community fork.
- You'll be able to interact with **`@gitlab-bot`**, GitLab's system for connecting contributors with merge request coaches.

While you're at it, **join the [GitLab Community Discord](https://discord.gg/gitlab)** and look at the `#contribute` channel. This is where GitLab team members and the wider community answer contributor questions. It's a useful resource throughout the program alongside our own program Discord.

> **How to know you're done:** You can access the community fork at `gitlab.com/gitlab-community/gitlab`. If you can see that project and its branches, you're onboarded. If you're stuck on any onboarding step, post in `#sp26-issue-selection` on our [program Discord](https://discord.gg/YVVD9h9EJe) or email **contributors@gitlab.com**.

---

### Step 2: Create Your Contribution README (15 minutes)

Your **Contribution README** is the single most important artifact of this program. It is a living document hosted on your own GitLab project that tracks your entire journey — from issue selection through merge request submission. Mentors and staff will read your README to understand where you are, what you're working on, and how to help you. You will update it every week.

#### How to set it up:

1. **Create a new personal project on GitLab** to host your README:
   - Go to [gitlab.com/projects/new](https://gitlab.com/projects/new#blank_project)
   - Name it something clear like `ai-corps-contribution` or `sp26-gitlab-contribution`
   - Set visibility to **Public** (mentors and staff need to be able to view it)
   - Check **"Initialize repository with a README"**
   - Click **Create project**

2. **Copy the README template** into your new project. You have two options:

   **Option A: GitLab Web IDE (no local setup needed)**
   - Open the [README template](https://gitlab.com/codepath-org/ai-corps/spring-2026-gitlab-ai301/-/blob/main/students/CONTRIBUTION-README.md?ref_type=heads) and click **Raw** or copy the full contents
   - In your new project, click the **Web IDE** button (or click your `README.md` file → **Edit** → **Edit in Web IDE**)
   - Replace the default README content with the template you copied
   - Click **Commit to 'main'**

   **Option B: Local clone**
   ```bash
   git clone https://gitlab.com/<your-username>/ai-corps-contribution.git
   cd ai-corps-contribution
   ```
   - Download or copy the [README template](https://gitlab.com/codepath-org/ai-corps/spring-2026-gitlab-ai301/-/blob/main/students/CONTRIBUTION-README.md?ref_type=heads) contents into your `README.md`
   - Commit and push:
   ```bash
   git add README.md
   git commit -m "Add contribution README template"
   git push origin main
   ```

3. **Confirm it's working:** Navigate to your project page on GitLab. You should see the README template rendered with all the section headers for each phase. **Copy the URL to your project** — you'll include this link in your check-in forms so mentors and staff can find your README throughout the program.

4. Familiarize yourself with the template sections. You'll fill them in progressively as you move through each phase:
   - **Phase I:** Issue link + problem summary + why you chose it
   - **Phase II:** Environment setup notes + reproduction steps + solution plan
   - **Phase III:** Implementation progress + branch links + testing notes
   - **Phase IV:** MR link + summary + maintainer feedback log

> **Think of your README as a professional engineering journal.** It's not busywork — it's the document that lets mentors give you targeted feedback, lets the CodePath team know if you're stuck, and serves as a portfolio piece showing your contribution process. Strong READMEs lead to better mentor support. Weak READMEs make it harder for anyone to help you.

---

### Step 3: Browse the Issue Lists (30 minutes max)

Now it's time to find your issue. You have three starting points, ordered from most curated to least:

#### Source 1: GitLab's Public Starter List
Maintained by the GitLab Contributor Success team. These are issues explicitly tagged for new contributors with varying levels of complexity.

→ [GitLab Starter Issues](https://contributors.gitlab.com/issues)

#### Source 2: CodePath's Top Picks
A curated list of issues hand-selected by your CodePath team and GitLab mentors. These are tethered to projects directly maintained by GitLab staff involved in this program — meaning you'll have access to people who know the codebase when you need help.

→ [CodePath Curated Issues List](https://www.notion.so/beaed3f4289e42f38cf13bf16834a90e?v=30c06d25e7488005af57000c1eb4aaa2)

#### Source 3: GitLab's Full Issue Board
The complete, unfiltered issue tracker. Powerful but overwhelming without filters. Only use this if nothing on the first two lists matches your interests — and if you do, use the filtering walkthrough later in this guide.

→ [GitLab Project Issue Board](https://gitlab.com/gitlab-org/gitlab/-/issues)

> **Recommendation:** Start with Source 1 or 2. These have been pre-vetted for feasibility and active maintainer engagement. Skim titles and descriptions. **Don't read every issue deeply yet.** Star or bookmark 3–5 that catch your eye based on: the title sounds like something you could explain to a friend, it involves a technology or area you're curious about, and it seems specific (not a massive overhaul).

---

### Step 4: Read Your Top 3 Candidates Carefully (30 minutes)

For each of your 3 best options, open the full issue page and read:
- The original issue description
- All comments from maintainers or team members (look for the GitLab team badge)
- Any linked merge requests (are there failed attempts you can learn from?)
- The labels (look for things like "quick win", "quick win::first-time contributor" which are dedicated labels for new contributors) or the context feels achievable for you.

---

### Step 5: Run the Issue Selection Checklist (15 minutes)

For each of your 3 candidates, go through all 5 checks below. Write down your answers — even rough notes count. Discard any issue that scores below 3.

#### ✅ Check 1: I understand the problem.
Can you explain what is broken or missing in one sentence? Do you know what "fixed" looks like? If you can't articulate the problem in plain language, you don't understand the issue yet — and that's a sign to keep reading or keep looking.

#### ✅ Check 2: The scope fits 3–4 weeks of work.
The issue should be **specific and bounded**. Good examples: "Add validation to X form," "Fix incorrect tooltip rendering on Y page," "Update Z API endpoint to handle edge case." Bad examples: "Refactor authentication system," "Improve performance," "Redesign settings page." If the issue description is more than a few paragraphs of requirements, it is probably too large.

#### ✅ Check 3: It matches my skills (or things I can learn quickly with AI).
The issue involves languages, frameworks, or patterns that you already know — or that you could realistically learn with GitLab Duo and Claude Code in a few days. If the issue requires deep expertise in a system you've never touched and can't quickly ramp on, it's not the right fit for this cycle.

#### ✅ Check 4: The issue is active and claimable.
Look for these signals:
- Maintainer or team member activity in the last 6 months
- **Not** assigned
- **Not** labeled "proposal," "needs discussion," "blocked," "wontfix" or any other labels that signal a deadend
- No open merge request already solving it (check the MR tab on the issue)

#### ✅ Check 5: There is helpful context.
Are there comments from maintainers with analysis, hints, or related issues? Are there links to the relevant code files? The more context an issue has, the faster you'll move in Phase II.

#### Decision Rule

| Result | Action |
|--------|--------|
| All 5 checked | **Claim it.** Move to the next step. |
| 3–4 checked | **Ask for help.** Post in `#sp26-issue-selection` or bring it to office hours. |
| Fewer than 3 | **Skip it.** Keep looking. |

---

### Step 6: Pick One and Commit (5 minutes)

Choose the issue that scored highest on the checklist. If two are tied, pick the one with more maintainer context — it will make Phase II significantly easier.

---

### Step 7: Update Your README and Check-In Form (15 minutes)

Open the Contribution README in the project you created in Step 2 and fill in the Phase I section:
- The issue link
- Your 2–4 sentence problem summary (see the examples later in this guide)

Then submit your [check-in form](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) and mark "Phase I Complete."

---

### Step 8: Announce in Discord (2 minutes)

Post in **`#sp26-general`** on our [program Discord](https://discord.gg/YVVD9h9EJe):
> "🎯 Phase 1 Complete — Selected [issue title]: [one-line summary]. Link: [url]" or anything you want us to hype you up for!

This celebrates your milestone with the cohort and lets mentors and peers see what you're working on. Use `#sp26-general` for announcements and milestones. Use `#sp26-issue-selection` for technical questions, troubleshooting, or when you need help choosing.

---

### Step 9: Tag a Merge Request Coach (2 minutes)

This is your first interaction with GitLab's contribution system. Comment on your chosen issue page on GitLab:

```
@gitlab-bot help
```

This tags a **Merge Request Coach** — a GitLab team member who helps community contributors. They can:
- Confirm the issue is valid and currently accepting contributions
- Point you toward the right part of the codebase
- Flag any concerns about scope or approach before you invest time building in Phase II

**Don't skip this step.** Early coach engagement saves you from discovering in Week 3 that your issue was already resolved, is blocked on other work, or has hidden complexity. You do not need to be assigned to the issue to start working — GitLab's process explicitly allows this.

---

## Filtering the Full Issue Board (If You Need It)

If the curated lists don't have a match for you, here's how to navigate GitLab's full issue tracker to find first-time contributor friendly issues:

### Filter Step 1: Start with FTC-Friendly Labels

Go to [gitlab.com/gitlab-org/gitlab/-/issues](https://gitlab.com/gitlab-org/gitlab/-/issues) and filter by these labels (you can combine multiple):

**Primary FTC Labels:**
- `1st contribution` — explicitly marked for first-time contributors
- `Community contribution` — community-focused work
- `Community challenge` — community engagement opportunities

**Help Wanted Labels (by area):**
- `BE Help Needed` — Backend help needed
- `FE Help Needed` — Frontend help needed
- `Design Help Needed` — Design help needed
- `EM Help Needed` — Engineering Manager help needed
- `Accepting UX contributions` — UX work welcome

**Other FTC Indicators:**
- `First mile` — onboarding-related
- `Category:Onboarding` — onboarding category
- `AI-Seeking community feedback` — community input welcome
- `Community Interest` — community engagement

### Filter Step 2: Apply Additional Filters

After selecting FTC-friendly labels, narrow down further:

1. **Weight filter:** Look for issues with weight ≤ 3 (ideal) or ≤ 5 (acceptable). Issues without weight set can also be good quick fixes.
2. **Assignee filter:** Prefer **unassigned issues** — if someone is already assigned, they're likely working on it.
3. **Sort by:** "Recently created" or "Recently updated" — prioritize issues created within the last 30 days (ideally within 7 days).
4. **State:** Keep it set to "Open" (default).

### Filter Step 3: Evaluate Individual Issues

When you find a promising issue, check these criteria:

✅ **Green flags:**
- **Comment count ≤ 5** (ideally ≤ 3) — less discussion means less complexity
- **No assignees** — available for you to work on
- **No blocking issues** — won't be blocked by dependencies
- **No subtasks** — self-contained work
- **Clear acceptance criteria** — you know what "done" looks like
- **No existing open MR** — check the "Related merge requests" section

⚠️ **Red flags:**
- Comment count > 10 — likely complex or controversial
- Already assigned — someone is working on it
- Weight > 5 — may be too large in scope
- Has blocking issues — dependencies may delay your work
- Multiple subtasks — might be more complex than it appears

### Filter Step 4: Use AI to Validate

Before committing, paste the issue URL into GitLab Duo or Claude Code and ask:
- *"Is this issue appropriately scoped for a first-time contributor? What would the fix likely involve?"*
- *"Are there any hidden complexities I should be aware of?"*
- *"What files would likely need to be modified?"*

> **Do not** spend more than 1 hour browsing the full board. If you haven't found something in an hour, stop and ask for help (see Escalation below).

---

## Slippery Spots

These are the most common ways students get stuck in Phase I. If you recognize yourself in any of these, take the action listed.

### 🟡 "I'm stuck on the contributor onboarding."
**What's happening:** The onboarding process hit a snag — account permissions, community fork access, or a step you don't understand.
**Fix:** Post in `#sp26-issue-selection` on our [program Discord](https://discord.gg/YVVD9h9EJe) with a screenshot of where you're stuck. You can also email **contributors@gitlab.com** directly — GitLab's Contributor Success team responds to these. Don't let onboarding block your issue browsing — you can look at issues and run the checklist while onboarding is in progress. Just make sure onboarding is complete before you tag `@gitlab-bot help` in Step 9.

### 🟡 "I'm not sure how to set up my README."
**What's happening:** You're unsure about creating the GitLab project or copying the template.
**Fix:** The fastest path is the Web IDE option — no local tools required. Create a new project at [gitlab.com/projects/new](https://gitlab.com/projects/new#blank_project), open the [README template](https://gitlab.com/codepath-org/ai-corps/spring-2026-gitlab-ai301/-/blob/main/students/CONTRIBUTION-README.md?ref_type=heads), copy its contents, paste them into your project's README using the Web IDE, and commit. If you're still stuck, post in `#sp26-issue-selection` — this is a common first-day question and someone will help you quickly. You don't need to fill in the whole template right now — just get the project created and fill in the Phase I section.

### 🟡 "I've been browsing for hours and nothing feels right."
**What's happening:** Paradox of choice. 44,700 issues is paralyzing by design — that's why the curated lists exist.
**Fix:** Close the full issue board. Open the CodePath Curated Issues List. Pick the best option from that list within 20 minutes. Remember: you can swap issues later with no penalty as long as you have time to build your solution.

### 🟡 "I found one but I'm not sure it's good enough."
**What's happening:** Perfectionism. There is no perfect issue. A solid 4/5 on the checklist is a great starting point.
**Fix:** Run the checklist. If it scores 3 or higher, post it in `#sp26-issue-selection` and ask: *"Thinking about [issue link] — any red flags?"* A mentor or peer will give you a quick gut check.

### 🟡 "The issue I want is in Ruby and I only know Python."
**What's happening:** Language mismatch anxiety. This is normal — and it's literally what this program teaches you to handle.
**Fix:** If the issue scores well on the other 4 checklist items, the language gap is manageable. You have GitLab Duo and Claude Code specifically to bridge language differences. Ruby is readable to Python developers, and AI tools can translate patterns effectively. Pick the issue and address the language gap in Phase II.

### 🟡 "Someone else in the cohort picked the same issue."
**What's happening:** Overlap concern. Multiple students can select the same issue — you are not competing.
**Fix:** Keep your selection. You will each develop your own independent solution. If you want to avoid overlap for personal preference, check the cohort issue ledger before committing.

### 🟡 "I picked an issue but now I realize it's too big."
**What's happening:** Scope misjudgment. This happens to everyone, including experienced engineers.
**Fix:** Go back to Step 3. Pick a new issue. **There is zero penalty for swapping during Phase I.** Better to spend 1–2 days finding the right issue than 2–3 weeks stuck on the wrong one.

---

## You're on the Right Track If...

- ✅ Your GitLab contributor onboarding is complete and you can access the community fork
- ✅ Your Contribution README is created and has the Phase I section filled in
- ✅ You can explain the problem in one sentence to someone who hasn't read the issue
- ✅ You can point to specific files or modules in the GitLab codebase that are likely involved (even if you're guessing — that shows you read the context)
- ✅ Your checklist scores 4 or 5 out of 5
- ✅ You chose within the first 3 days of the program
- ✅ Your README problem summary goes beyond "I picked this because it looked interesting" — it explains *why this issue, why you, and what "fixed" means*
- ✅ You tagged `@gitlab-bot help` and got early confirmation from a coach

---

## Strong vs. Weak README Examples

### ✅ Strong Example

```markdown
## Why I Chose This Issue

I chose issue #12345 "Add email validation to user profile form" because 
it aligns with my JavaScript experience and my goal to improve my frontend 
validation skills. The issue is labeled "good for new contributors" and has 
clear acceptance criteria in the comments.

I'm interested in this because:
1. I've built form validation before in personal projects, so I understand 
   the basics
2. The codebase area (user profiles) seems contained and not too complex 
   for a first contribution
3. The maintainer comments indicate they're actively reviewing MRs in this area
4. I want to learn how GitLab handles client-side vs server-side validation 
   patterns

From reading the issue thread, I understand the current problem is that 
invalid emails can be submitted without any user feedback. My contribution 
will improve the user experience and data quality.

Tagged @gitlab-bot help on the issue — coach confirmed it's valid and 
pointed me to the user model area for Phase II investigation.
```

**Why this works:** The student shows they understand the problem, explains their skill match, identifies that the area is actively maintained, connects the work to a personal learning goal, and has already engaged with GitLab's review system.

### ❌ Weak Example

```markdown
## Why I Chose This Issue

I picked this issue because it looked interesting and not too hard. 
It's about form validation.
```

**Why this fails:** No reasoning about skill match, learning goals, or understanding of the issue. A mentor can't assess whether this is appropriate for the student, and the student hasn't demonstrated they actually read the issue thread.

---

## When and How to Escalate

Phase I should take **1–3 days**. If you're approaching Day 4 without a selection, it's time to ask for help. Here is the escalation ladder:

### Level 1: Peer Help (anytime)
Post in **`#sp26-issue-selection`** on Discord. Share what you've looked at, what's tripping you up, and ask for suggestions. Your peers and program staff are monitoring this channel.

*Example message:*
> "I've been looking at issues related to [area]. I found [issue link A] and [issue link B] but I'm not sure about scope. Anyone have thoughts or suggestions for something similar?"

### Level 2: Mentor / Office Hours (Tue & Thu)
Bring your top 2–3 candidates to office hours. Mentors can give you a quick feasibility read and point you toward better options if needed.
- **Tuesday 10–11am ET**
- **Thursday 5–6pm ET**
- Submit your question for the next [Office Hours](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) even if you can't attend live — it will still get answered.

### Level 3: Direct Staff Support (Day 4+)
If you still don't have an issue by Day 4, the CodePath team will reach out to you directly with 3 curated issue recommendations. You don't need to wait for this — you can DM **Cam Flowers** in Discord or Slack at any point to request a [1:1 consultation](https://calendar.app.google/RVukCQpVgxLFNF7Y7).

> **Important:** If you hit Day 7 without a selected issue, Cam and the CodePath team will assign one to you directly so you can keep moving. This is not a punishment — it's a safety net to ensure you don't lose build time. But you'll have a much better experience if you choose your own issue by Day 3.

## Phase I Deliverables Summary

| Deliverable | Where |
|---|---|
| GitLab contributor onboarding complete | [contributors.gitlab.com](https://contributors.gitlab.com) |
| Contribution README project created with template | Your personal GitLab project (public) |
| Issue link + problem summary in README | Your Contribution README |
| `@gitlab-bot help` comment on your issue | The issue page on GitLab |
| Phase I marked complete | [Check-In Form](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) |
| Milestone announced | `#sp26-general` on Discord |

---

## Resources

| Resource | Link |
|---|---|
| GitLab Contributor Onboarding | [contributors.gitlab.com](https://contributors.gitlab.com) |
| README Template (source) | [Contribution README Template](https://gitlab.com/codepath-org/ai-corps/spring-2026-gitlab-ai301/-/blob/main/students/CONTRIBUTION-README.md?ref_type=heads) |
| Create a New GitLab Project | [gitlab.com/projects/new](https://gitlab.com/projects/new#blank_project) |
| CodePath Curated Issues List | [Notion](https://www.notion.so/beaed3f4289e42f38cf13bf16834a90e?v=30c06d25e7488005af57000c1eb4aaa2) |
| GitLab Starter Issues | [contributors.gitlab.com/issues](https://contributors.gitlab.com/issues) |
| GitLab Full Issue Board | [gitlab.com/gitlab-org/gitlab/-/issues](https://gitlab.com/gitlab-org/gitlab/-/issues) |
| GitLab Community Discord | [discord.gg/gitlab](https://discord.gg/gitlab) |
| Check-In Form | [Typeform](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) |
| Office Hours | [Sign-Up Form](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) |
| Program Discord | [discord.gg/YVVD9h9EJe](https://discord.gg/YVVD9h9EJe) |
| Cam 1:1 Booking | [Calendly](https://calendar.app.google/RVukCQpVgxLFNF7Y7) |
| Contributor Success Email | contributors@gitlab.com |

---

## What Happens Next

Once you're onboarded, your README is created and updated, your check-in is submitted, you've tagged `@gitlab-bot help`, and your milestone is announced — **you're done with Phase I.** Move directly to **Phase II: Reproduce & Plan**, where you'll set up your local development environment, reproduce the issue, and draft your solution approach.

If you finish Phase I on Day 1 or 2, don't wait — start Phase II immediately. Momentum is your friend in this program.

---

*Phase I Written Guide — AI Corps x GitLab, Spring 2026. See the Student Handbook for full program context and the Mentor Handbook for information on how your mentors will support you.*