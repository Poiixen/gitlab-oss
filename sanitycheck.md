# Tito git refresher

git push origin main   # → GitLab 
git push github main   # → GitHub 

## check for status
```bash
git status                   # see what files changed
git remote -v                # verify your remotes (GitLab + GitHub)
git log --oneline            # see recent commits
```

---

## save changes (Stage → Commit → Push)
```bash
git add .                    # stage ALL changed files
git add filename.py          # stage a specific file

git commit -m "msg" # commit with a message

git push origin main         # push to GitLab (professor sees this)
git push github main         # push to GitHub (contribution graph)
```

---

## pulling
```bash
git pull origin main         # pull latest from GitLab
```

---

## branches 
```bash
git branch                   # see all branches
git checkout -b branch-name  # create + switch to new branch
git checkout main            # switch back to main
```

---

## on da daily
```bash
# Pull latest changes first
git pull origin main

# 3. Make your changes in VS Code...

# 4. Stage + Commit
git add .
git commit -m "msg"

# 5. Push to both
git push origin main   # GitLab 
git push github main   # GitHub 
```

---