# Phase IV: Submit & Iterate

**AI Corps x GitLab — Open Source Contribution Learning Path, Spring 2026**

---

## What This Phase Is About

Phase IV is the finish line — and the starting line of your life as an open source contributor. You will take your working solution from Phase III, open a formal merge request on GitLab, write a professional description, and engage with feedback from maintainers and reviewers.

This is the core completion milestone of the program. Submitting a review-ready merge request — regardless of whether it gets accepted — means you have completed the AI Corps contribution cycle.

A few things to internalize before you begin:

- **Submission is not the same as acceptance.** Your MR does not need to be merged to count. The goal is a professional, review-ready submission.
- **Feedback is not failure.** Maintainers requesting changes is the normal open source workflow. A request for revision means they took the time to engage with your work.
- **Iteration is expected.** Most merge requests go through multiple rounds of review. The faster you respond to feedback, the more likely your MR will move forward.

**Target duration: 3–5 days.**

---

## What "Done" Looks Like

To complete Phase IV, you need to do two things:

**1. Update your Contribution README with:**

- A link to your submitted merge request
- A brief summary of what you contributed
- Notes on feedback received or next steps (if still in review)

**2. Submit your check-in form and indicate "Phase IV Complete."**

That's it. Once your MR is open and your README is updated, you have completed the program's core milestone. Congratulations.

---

## Step-by-Step Procedure

### Step 1: Final Pre-Submission Checks (30 minutes)

Before opening your MR, run through this checklist one last time:

- [ ] **Your fix works.** Reproduce the original issue — it should no longer occur.
- [ ] **All tests pass.** Run the full test suite (or the relevant subset). No new failures.
- [ ] **No unrelated changes.** Run `git diff origin/master` and review every changed line. Remove debug code, stray comments, and formatting-only changes.
- [ ] **Commit messages are clean.** Each commit should have a clear, descriptive message. Squash fixup commits if needed:
  ```bash
  git rebase -i origin/master
  ```
- [ ] **Branch is up to date.** Rebase on the latest upstream to minimize merge conflicts:
  ```bash
  git fetch origin
  git rebase origin/master
  git push origin fix-issue-XXXXX --force-with-lease
  ```

---

### Step 2: Open Your Merge Request (30 minutes)

1. Navigate to the community fork on GitLab (e.g., `gitlab.com/gitlab-community/gitlab`)
2. Find your branch and click **"Create merge request"** (GitLab often prompts this after a recent push)
3. Set the **target branch** to `master` on the **canonical** repository (e.g., `gitlab-org/gitlab:master`)
4. Fill in the MR description using the template below

