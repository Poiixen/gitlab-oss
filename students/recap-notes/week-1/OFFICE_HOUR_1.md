# 🎉 GitLab x CodePath AI Corps — Office Hours #1 Recap
**February 24, 2026 | Week 1**

---

## Who Was in the Room

We were joined by three incredible GitLab engineers who volunteered their time to support you:

- **Alberto Bignotti** — Backend Engineer, DevEx::API Team | Berlin, Germany
- **Allen Cook** — Senior Backend Engineer, Code Creation (AI/Code Suggestions) | Kentucky, USA
- **Rocky Mongare** — Support Engineer | Nairobi, Kenya

Students **Mike**, **Soney**, and **Shikha** came with great questions — and the whole conversation is worth watching in the recording. Here's what you need to know before your first Typeform submission.

---

## Making Phase 1 More Manageable: How to Pick Your Issue

The #1 question this week was *"How do I find and choose the right issue?"* — and the mentors had a lot of wisdom to share.

**Start with the `quick win` label.**
Rocky dropped two links in chat, and the difference between them matters. These are pre-filtered issues that are open, unassigned, and tagged specifically for contributors getting started — don't scroll through 44k+ issues cold.

- [Quick Wins — gitlab-org/gitlab (the main platform)](https://gitlab.com/gitlab-org/gitlab/-/work_items?sort=created_date&state=opened&assignee_id=None&label_name%5B%5D=quick%20win&first_page_size=100)
- [Quick Wins — All of gitlab-org (the full organization)](https://gitlab.com/groups/gitlab-org/-/work_items?sort=created_date&state=opened&label_name%5B%5D=quick%20win&first_page_size=100)

**Here's the distinction Rocky made, and why it matters for you:**

The **first link** scopes to `gitlab-org/gitlab` — the core GitLab platform repository. This is the main product most people think of when they think "GitLab." Issues here are primarily in **Ruby**, since that's the dominant language of the platform. If you're comfortable with Ruby, or the Rubocop/JSON SafeParse quick wins look appealing, this is your starting point.

The **second link** searches across the entire **gitlab-org organization** — a much broader umbrella. GitLab the organization maintains dozens of projects beyond the core platform: things like a Terraform provider, GitLab CLI tools, language-specific SDKs, documentation tooling, and more. Rocky specifically called out the **Terraform provider** as one example of what you'll find there. This means if Ruby isn't your language, you're not locked out — there are quick win opportunities in Go, Python, JavaScript, and other languages depending on the project.

So if the first link feels narrow or the issues don't match your stack, go to the second link and browse by project. You'll likely find something that plays to your strengths.

**You don't need to solve a huge problem.** Alberto put it well: the goal isn't to tackle something massive *or* to knock out something trivial in 10 minutes. Calibrate to something you can reasonably explain what's going on — and that you can complete within the 10-week window. A one-line fix still counts. It still gets reviewed. It still teaches you the full contribution workflow.

**Rubocop / JSON SafeParse issues are a solid starting point.** Many of your cohort peers have already selected these. Alberto confirmed from his own experience: you don't even need to install the full GDK locally to complete them. Luciano (who joined later) verified the same — some of these can be done entirely through GitLab's **Web IDE**, right in your browser.

**Should you pick something in a language you don't know?** Cam and Alberto both weighed in: if you're unfamiliar with the language, a small quick-win issue is a great way to still learn it without getting stuck. AI tools are your friend here. If an issue is genuinely too large to complete in this program, that doesn't mean it's not worth working on later — just not the right fit for right now.

**How do you know no one else is working on it?** Assign yourself using the **@gitlabbot** command on the issue. Since you're an external contributor (not a GitLab team member), you can't assign directly — you use the bot. Rocky also pointed out you can check the issue's **Activity** section to see if it's been mentioned in any existing merge requests.

---

## Decoding the GitLab Issue Board: Groups, Sections & the Handbook

If the GitLab issue board UI has felt overwhelming, you're not alone — Alberto literally said *"I would get dizzy from all the labels"* when he was contributing from the outside. Here's what the mentors broke down that makes it click:

**Groups = Teams.** When you see a label like `group::runner` or `group::security policies` on an issue, that's GitLab's internal way of routing it to a specific engineering team. Alberto's group, for example, is 4–5 people focused on the API platform. If you have a domain you care about (like CI/CD, security, code review), you can use the group label to filter issues down to that team's work.

**Sections = Departments.** Sections sit above groups — think of them as a set of related teams under a broader area of the product. So if you're looking at `section::ci`, that's the whole CI/CD part of the engineering org, not just one team.

**How to use this for issue selection:** Allen's advice was to look up the engineering groups in the GitLab handbook, find one that maps to something you're interested in, and go look at their specific issues for quick wins. This is especially useful if you're Soney and want to stay in the CI/CD space — filter by `group::` labels in that section instead of scrolling everything.

**The GitLab Handbook is public — and it explains all of this.** Rocky linked it mid-session and it's genuinely one of the best resources available to you. It maps out the entire product category hierarchy: which groups exist, what they own, and how they're organized. You don't have to guess what a label means.

- [GitLab Product Category Hierarchy](https://handbook.gitlab.com/handbook/product/categories/#hierarchy) — bookmark this

**Pro tip from Alberto:** The handbook has the answers, but it can be hard to navigate cold. His suggestion? *Use AI (like Claude) to read the handbook and surface what you need.* Ask it something like "What does the group::runner team own in GitLab?" and you'll get a much faster answer than digging manually.

---

## Key Resources Shared

| Resource | Link |
|---|---|
| Quick Win Issues (gitlab-org/gitlab) | https://gitlab.com/gitlab-org/gitlab/-/work_items?sort=created_date&state=opened&assignee_id=None&label_name%5B%5D=quick%20win |
| Quick Win Issues (all groups) | https://gitlab.com/groups/gitlab-org/-/work_items?sort=created_date&state=opened&label_name%5B%5D=quick%20win |
| GitLab Category Hierarchy (to understand the platform) | https://handbook.gitlab.com/handbook/product/categories/#hierarchy |
| Issue Triage / Severity & Priority Labels | https://handbook.gitlab.com/handbook/product-development/how-we-work/issue-triage/ |
| Contributing to Premium/Ultimate Features | https://docs.gitlab.com/development/contributing/#contributing-to-premiumultimate-features-with-an-enterprise-edition-license |
| Discord: Office Hours channel | https://discord.com/channels/1417608659508265123/1475008043036049541 |
| Office Hours Question Form | https://docs.google.com/forms/d/e/1FAIpQLSdeneeh8_VFDUVn3NmwVaQ4-dpfyTx3fOPfY4oVkUFY6EkXXg/viewform |

---

## Still Stuck? We'll Help You Pick One.

If you've gone through the quick win lists, tried filtering by group or section, and you're still not sure what to pick — don't spin your wheels. Reach out to **Cam directly** and we'll help assign you an issue to get started. No shame in it, that's what we're here for.

You can DM Cam on Discord or reach out through the program channels. Just say you're stuck on issue selection and we'll get you sorted.

---

## Words of Encouragement from Your Mentors

> **Rocky:** *Shared an immediate action — a comment on how to assign yourself to an issue so you can get moving right now. He literally did it mid-session. That's the energy.*

> **Alberto:** "When I was contributing, I was self-conscious — like, is my contribution worth the reviewers' time? Is it up to standard? **Don't question yourself, and don't question the patience of GitLab people.** Everyone I've worked with there is great, super helpful, and most of all — they're happy to help. Really, don't worry."

> **Allen:** "Feel free to reach out. We're here to help you learn GitLab. Just get your issues done and ask any questions — we're here."

---

## What Happens Next

Your **first Typeform submission** is coming up. Here's what it needs to reflect:

- The **issue you selected** (link in your README)
- A **"Why I chose this"** section showing you understand the problem
- A brief **problem summary** in your own words

You don't need to have solved it yet — you just need to have chosen it thoughtfully and be able to explain it.

If you're still finding your issue, use the quick win links above, filter by a language or area you know, and pick something you can describe in a sentence or two. That's Phase 1. You've got this.

**Questions?** Drop them in Discord or use the question form above — mentors are checking asynchronously throughout the week.

---

*See you at the next office hours. 🚀*