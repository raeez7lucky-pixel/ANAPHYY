# RAZZ — publishing & editing guide

This site is now split into small files instead of one giant HTML blob:

- `index.html` — the reader shell (sidebar, themes, chapter loader). You
  shouldn't need to touch this.
- `chapters.json` — the chapter list (id, title, filename).
- `content/chapters/chapter-01.html` … `chapter-20.html` — one file per
  chapter. This is what you'll edit.
- `images/` — where uploaded images live.
- `admin/` — a free, no-code content editor (Decap CMS) that lets you log
  in on the web and edit chapters + upload images from any browser, no
  coding required.

## 1. Put this on GitHub (no coding needed)

1. Go to https://github.com and create a free account if you don't have one.
2. Click **New repository**, name it (e.g. `razz-site`), keep it **Public**
   or **Private** (either works), click **Create repository**.
3. On the new repo page, click **uploading an existing file**.
4. Drag the *entire contents* of this folder (not the folder itself — the
   files and subfolders inside it) into the upload box.
5. Scroll down, click **Commit changes**.

## 2. Host it for free on Netlify

1. Go to https://app.netlify.com and sign up (you can sign up with your
   GitHub account — makes step 3 easier).
2. Click **Add new site → Import an existing project**.
3. Choose **GitHub**, authorize it, and pick the repo you just created.
4. Build settings: leave the build command **empty**, publish directory
   `.` (a single dot). Click **Deploy site**.
5. After a minute your site is live at a random address like
   `https://chipper-unicorn-123abc.netlify.app`. You can rename this
   (Site settings → Change site name) or add a custom domain later.

## 3. Turn on the no-code editor (Decap CMS)

1. In Netlify, go to your site → **Site configuration → Identity** → 
   **Enable Identity**.
2. Under Identity → **Registration**, set it to **Invite only** (so
   random people can't sign up).
3. Under Identity → **Services**, enable **Git Gateway**. This lets the
   editor save changes back to GitHub for you, invisibly.
4. Go to the **Identity** tab (top of the site dashboard) → **Invite
   users** → invite your own email address. Check your inbox and accept
   the invite — it'll ask you to set a password.
5. Visit `https://YOUR-SITE-NAME.netlify.app/admin/` and log in with that
   email + password.

You're in. From there you can:
- Click **Chapters** in the sidebar, pick a chapter, and edit its HTML
  directly, or
- Click **Media** in the sidebar to **upload images** — after uploading,
  copy the image's URL (it'll be something like `/images/my-photo.jpg`)
  and paste it into a chapter as `<img src="/images/my-photo.jpg">`
  wherever you want it to appear.

Every save in the editor automatically re-publishes the live site within
about a minute — no coding, no re-uploading files by hand.

## Notes
- Don't rename or delete files inside `content/chapters/` — `chapters.json`
  points to them by exact filename.
- If you want the chapter *titles* in the sidebar changed too, edit
  `chapters.json` (either directly on GitHub, or ask me to add a title
  editor to the CMS as well).
