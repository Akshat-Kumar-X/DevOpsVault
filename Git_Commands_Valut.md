# BitBucket/Git Commands Quick Revision Kit
* Bitbucket uses **Git under the hood**.
* Most Git commands remain the same — only the **remote URLs**, **authentication**, and **PR process (via UI/API)** differ slightly.

---

## ✅ **Essential Git Commands for DevOps + Bitbucket Usage**

### 🔹 1. **Repository Setup & Configuration**

| Task            | Git Command                                                                                       | Bitbucket Notes                               |
| --------------- | ------------------------------------------------------------------------------------------------- | --------------------------------------------- |
| Set global user | `git config --global user.name "Your Name"`<br>`git config --global user.email "you@example.com"` | Needed for commit authorship                  |
| Clone repo      | `git clone <repo-url>`                                                                            | Use Bitbucket clone URL (`https://` or `ssh`) |
| Check remote    | `git remote -v`                                                                                   | Shows Bitbucket URL                           |
| Add remote      | `git remote add origin <repo-url>`                                                                | For new projects                              |

---

### 🔹 2. **Branching & Navigation**

| Task              | Git Command                                                                          |
| ----------------- | ------------------------------------------------------------------------------------ |
| Check branches    | `git branch` (local)<br>`git branch -r` (remote)<br>`git branch -a` (all)            |
| Create new branch | `git checkout -b feature/my-feature`                                                 |
| Switch branch     | `git checkout develop`                                                               |
| Rename branch     | `git branch -m new-name`                                                             |
| Delete branch     | `git branch -d old-branch` (local)<br>`git push origin --delete old-branch` (remote) |

✅ **Bitbucket Tip**: You can also create and delete branches via UI.

---

### 🔹 3. **Staging & Committing Changes**

| Task              | Git Command                                              |
| ----------------- | -------------------------------------------------------- |
| Check status      | `git status`                                             |
| Add changes       | `git add .` (all files)<br>`git add file.txt` (specific) |
| Commit changes    | `git commit -m "Add login feature"`                      |
| Amend last commit | `git commit --amend`                                     |

---

### 🔹 4. **Pushing & Pulling**

| Task          | Git Command                                                         |
| ------------- | ------------------------------------------------------------------- |
| Push branch   | `git push origin feature/my-feature`                                |
| Pull latest   | `git pull origin develop`                                           |
| Pull + rebase | `git pull --rebase origin develop`                                  |
| Set upstream  | `git push --set-upstream origin feature/my-feature` (on new branch) |

✅ **Bitbucket Note**: Most teams enforce **protected branches** (like `main` / `master` / `develop`), so you may need to raise a Pull Request instead of directly pushing.

---

### 🔹 5. **Merge & Rebase**

| Task          | Git Command                                               |
| ------------- | --------------------------------------------------------- |
| Merge branch  | `git checkout develop`<br>`git merge feature/my-feature`  |
| Rebase branch | `git checkout feature/my-feature`<br>`git rebase develop` |
| Abort rebase  | `git rebase --abort`                                      |
| Abort merge   | `git merge --abort`                                       |

✅ **Bitbucket Tip**: Do the actual **Pull Request** merge via UI — Git only prepares the changes.

---

### 🔹 6. **Undo & Fixes**

| Task                    | Git Command                |
| ----------------------- | -------------------------- |
| Undo staged file        | `git reset file.txt`       |
| Undo last commit (soft) | `git reset --soft HEAD~1`  |
| Hard reset (dangerous)  | `git reset --hard HEAD~1`  |
| Revert commit           | `git revert <commit-hash>` |
| Clean untracked         | `git clean -fd`            |

---

### 🔹 7. **Logs & History**

| Task             | Git Command                                                |
| ---------------- | ---------------------------------------------------------- |
| Commit history   | `git log`<br>`git log --oneline`                           |
| Show diff        | `git diff`<br>`git diff HEAD`<br>`git diff origin/develop` |
| Who changed what | `git blame file.txt`                                       |

---

### 🔹 8. **Tagging Releases**

| Task       | Git Command                                                                   |
| ---------- | ----------------------------------------------------------------------------- |
| Create tag | `git tag v1.0.0`                                                              |
| Push tag   | `git push origin v1.0.0`                                                      |
| List tags  | `git tag`                                                                     |
| Delete tag | `git tag -d v1.0.0` (local)<br>`git push origin --delete tag v1.0.0` (remote) |

---

### 🔹 9. **Bitbucket-Specific Actions**

| Task               | How to Do                                                                                   |
| ------------------ | ------------------------------------------------------------------------------------------- |
| Create PR          | Do via Bitbucket UI or API:<br>`https://bitbucket.org/<workspace>/<repo>/pull-requests/new` |
| Approve / Merge PR | Use Bitbucket Web UI with reviewer rules                                                    |
| Add SSH Key        | Add via Bitbucket account settings for SSH access                                           |
| Webhook Setup      | In repo settings → Webhooks (for CI tools like Jenkins)                                     |

---

## 🚀 Pro Tips for Interns

* Always `pull` before you `push`.
* Use **feature branches** — never commit to `main`/`develop` directly.
* Keep commit messages meaningful (`feat:`, `fix:`, `refactor:`).
* Learn to resolve merge conflicts calmly — very common in DevOps life.
* Always test your changes before pushing.

---

Would you like a **Git command cheat sheet (PDF or image)** or a **practice repo** to try this out on? I can set that up next.
