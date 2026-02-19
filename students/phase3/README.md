# Phase III: Build

**AI Corps x GitLab — Open Source Contribution Learning Path, Spring 2026**

---

## What This Phase Is About

Phase III is where you write code. You have an issue, you've reproduced it, and you have a plan. Now you execute that plan — implementing your solution, writing tests, and pushing working commits to your fork.

This is the longest phase of the program (~2 weeks) and the one where momentum matters most. The biggest risk isn't writing bad code — it's writing no code. Students who push regularly, test incrementally, and ask for feedback early almost always reach Phase IV. Students who go silent for a week often don't.

**Target duration: ~2 weeks.**

---

## What "Done" Looks Like

To complete Phase III, you need to do two things:

**1. Update your Contribution README with:**

- A brief summary of the implementation work completed
- Links to your active development branch, meaningful commits, or a draft MR (optional but strongly encouraged)
- Notes on testing approaches or validation steps taken

**2. Submit your check-in form and indicate "Phase III Complete."**

Phase III is complete when you have a working solution that you're ready to submit as a merge request. It does not need to be perfect — Phase IV is where you polish and iterate.

---

## Step-by-Step Procedure

### Step 1: Review GitLab's Contribution Guidelines (30 minutes)

Before writing any code, read the relevant sections of the [GitLab Contribution Guide](https://docs.gitlab.com/ee/development/contributing/). This tells you what reviewers will expect. Focus on:

- **Code style:** GitLab enforces style guides for Ruby, JavaScript, CSS, and other languages. Find the one relevant to your change.
- **Testing requirements:** Every code change needs tests. Understand what kind of tests GitLab expects (unit, integration, feature).
- **Commit message format:** GitLab has conventions for commit messages. Follow them from your first commit — it's much harder to rewrite history later.
- **MR description template:** Familiarize yourself with what a merge request description needs. You'll write this in Phase IV, but knowing the format now helps you track the right information as you build.

> **Shortcut:** Paste the contribution guide URL into Claude Code and ask: *"What are the key rules I need to follow for a [Ruby/JavaScript/etc.] contribution to GitLab?"*

---

### Step 2: Implement Your Plan in Small, Testable Increments (1–2 weeks)

This is the core of Phase III. Work through your solution plan step by step.

#### The Daily Rhythm

1. **Start each session** by pulling the latest from upstream to avoid merge conflicts:
   ```bash
   git fetch origin
   git rebase origin/master
   ```
2. **Work on one small piece** of your plan at a time. If your plan says "modify validation method, add tests, update docs" — do the validation method first, commit it, then move to tests.
3. **Commit frequently.** Every meaningful change gets its own commit. Aim for at least one commit per working day.
   ```bash
   git add -A
   git commit -m "Fix email validation typo in user.rb"
   git push origin fix-issue-XXXXX
   ```
4. **Run tests after every change.** Don't wait until the end to discover your changes broke something.
5. **Document as you go.** Update your README with what you built, challenges you faced, and decisions you made. This is your weekly progress log.

#### Using AI Effectively During Build

AI tools are your pair programming partner in this phase. Use them for:

- **Understanding unfamiliar code:** *"What does this method do? What calls it?"*
- **Language translation:** *"I know how to do this in Python — how do I do it in Ruby?"*
- **Writing test scaffolding:** *"Generate RSpec tests for a method that validates email format"*
- **Debugging failures:** *"My test is failing with this error. What's wrong?"*
- **Style compliance:** *"Does this code follow GitLab's Ruby style guide?"*

**Critical rule:** Always review and understand AI-generated code before committing it. You are responsible for every line in your merge request. If a reviewer asks "why did you do X?" — "the AI suggested it" is not an acceptable answer.

---

### Step 3: Write Tests (throughout, not at the end)

Tests are non-negotiable for GitLab contributions. Write them alongside your code, not after.

#### What to Test

- **The fix itself:** Does the bug no longer occur? Write a test that would have caught the bug before your fix.
- **Edge cases:** What happens with empty input? Extremely long input? Unexpected types?
- **Regressions:** Do all existing tests still pass? Run the full test suite (or the relevant subset) regularly.

#### Finding Test Examples

The best way to learn how to write tests for GitLab is to look at existing tests in the same area:
- Find the spec file that corresponds to the file you modified (e.g., `app/models/user.rb` → `spec/models/user_spec.rb`)
- Read 2–3 existing tests to understand the patterns, helpers, and factories used
- Model your new tests on those patterns

> **AI tip:** Paste an existing test file into Claude Code and ask: *"How do I add a test case here that checks [your scenario]?"*

---

### Step 4: Participate in Scrums (Tuesdays & Thursdays)

During Phase III, you'll be prompted to participate in a **twice-weekly Discord scrum** (Tuesdays and Thursdays). A bot or facilitator will post a prompt — reply with:

1. **What I did since last scrum**
2. **What I'm working on next**
3. **Am I blocked? If so, on what?**

This takes 2 minutes and serves two purposes: it keeps you accountable, and it surfaces blockers early so the team can help. Non-participation is tracked and may trigger a check-in from staff.

---

### Step 5: Self-Review Before Moving On (1 hour)

Before marking Phase III complete, run this pre-submission checklist:

- [ ] **Code change works.** The bug is fixed or the feature works as intended in your local environment.
- [ ] **Tests pass.** All new tests pass. All existing tests still pass (or you can explain why a failure is unrelated).
- [ ] **Style compliance.** Your code follows the project's style guide. Run any available linters.
- [ ] **No unnecessary changes.** Your diff should only include changes relevant to the issue. Remove debug statements, commented-out code, and unrelated formatting changes.
- [ ] **Commit history is clean.** Each commit has a descriptive message. Squash or reword if needed.
- [ ] **README is updated.** Implementation summary, branch link, testing notes.

---

### Step 6: Update README and Check-In (15 minutes)

Add or update the following in your Contribution README:

- **Implementation Progress:** What you built, files modified, key commits
- **Challenges Faced:** What was hard, how you solved it, what tools helped
- **Testing:** What tests you added, what validation you performed
- **Branch Link:** Direct link to your working branch on your fork

Then submit your [check-in form](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) and indicate "Phase III Complete."

---

## Slippery Spots

### 🟡 "I haven't committed anything in 3+ days."
**What's happening:** You're either stuck, distracted, or trying to get everything perfect before committing.
**Fix:** Commit what you have right now — even if it's incomplete. A work-in-progress commit is infinitely more useful than nothing. If you're stuck on a specific problem, post it in `#sp26-build-support` with the error message and what you've tried. The team tracks commit gaps and will reach out if they see 48+ hours of silence.

### 🟡 "My code works but I haven't written any tests."
**What's happening:** Test avoidance. Understandable — writing tests in an unfamiliar framework is hard. But GitLab will not accept a contribution without tests.
**Fix:** Find the existing test file for the code you modified. Read 2-3 tests there. Model yours on those patterns. Use AI to generate a starting scaffold, then customize it. Even one meaningful test is better than zero.

### 🟡 "I'm making changes but I keep breaking other things."
**What's happening:** Cascading side effects, often from modifying shared code.
**Fix:** Run the test suite after every small change. If a change breaks something unrelated, investigate whether your modification has wider impact than expected. Check `git diff` to ensure your changes are scoped to the issue. Ask in office hours if you're unsure whether your approach is too invasive.

### 🟡 "My plan from Phase II doesn't work — the fix is more complicated than I thought."
**What's happening:** Plans meet reality. This is normal in engineering.
**Fix:** Revise your plan in your README. If the scope has grown significantly, consider descoping — can you solve a smaller piece of the issue and note the rest as follow-up? Post your revised understanding in `#sp26-build-support` and ask for mentor input. If the issue has genuinely ballooned beyond 4 weeks of work, it may be worth returning to Phase I for a new issue.

### 🟡 "I've been in Phase III for 2+ weeks with minimal progress."
**What's happening:** You may be blocked, over-scoped, or need more targeted support.
**Fix:** This is exactly when to book a [1:1 session with Cam](https://calendar.app.google/RVukCQpVgxLFNF7Y7). He can help you decide whether to descope, swap issues, or pair-program through the blocker. Don't wait — build time is the scarcest resource in the program.

---

## You're on the Right Track If...

- ✅ You're committing code at least every other day
- ✅ You can describe what your code changes do and why, without referencing AI output
- ✅ You have at least one new test that validates your fix
- ✅ Your existing test suite still passes
- ✅ You're participating in scrums and documenting progress in your README
- ✅ You've asked for at least one round of feedback (from a peer, mentor, or in Discord)

---

## Strong vs. Weak README Examples

### ✅ Strong Example

```markdown
## Implementation Notes

### Week 3 Progress (Feb 17–23)
**What I built:**
- Fixed the typo in `user.rb` line 45 (`validate_emai` → `validate_email`)
- Added 3 unit tests in `spec/models/user_spec.rb`:
  - Test 1: Rejects email without @ symbol
  - Test 2: Rejects email without domain
  - Test 3: Accepts valid email formats
- All existing tests still pass (ran full test suite)

**Challenges faced:**
- Initially tests were failing because I didn't understand RSpec syntax 
  for validations
- Spent 2 hours debugging before realizing I needed to use `build` 
  instead of `create` for invalid models
- Found helpful example in `spec/models/project_spec.rb` line 89

**Commits this week:**
- abc123: Fix email validation callback typo
- def456: Add unit tests for email validation
- ghi789: Update user model documentation
```

**Why this works:** Specific files and lines, named commits, challenges documented with resolution details, test strategy explained. A mentor reading this knows exactly where the student is and what help they might need.

### ❌ Weak Example

```markdown
## Implementation Notes

Making progress on the fix. Working on tests. Should be done soon.
```

**Why this fails:** No specifics. No commits. No challenges. No evidence of actual work. "Making progress" for 2 weeks with no detail is an intervention trigger.

---

## When and How to Escalate

### Level 1: Peer + AI Help (anytime)
Post in **`#sp26-build-support`** on [Discord](https://discord.gg/YVVD9h9EJe). Include your error message, the relevant code snippet, and what you've already tried (including AI suggestions). Peers who solved similar issues are often the fastest help. For GitLab-specific coding questions, the **`#contribute`** channel on the [GitLab Community Discord](https://discord.gg/gitlab) is also available.

### Level 2: Mentor / Office Hours (Tue & Thu)
Bring your code, your error, and your branch link. Mentors can review your approach, spot issues, and suggest debugging strategies.
- **Tuesday 10–11am ET**
- **Thursday 5–6pm ET**
- Submit your question for the next [Office Hours](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) even if you can't attend live.

### Level 3: Direct Staff Support (48h commit gap or 7+ days with minimal progress)
If you haven't committed in 48 hours, the system will flag you for outreach. If you've been in Phase III for 7+ days with minimal progress, Cam will reach out for a scope assessment. You can always proactively book a [1:1 session](https://calendar.app.google/RVukCQpVgxLFNF7Y7) to discuss descoping, swapping, or pair programming.

---

## Phase III Deliverables Summary

| Deliverable | Where |
|---|---|
| Implementation summary + branch link + testing notes | Your Contribution README on GitLab |
| Phase III marked complete | [Check-In Form](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) |
| Scrum participation (twice weekly) | `#sp26-build-support` on Discord |
| Milestone announced | `#sp26-general` on Discord (recommended) |

---

## Resources

| Resource | Link |
|---|---|
| GitLab Contribution Guide | [docs.gitlab.com/.../contributing](https://docs.gitlab.com/ee/development/contributing/) |
| GitLab Testing Guide | [Testing Levels](https://docs.gitlab.com/ee/development/testing_guide/) |
| GitLab Commit Message Guidelines | [Commit Messages](https://docs.gitlab.com/ee/development/contributing/merge_request_workflow.html#commit-messages-guidelines) |
| GitLab Community Discord | [discord.gg/gitlab](https://discord.gg/gitlab) |
| Check-In Form | [Typeform](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) |
| Office Hours | [Sign-Up Form](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) |
| Program Discord | [discord.gg/YVVD9h9EJe](https://discord.gg/YVVD9h9EJe) |
| Cam 1:1 Booking | [Calendly](https://calendar.app.google/RVukCQpVgxLFNF7Y7) |
| CodePath GitLab Project | [Contribution README](https://gitlab.com/codepath-org/ai-corps/spring-2026-gitlab-ai301/-/blob/main/students/CONTRIBUTION-README.md?ref_type=heads) |

---

## What Happens Next

Once your solution is implemented, tests are passing, and your README is updated — **you're done with Phase III.** Move directly to **Phase IV: Submit & Iterate**, where you'll open a merge request, write a clear description, and engage with maintainer feedback.

If your code works and your tests pass, don't wait to polish. Submit your MR and iterate based on real feedback — that's how open source works.

---

*Phase III Written Guide — AI Corps x GitLab, Spring 2026.*