> **Important:** Your MR should go from your branch in the community fork to `master` on the upstream canonical repository. This is the standard GitLab community contribution workflow. See the [merge request tutorial](https://docs.gitlab.com/ee/development/contributing/merge_request_workflow.html) for complete step-by-step instructions.

#### MR Description Template

GitLab has a built-in MR template that appears when you create a merge request. If it doesn't auto-populate, use this structure:

```markdown
## What does this MR do?

[One paragraph: What is the change and what does it accomplish?]

## Why was this MR needed?

[Reference the issue. Explain the problem and what investigation revealed.]

## What are the relevant issue numbers?

Closes #[ISSUE_NUMBER]

## Screenshots / Recordings (if applicable)

[Before/after screenshots for UI changes. Console output for backend changes. 
Delete this section if not applicable.]

## Does this MR meet the acceptance criteria?

- [ ] Tests added for new/changed behavior
- [ ] All tests passing
- [ ] Follows project style guide
- [ ] No breaking changes introduced
- [ ] Documentation updated (if applicable)
```

#### Writing a Strong MR Description

Your MR description is the first thing a reviewer reads. It determines whether they engage with your code or skip to the next MR. Make it count.

**Do:**
- Explain the *why* before the *what.* Reviewers need context.
- Reference the issue number with `Closes #XXXXX` — this auto-links and auto-closes the issue on merge.
- Be specific about what you changed and why that approach was chosen.
- Include before/after evidence (screenshots, test output, console logs).

**Don't:**
- Write "Fixed the bug." That tells a reviewer nothing.
- Leave the description empty or use only the title.
- Include implementation details that are obvious from the diff — the description should provide context the code can't.

---

### Step 3: Request a Review (5 minutes)

After opening your MR, you need to get it in front of a reviewer. GitLab's process works like this:

1. **Follow the link posted by `@gitlab-bot`** on your MR to add labels and request a review from the GitLab team. The bot automatically posts this link after MR creation.
2. **If that doesn't happen**, add a comment on your MR:
   ```
   @gitlab-bot help
   ```
   This tags a **Merge Request Coach** who will assign relevant reviewers or guide you through the review themselves.
3. **If your code spans multiple areas** (e.g., frontend + backend), you can mention multiple coaches who specialize in each discipline.

> **Don't skip this step.** Without requesting a review, your MR may sit unreviewed. When your MR is triaged, a coach will assign relevant reviewers. The goal is to have your MR reviewed within a week after a reviewer is assigned.

---

### Step 4: Respond to Feedback Professionally (ongoing)

Once your MR is open, reviewers may:

- **Approve it** — congratulations, your MR will be merged.
- **Request changes** — the most common outcome. They'll leave comments on specific lines or the overall approach.
- **Ask questions** — they need clarification about your approach or reasoning.
- **Suggest alternatives** — they may recommend a different approach entirely.

#### How to Respond

**When they request a code change:**
1. Read the comment carefully. Make sure you understand what they're asking.
2. The reviewer will set the `~"workflow::in dev"` label, signaling the MR is back in your hands.
3. Make the change in your branch and push a new commit.
4. Reply to the comment confirming the change: *"Updated in [commit hash]. Switched to the factory approach as suggested."*
5. When all requested changes are complete, comment **`@gitlab-bot ready`** to signal the MR is ready for review again.
6. If you disagree with the suggestion, say so respectfully and explain your reasoning. Open source is a conversation.

> **Expect multiple rounds.** GitLab merge requests are typically reviewed by two domain experts — a reviewer and then a maintainer. This process may repeat several times before merge. This is normal and means your contribution is being taken seriously.

**When they ask a question:**
Reply directly, clearly, and promptly. Provide links to the relevant code or issue comments if it helps. Reviewers who ask questions are engaged — that's good.

**When they suggest a different approach:**
Consider it seriously. Maintainers know the codebase deeply. If the alternative approach is reasonable, implement it. If you believe your approach is better, explain why with technical reasoning.

**When you don't hear back:**
GitLab maintainers are busy. The goal is to have a merge request reviewed within a week after a reviewer is assigned, but this may take longer due to workload or holidays. If you haven't received a review within 5–7 business days, it's appropriate to leave a polite follow-up comment: *"Friendly ping — is there anything I can update to move this forward?"* For details about timelines and how to request help or escalate, see the [Wider Community Merge Request guide](https://docs.gitlab.com/ee/development/contributing/merge_request_workflow.html).

#### Tone Guidelines

You are representing yourself, CodePath, and this cohort in a public forum. Maintainers interact with thousands of contributors. Stand out by being:
- **Professional:** Clear, concise, no slang or emoji in MR discussions.
- **Responsive:** Reply within 24 hours when possible. Speed signals seriousness.
- **Grateful:** Thank reviewers for their time and feedback, even when they're critical.
- **Specific:** "I made the change you suggested" is better than "Done."

---

### Step 5: Update README and Check-In (15 minutes)

Add or update the following in your Contribution README:

- **MR Link:** Direct link to your submitted merge request
- **Summary:** What you contributed (1–2 sentences)
- **Status:** Awaiting review / Iterating / Approved / Merged
- **Maintainer Feedback:** Summary of feedback received and how you addressed it

Then submit your [check-in form](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) and indicate "Phase IV Complete."

Finally, celebrate your milestone in **`#sp26-general`** on Discord:
> "🚀 Phase IV Complete — MR submitted! [link to your merge request]"

This is the core completion milestone of the program. You earned it.

---

## Slippery Spots

### 🟡 "I keep polishing instead of submitting."
**What's happening:** Perfectionism. You want the code to be flawless before anyone sees it.
**Fix:** Submit now. Open source works by iterating in public. A "good enough" MR that gets feedback is worth infinitely more than a "perfect" MR that never gets opened. Maintainers expect to request changes — that's the process.

### 🟡 "My MR description is basically empty."
**What's happening:** You're treating the MR like a code dump instead of a professional communication.
**Fix:** Go back to Step 2 and use the template. Your description should be 2–3 paragraphs minimum. If you struggle to explain what your MR does, that may indicate you need to revisit your understanding of the issue.

### 🟡 "A reviewer requested changes and I feel discouraged."
**What's happening:** You're interpreting review feedback as rejection. It's not.
**Fix:** Review feedback means someone engaged with your contribution. That's a positive signal. Read the feedback carefully, make the requested changes, push a new commit, and reply. Most MRs go through 2–3 rounds of review before merging. This is normal.

### 🟡 "I submitted my MR a week ago and nobody has reviewed it."
**What's happening:** Maintainers have large queues. Community contributions sometimes take longer to review.
**Fix:** First, confirm you tagged `@gitlab-bot help`. If you did, wait 5–7 business days before following up. Then leave a polite comment. You can also mention it in `#sp26-mr-submission` — a GitLab mentor from the program may be able to give the MR a nudge.

### 🟡 "The reviewer wants me to completely redo my approach."
**What's happening:** Your implementation path may not align with the project's architecture or conventions.
**Fix:** This is a learning moment, not a failure. Ask the reviewer for more context: *"Can you point me to an example of the pattern you'd recommend?"* Use AI tools to understand the suggested approach. If the rework is genuinely beyond your remaining time, document what you learned in your README and note it as a follow-up.

---

## You're on the Right Track If...

- ✅ Your MR has a clear, multi-paragraph description that explains the what, why, and how
- ✅ You tagged `@gitlab-bot help` to request a reviewer
- ✅ Your acceptance criteria checklist is filled in
- ✅ You're responding to reviewer comments within 24 hours
- ✅ You're pushing follow-up commits when changes are requested
- ✅ Your README documents the feedback loop, not just the submission

---

## Strong vs. Weak README Examples

### ✅ Strong Example

```markdown
## Merge Request

**MR Link:** https://gitlab.com/gitlab-org/gitlab/-/merge_requests/54321

**MR Description:**
What does this MR do?: Fixes email validation in user profile form by 
correcting a typo in the validation callback.

Why was this MR needed?: Issue #12345 reported that the user profile form 
accepts invalid email addresses. Investigation revealed a typo in user.rb 
line 45: the callback was calling validate_emai instead of validate_email, 
causing the validation method to never execute.

What are the relevant issue numbers?: Closes #12345

Does this MR meet the acceptance criteria?:
[x] Tests added for new behavior
[x] All tests passing
[x] Follows Ruby style guide
[x] No breaking changes

**Maintainer Feedback:**
- Feb 28: Reviewer requested I use `let!` instead of `let` in tests for 
  consistency with the rest of the spec file. Updated in commit ghi789.
- Mar 2: Approved. Awaiting merge.

## Learnings & Reflections
Biggest lesson: Reading existing tests in the same spec file was more 
valuable than any documentation. The patterns are already there — you 
just have to look.
```

**Why this works:** Clear MR description, issue referenced, checklist complete, feedback documented with specific changes, reflections that demonstrate learning.

### ❌ Weak Example

```markdown
## Merge Request

Submitted my MR. Waiting for review.
```

**Why this fails:** No MR link, no description, no evidence of the submission, no feedback documentation. A mentor can't evaluate progress or help.

---

## When and How to Escalate

### Level 1: Peer Help (anytime)
Post in **`#sp26-mr-submission`** on [Discord](https://discord.gg/YVVD9h9EJe). Share your MR link and ask for peer review before or after submission. A second pair of eyes often catches things you missed.

### Level 2: Mentor / Office Hours (Tue & Thu)
Mentors can help you polish your MR description, interpret reviewer feedback, and coach you on maintainer communication.
- **Tuesday 10–11am ET**
- **Thursday 5–6pm ET**
- Submit your question for the next [Office Hours](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) even if you can't attend live.

### Level 3: Direct Staff Support
If you're past Week 5 and haven't submitted an MR, the CodePath team will reach out to help you get to submission. If you're struggling with reviewer feedback, Cam can coach you through responses. Book a [1:1 session](https://calendar.app.google/RVukCQpVgxLFNF7Y7) anytime.

---

## Phase IV Deliverables Summary

| Deliverable | Where |
|---|---|
| MR link + summary + feedback notes | Your Contribution README on GitLab |
| Phase IV marked complete | [Check-In Form](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) |
| MR submitted to GitLab | The upstream GitLab project |
| Milestone announced | `#sp26-general` on Discord |

---

## Resources

| Resource | Link |
|---|---|
| GitLab Contribution Guide | [docs.gitlab.com/.../contributing](https://docs.gitlab.com/ee/development/contributing/) |
| GitLab MR Guidelines | [MR Workflow](https://docs.gitlab.com/ee/development/contributing/merge_request_workflow.html) |
| Wider Community MR Guide | [Community MR Guide](https://docs.gitlab.com/ee/development/contributing/merge_request_workflow.html#wider-community-merge-request-guide) |
| GitLab Community Discord | [discord.gg/gitlab](https://discord.gg/gitlab) |
| Check-In Form | [Typeform](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) |
| Office Hours | [Sign-Up Form](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) |
| Program Discord | [discord.gg/YVVD9h9EJe](https://discord.gg/YVVD9h9EJe) |
| Cam 1:1 Booking | [Calendly](https://calendar.app.google/RVukCQpVgxLFNF7Y7) |
| CodePath GitLab Project | [Contribution README](https://gitlab.com/codepath-org/ai-corps/spring-2026-gitlab-ai301/-/blob/main/students/CONTRIBUTION-README.md?ref_type=heads) |
| Contributor Success Email | contributors@gitlab.com |

---

## What Happens Next

**You did it.** Once your MR is open, your README is updated, and your check-in is submitted — you have completed the core milestone of the AI Corps program.

### If Time Remains: Start Cycle 2

If you completed Phase IV before the program end date, you can start the entire cycle over:

1. Return to **Phase I** and select a new issue
2. Progress through Phases II–IV with a second contribution
3. Each additional MR strengthens your portfolio and deepens your open source experience

### If Your MR Is Still in Review

Keep iterating. Respond to feedback, push follow-up commits, and keep your README updated. An MR that's actively being reviewed at program close still counts as a completion.

### Either Way

Document your learnings in the **Learnings & Reflections** section of your README. What technical skills did you gain? What was the hardest part? What would you do differently next time? This is valuable for you, for future cohorts, and for your own professional portfolio.

---

*Phase IV Written Guide — AI Corps x GitLab, Spring 2026.*