# Phase II: Reproduce & Plan

**AI Corps x GitLab — Open Source Contribution Learning Path, Spring 2026**

---

## What This Phase Is About

Phase II is where you prove — to yourself and to your mentors — that you actually understand the issue you selected. You do this by reproducing it locally on your own machine and writing a concrete plan for how you intend to fix it.

This is the most technically demanding setup phase of the program. You will set up a local development environment, trigger the bug or behavior described in your issue, and then write a plan that shows you understand the root cause and have a realistic path to solving it.

If Phase I was about choosing wisely, Phase II is about proving you can work with what you chose.

**Target duration: 3–7 days.**

> **Prerequisites:** Before starting Phase II, you should have completed Phase I (issue selected, `@gitlab-bot help` tagged on the issue, README updated) and GitLab contributor onboarding (community fork access confirmed). If either is incomplete, go back and finish them first.

---

## What "Done" Looks Like

To complete Phase II, you need to do three things:

**1. Update your Contribution README with:**

- Clear, numbered reproduction steps (someone else should be able to follow them)
- A direct link to your branch in the community fork
- A short solution plan — bullet list or paragraph describing your intended approach

**2. Submit your check-in form and indicate "Phase II Complete."**

**3. (Recommended) Announce your Phase II completion in `#sp26-general` with a brief summary of your reproduction and plan.**

No merge request. No finished code. Just proof that you can reproduce the problem and a plan that makes sense.

---

## Step-by-Step Procedure

### Step 1: Set Up Your Local Development Environment (1–4 hours)

This is the step where most students hit friction. Budget time for it and don't panic — environment setup challenges are universal, even for experienced engineers.

GitLab offers two paths. **Start with GDK-in-a-box** unless you have a specific reason to install GDK from scratch.

#### Option A: GDK-in-a-box (Recommended for Most Students)

GDK-in-a-box packages the entire GitLab Development Kit into a **pre-configured container image** that you connect to with VS Code. This skips most of the manual installation and dependency headaches.

