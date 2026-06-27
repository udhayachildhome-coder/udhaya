# Udhaya.org

Website for **UDHAYA — United Human Action for Young Associates**, a charitable
trust supporting vulnerable children and families across South India since 1997.

**Status:** V1 public site — FROZEN. Plain HTML/CSS/JS, no frameworks.
Each page is self-contained (its styles are inside the file).

---

## Pages

| File | Page |
|------|------|
| `index.html` | Home |
| `about.html` | About Us |
| `division-children-home.html` | Division 1 — Children's Home |
| `division-education-youth.html` | Division 2 — Education & Youth Development |
| `division-community-welfare.html` | Division 3 — Community Welfare & Family Support |
| `assets/images/` | Drop real photos here |

All links between pages are verified — nothing 404s.

---

## How to deploy (high level)

GitHub stores the code → Vercel serves it at a URL. You push, Vercel redeploys.

1. Put this folder under Git version control.
2. Push it to a GitHub repository.
3. Import the repo into Vercel → you get a live URL.
4. From then on: edit → commit → push → site updates automatically.

Detailed click-by-click steps will be followed together, step by step.

### Vercel settings for this site
- Framework Preset: **Other**
- Build Command: **(leave empty)**
- Output Directory: **(leave empty)**

(Plain static files — no build step.)

---

## Adding photos later
Each page currently shows styled **placeholders** where photos go.
To add a real photo: upload it into `assets/images/` (GitHub's
**Add file → Upload files** works with no coding), then point the
matching `<img>` at it. A photo list (filename + size per slot) will be
provided when we wire these up.

---

## Coming after launch
- Supabase backend (database + logins)
- Sponsor / Admin / Setup portals
- Live photo uploads & dynamic updates
