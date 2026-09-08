# Mr. Babb — Class Activities

Interactive classroom activities, hosted on GitHub Pages. Every activity is a single
self-contained HTML file: no build step, no dependencies, no CDN links, no tracking.
They run offline, on a Chromebook, and on a phone.

---

## ⚠️ Read this before you commit anything else

**This repository is public. Never commit a lesson plan or an answer key.**

The lesson plan for each activity (`*-lesson-plan.docx`) contains the full answer keys,
the exit-ticket letters, and the misconception notes. If it lands in this repo, students
can find it. Keep those files in Google Drive or on your own machine.

`.gitignore` already blocks the usual filenames, but `.gitignore` only protects you when
you commit with git. **If you upload files by dragging them onto github.com, gitignore is
not consulted** — check the file list yourself before you click Commit.

Answers inside the activities themselves are stored as salted hashes, so viewing source
does not reveal them. That defeats casual snooping; it will not stop a determined student
with the browser console.

---

## Setting up GitHub Pages (one time, about two minutes)

1. Create a new repository. Public is fine — that's what Pages needs on a free account.
   A short name is best, because it becomes part of the URL: `ccr` or `class-activities`.
2. Upload everything in this folder, keeping the folder structure. Drag the files onto the
   repo's upload page, or use **Add file → Upload files**.
3. Go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Set the branch to **main** and the folder to **/ (root)**. Click **Save**.
6. Wait about a minute, then reload the Settings → Pages screen. Your URL appears at the top.

Your site will be at:

```
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/
```

The activity itself is at:

```
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/ccr-111-letter-to-future-self.html
```

Give students either link — the first one opens the menu, the second jumps straight in.
Both work with no account and no sign-in, which is the whole point of hosting it this way.

---

## What's in here

```
index.html                              the menu students land on
ccr-111-letter-to-future-self.html      CCR 1.1.1 — the activity itself
handouts/
  ccr-111-do-now.docx                   student Do Now (no answers in it)
.nojekyll                               tells Pages to serve files as-is
.gitignore                              blocks teacher-only files from being committed
README.md                               this file
```

**Not in here, on purpose:** `ccr-111-lesson-plan.docx` (answer keys), the hash build
script, and the test suite.

---

## Adding the next activity

1. Drop the new `.html` file in the root, named all-lowercase and hyphenated:
   `csp-121-conditionals.html`.
2. Open `index.html` and copy one `<div class="item">` block. Change the code, title,
   description, tags, and `href`.
3. Commit. Pages redeploys in under a minute.

To start a new course section on the menu, copy the `<h2 class="sec">` heading and the
`<div class="grid">` block below it.

---

## Updating an activity

Upload the new version of the file with the same name and commit. Students get the new
version the next time they load the page — the URL never changes, so anything you already
posted to Classroom keeps working.

If a student says they're seeing the old version, have them hard-refresh:
**Ctrl+Shift+R** (**Cmd+Shift+R** on a Mac).

---

## Troubleshooting

**404 after setup.** Pages can take a few minutes on the first deploy. Confirm
Settings → Pages shows a green "Your site is live at…" banner, and that the branch is
**main** and the folder is **/ (root)**.

**The menu loads but the activity link 404s.** The filename must match the `href` in
`index.html` exactly — GitHub Pages is case-sensitive. `CCR-111-...` and `ccr-111-...`
are different files to it.

**The page loads unstyled.** That means the HTML file was altered on upload. Re-upload the
original file; don't paste the contents into GitHub's web editor.

**A student lost their work.** These activities intentionally store nothing. That is the
one real failure mode: have students copy their work out at the last section partway
through the period, not only at the end.