→ [Configure GDK-in-a-box](https://gitlab.com/gitlab-org/gitlab-development-kit/-/blob/main/doc/howto/gdk_in_a_box.md)

**Why start here:**
- Avoids most Ruby/Node/PostgreSQL version conflicts
- Works consistently across macOS, Windows, and Linux
- Faster path to a running local GitLab instance
- You can always switch to a full GDK install later if needed

#### Option B: Full GDK Installation

If you prefer a native installation or need more control over the environment:

→ [Install the GDK Development Environment](https://gitlab.com/gitlab-org/gitlab-development-kit/-/blob/main/doc/index.md)

1. Follow the GDK installation instructions for your OS
2. Run `gdk install` and wait (this takes a while)
3. Run `gdk start` to boot the development environment
4. Navigate to `http://localhost:3000` to confirm GitLab is running locally
5. Sign in with the default admin credentials shown in the GDK docs

#### Common GDK Issues and Fixes

| Problem | Fix |
|---------|-----|
| Docker memory errors / crashes | Increase Docker memory allocation to **8GB minimum** (Docker Desktop → Settings → Resources) |
| Ruby version mismatch | Use `rbenv` or `asdf` to install the Ruby version specified in `.ruby-version`. Run `rbenv install <version>` then `rbenv local <version>` |
| PostgreSQL connection error | Run `gdk restart`. If that fails, try `gdk reconfigure`. Check that PostgreSQL is running with `gdk status` |
| `bundle install` failures | Run `gem install bundler` first. If specific gems fail, check if you're missing system dependencies (the error message usually tells you which) |
| Node/yarn errors | Check `.node-version` and install the matching version via `nvm`. Then run `yarn install` |
| GDK takes forever to start | Normal on first boot. Subsequent starts are faster. If it hangs >20 min, check `gdk tail` for error logs |

> **If setup fails after 4 hours of effort:** Stop. Ask for help. Post your error logs in `#sp26-solution-planning` on our program Discord or in `#contribute` on the [GitLab Community Discord](https://discord.gg/gitlab). You can also bring your laptop to the next office hours session for live screen-share debugging. Don't let setup block you for days.

---

### Step 2: Create Your Working Branch (10 minutes)

Once your environment is running, create a branch in the **community fork** (not a personal fork):

1. Clone the community fork if you haven't already (the onboarding issue you completed in Week 0 has the correct URL):
   ```bash
   git clone https://gitlab.com/gitlab-community/gitlab.git
   cd gitlab
   ```
2. Make sure you're up to date:
   ```bash
   git checkout master
   git pull origin master
   ```
3. Create a working branch named after your issue:
   ```bash
   git checkout -b fix-issue-XXXXX
   ```
4. Push the branch so it exists on the remote:
   ```bash
   git push origin fix-issue-XXXXX
   ```

> **Note:** If your issue is on a different GitLab project (not the main `gitlab` repo), check the community forks for the matching project. The onboarding process you completed explains how to find the right fork.

---

### Step 3: Reproduce the Issue (1–2 hours)

Reproducing the issue means you can trigger the exact behavior described in the issue — consistently, not just once. This is critical because:
- It proves the issue still exists (it may have been fixed upstream)
- It gives you a baseline to test your fix against
- Your reproduction steps become documentation for your README

#### How to Reproduce

1. **Read the issue description again.** Look for reproduction steps if they're provided. If they aren't, look in the comments — maintainers or reporters often clarify steps there. Check if the MR coach you tagged in Phase I left any pointers.
2. **Follow the steps exactly in your local environment.** Navigate to the right page, enter the specified input, trigger the action.
3. **Document what you observe.** Write down:
   - What you expected to happen (the correct behavior)
   - What actually happened (the bug)
   - Any error messages, console output, or screenshots
4. **Reproduce it at least twice** to confirm it's consistent, not a fluke.
5. **If you can't reproduce it:** The issue may have been partially fixed, or your environment may differ from the reporter's. Check the issue comments for version information. Ask in `#sp26-solution-planning` or comment on the issue itself asking for clarification.

#### Using AI to Help Reproduce

Paste the issue URL or description into GitLab Duo or Claude Code and ask:
- *"Based on this issue, what files are likely involved?"*
- *"What steps would reproduce this bug in a local GDK environment?"*
- *"Where in the codebase should I look for the relevant code?"*

AI won't replace your own investigation, but it can point you to the right files and save hours of manual code-searching.

---

### Step 4: Write Your Solution Plan (1–2 hours)

Now that you can reproduce the issue, think through how to fix it before writing any code. A plan prevents wasted effort and gives mentors something concrete to review.

Your plan should answer four questions:

**1. What's the root cause?**
Why is this happening? Trace the behavior to the specific code (file, function, line if possible) that's responsible. Use AI tools to help navigate the codebase.

**2. What's your proposed fix?**
Describe the change at a high level. "I will modify the validation method in `user.rb` to check email format before saving" is good. "I will fix the bug" is not.

**3. What files will you touch?**
List the specific files you expect to modify. This helps mentors validate your approach.

**4. How will you verify it works?**
What tests will you write or run? How will you confirm the bug is fixed and nothing else is broken?

#### The UMPIRE Framework (Adapted)

Use this structure to organize your plan in your README:

- **Understand:** Restate the problem in your own words. What's broken? What should happen instead?
- **Match:** What similar patterns or solutions exist in the codebase? Find a related piece of code that does something similar to what you need.
- **Plan:** Step-by-step implementation plan. What will you modify, add, or remove?
- **Implement:** (You'll do this in Phase III — leave a placeholder link for your branch)
- **Review:** How will you self-review against [GitLab contribution guidelines](https://docs.gitlab.com/ee/development/contributing/)? Review GitLab's [commit message guidelines](https://docs.gitlab.com/ee/development/contributing/merge_request_workflow.html#commit-messages-guidelines) and [merge request guidelines](https://docs.gitlab.com/ee/development/contributing/merge_request_workflow.html) now so you're prepared.
- **Evaluate:** What tests will confirm your fix works? GitLab requires [automated testing](https://docs.gitlab.com/ee/development/testing_guide/) — understand the different testing levels and plan accordingly.

---

### Step 5: Update Your README and Check-In (30 minutes)

Add the following sections to your Contribution README:

- **Environment Setup:** Notes on challenges you faced and how you solved them (GDK-in-a-box vs. full GDK, any errors, how you resolved them)
- **Reproduction Steps:** Numbered steps another person could follow
- **Branch Link:** Direct link to your working branch in the community fork
- **Solution Plan:** Your UMPIRE-based plan or equivalent

Then submit your [check-in form](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) and indicate "Phase II Complete."

---

## Slippery Spots

### 🟡 "GDK won't install and I've spent 2 days on it."
**What's happening:** Environment setup friction. This is the most common Phase II blocker.
**Fix:** If you're using the full GDK install, try switching to **GDK-in-a-box** first — it eliminates most dependency issues. Post your exact error message in `#sp26-solution-planning` — include your OS, Docker version, and the last 20 lines of error output. You can also post in `#contribute` on the [GitLab Community Discord](https://discord.gg/gitlab) where GitLab team members help contributors with setup issues. Attend the next [office hours](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) for live screen-share debugging.

### 🟡 "I can't reproduce the issue — it seems to work fine for me."
**What's happening:** Environment mismatch, or the issue has been partially fixed.
**Fix:** Check the issue comments for specific version numbers or browser requirements. Run `git log` on the relevant file to see if recent commits may have addressed it. Check if your MR coach (tagged in Phase I) left any pointers. If you've genuinely confirmed the issue no longer exists, comment on the issue to report your findings (this is itself a valuable contribution!), then go back to Phase I and select a new issue.

### 🟡 "I can reproduce it but I have no idea what's causing it."
**What's happening:** Normal. Large codebases are hard to navigate, especially unfamiliar ones.
**Fix:** Use AI tools to trace the code path. Paste the relevant file into Claude Code and ask: *"What does this function do, and what could cause [symptom]?"* Look at `git blame` on the relevant lines to see when they were last changed and why. Check if the issue has labels pointing to a specific area (e.g., `~frontend`, `~database`). You can also ask your MR coach for pointers — they confirmed the issue in Phase I and may have hints.

### 🟡 "I jumped straight to coding without planning."
**What's happening:** The temptation to start fixing before understanding. This almost always leads to rework.
**Fix:** Stop coding. Go back to Step 4. Write the plan first. It doesn't need to be long — even a 5-bullet plan is better than none. Your Phase III work will be faster and more focused with a plan in hand.

### 🟡 "My plan seems too simple — is that okay?"
**What's happening:** You may have chosen a well-scoped issue. That's good.
**Fix:** Yes, simple plans are fine. "Fix typo in validation method, add unit test, verify existing tests pass" is a perfectly valid plan. Complexity is not a virtue in open source contributions.

---

## You're on the Right Track If...

- ✅ You can trigger the issue behavior on-demand in your local environment
- ✅ Someone else could follow your reproduction steps and see the same result
- ✅ You can name the specific file(s) and function(s) involved in the bug
- ✅ Your solution plan identifies a root cause, not just a symptom
- ✅ You documented your environment setup challenges (this helps others and shows mentors you're engaged)

---

## Strong vs. Weak README Examples

### ✅ Strong Example

```markdown
## Reproduction Process

### Environment Setup
Used GDK-in-a-box with VS Code — had it running in about 90 minutes. Only 
issue was needing to increase Docker memory to 8GB.

Working branch: https://gitlab.com/gitlab-community/gitlab/-/tree/fix-issue-12345

### Steps to Reproduce
1. Navigate to http://localhost:3000/profile/edit
2. In the email field, enter "notanemail"
3. Click "Save changes" button
4. **Expected:** Validation error appears, form doesn't submit
5. **Actual:** Form submits successfully, "notanemail" is saved to database

### Solution Plan
**Understand:** The profile edit form accepts invalid email formats without 
client-side or server-side validation feedback to the user.

**Match:** The `project.rb` model has a similar email validation pattern at 
line 89 that correctly rejects malformed emails.

**Plan:**
1. Fix the typo in `user.rb` line 45 (`validate_emai` → `validate_email`)
2. Add 3 unit tests in `spec/models/user_spec.rb`
3. Run full test suite to confirm no regressions

**Review:** Will self-review against GitLab commit message guidelines and 
Ruby style guide before opening MR.

**Evaluate:** Manual test reproducing steps 1-3 above should now show 
validation error. All existing tests should continue to pass.
```

**Why this works:** Specific setup path documented, branch in community fork, numbered reproduction steps anyone could follow, root cause identified with file/line references, plan tied to UMPIRE framework with review preparation.

### ❌ Weak Example

```markdown
I set up the development environment and was able to reproduce the bug. 
The email validation doesn't work.

## Solution Approach
I'll fix the email validation code and add some tests.
```

**Why this fails:** No detail on setup path, no branch link, no specific reproduction steps, no root cause analysis, vague plan. A mentor reading this would need to ask many follow-up questions.

---

## When and How to Escalate

Phase II should take **3–7 days**. The biggest blocker is typically environment setup.

### Level 1: Peer + AI + GitLab Community Help (anytime)
Post in **`#sp26-solution-planning`** on [Discord](https://discord.gg/YVVD9h9EJe) for program-specific help. For GDK and GitLab-specific questions, post in **`#contribute`** on the [GitLab Community Discord](https://discord.gg/gitlab) — GitLab team members actively help contributors there. Include your error messages, OS, and what you've tried.

### Level 2: Mentor / Office Hours (Tue & Thu)
GDK setup issues are the top use case for office hours. Bring your laptop, share your screen, and debug live with a mentor.
- **Tuesday 10–11am ET**
- **Thursday 5–6pm ET**
- Submit your question for the next [Office Hours](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) even if you can't attend live.

### Level 3: Direct Staff Support (Day 3+ with no environment, Day 7+ with no plan)
If you don't have a working environment by Day 3 of Phase II, the CodePath team will reach out with setup alternatives. If you don't have a plan by Day 7, you'll receive a template and examples. You can also email GitLab's Contributor Success team directly at **contributors@gitlab.com** for setup issues. You can always DM **Cam Flowers** or book a [1:1 session](https://calendar.app.google/RVukCQpVgxLFNF7Y7) before these thresholds.

---

## Phase II Deliverables Summary

| Deliverable | Where |
|---|---|
| Reproduction steps + branch link + solution plan | Your Contribution README on GitLab |
| Phase II marked complete | [Check-In Form](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) |
| Milestone announced | `#sp26-general` on Discord (recommended) |

---

## Resources

| Resource | Link |
|---|---|
| GDK-in-a-box Setup | [Configure GDK-in-a-box](https://gitlab.com/gitlab-org/gitlab-development-kit/-/blob/main/doc/howto/gdk_in_a_box.md) |
| GDK Full Install Guide | [gitlab.com/.../gitlab-development-kit](https://gitlab.com/gitlab-org/gitlab-development-kit/-/blob/main/doc/index.md) |
| GitLab Contribution Guide | [docs.gitlab.com/.../contributing](https://docs.gitlab.com/ee/development/contributing/) |
| GitLab Merge Request Guidelines | [MR Workflow](https://docs.gitlab.com/ee/development/contributing/merge_request_workflow.html) |
| GitLab Testing Guide | [Testing Levels](https://docs.gitlab.com/ee/development/testing_guide/) |
| GitLab Community Discord | [discord.gg/gitlab](https://discord.gg/gitlab) |
| Check-In Form | [Typeform](https://8jv7nzkftlz.typeform.com/to/IktTSGIa) |
| Office Hours | [Sign-Up Form](https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform) |
| Program Discord | [discord.gg/YVVD9h9EJe](https://discord.gg/YVVD9h9EJe) |
| Cam 1:1 Booking | [Calendly](https://calendar.app.google/RVukCQpVgxLFNF7Y7) |
| CodePath GitLab Project | [Contribution README](https://gitlab.com/codepath-org/ai-corps/spring-2026-gitlab-ai301/-/blob/main/students/CONTRIBUTION-README.md?ref_type=heads) |
| Contributor Success Email | contributors@gitlab.com |

---

## What Happens Next

Once your README has reproduction steps, a branch link, and a solution plan — and your check-in is submitted — **you're done with Phase II.** Move directly to **Phase III: Build**, where you'll implement your solution, write tests, and push working code.

Don't wait for permission to start coding. If your plan is solid, begin Phase III immediately.

---

*Phase II Written Guide — AI Corps x GitLab, Spring 2026.*