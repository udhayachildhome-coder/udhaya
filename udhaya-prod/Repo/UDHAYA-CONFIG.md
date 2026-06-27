# UDHAYA — PROJECT CONFIGURATION
### Single source of truth · the "#attributes" full list

> Type **`#attributes`** in chat anytime and Claude will show you this full list.
> This file is your permanent copy — keep it with your project.
> ⚠️ No passwords or keys are stored here — those live in your password manager.

_Last updated: this session._

---

## 0 · Naming convention (use ONE name everywhere)
- **Project name everywhere:** `udhaya-prod`
  - Desktop folder → `udhaya-prod`
  - GitHub repo → `udhaya-prod`
  - Vercel project → `udhaya-prod`
- **Rules:** lowercase + hyphens, no spaces; never use `-old` / `1.1` / `Copy` /
  `final` / `v2` (GitHub keeps version history automatically); keep exactly ONE
  working folder; archive old folders as `_udhaya-archive`.
- **Do NOT rename the HTML files** — pages link to each other by exact filename.
- Supabase project stays `udhayachildhome` (name can't easily change; harmless).

## 1 · Organization
- **Name:** UDHAYA — United Human Action for Young Associates
- **Founded:** 1997
- **Location:** South India
- **Official tagline:** Lighting Lives Through Education, Care, and Compassion Since 1997
- **Three divisions:**
  1. Udhaya Children's Home
  2. Udhaya Education & Youth Development
  3. Udhaya Community Welfare & Family Support

## 2 · Design decisions (locked)
- **Public site theme:** Navy + Gold + Green (the version you kept)
- **Fonts:** Poppins (headings) + Inter (body)
- **Admin portal style:** Modern "bento" dashboard (gradient balance card, white sidebar,
  activity list) — colour-coded per division: indigo = Children's, emerald = Education, amber = Community
- **Pages are self-contained** (CSS lives inside each HTML file)

## 3 · Accounts
- **GitHub user:** `udhayachildhome-coder`
- **Supabase project:** `udhayachildhome`
  - URL: `https://nvawtcujzkxkzjbpisuo.supabase.co`
  - Region: _Mumbai (ap-south-1) or Singapore — confirm_
- **Vercel team:** `Udhaya-vercel` (Hobby / free plan)
- 🔑 _Saved separately in password manager:_ Supabase DB password, Supabase anon key.
  **Never store / commit the Supabase `service_role` key.**

## 4 · Tech stack & key choices
- **Public site:** HTML5 + CSS3 + vanilla JS, no frameworks
- **Hosting:** GitHub → Vercel (push → auto-deploy)
- **Backend:** Supabase (cloud Postgres) — chosen over self-host/local; relational; Row Level Security on every table
- **Admin / finance app:** React (built later)
- **Constraint:** everything on permanently free tiers

## 5 · The ONE clean repo (canonical files)
Source = `udhaya-site.zip`. Contains exactly:
```
index.html
about.html
division-children-home.html
division-education-youth.html
division-community-welfare.html
README.md
assets/images/
```
👉 Any folder with `index1.1.html`, `about-old.html`, `…Copy.html`, `donate.html`, etc.
is an OLD working copy — **not** the clean repo. Ignore those.

## 6 · Supabase database (already built ✅)
Tables, all with Row Level Security ON, all tied to a division:
- `divisions` — 3 rows inserted (public-readable)
- `profiles` — roles: `sponsor` / `staff` / `admin` / `super_admin`; auto-creates on signup
- `children` — locked down; staff see only their own division; no public/sponsor access
- `sponsors` — a sponsor sees only their own record
- `donations` — income; a sponsor sees only their own; staff see their division
- `expenses` — outflow; internal staff only

## 7 · Status
- ✅ Public site — 5 pages, frozen & complete
- ✅ Supabase database — built (6 tables, RLS enforced)
- 🟡 Deployment — **messy; doing a clean reset (see §8)**
- ⬜ Super-admin login (make yourself `super_admin`)
- ⬜ Connect the React front-end to Supabase
- ⬜ Build the admin portal screens

## 8 · CLEAN RESET PLAN (the fresh start)
**A. Tidy up the mess**
1. Vercel → delete any existing `udhaya…` project (Project → Settings → Delete Project).
2. GitHub → delete stray repos like `Udhaya-site` (repo → Settings → Danger Zone → Delete).
3. Local PC → rename the old cluttered folder to `udhaya-OLD-backup` (don't delete; just set aside).

**B. One clean repo (browser method — no GitHub Desktop)**
4. Extract a fresh `udhaya-site.zip` into a clean spot (e.g. Documents).
5. github.com → **＋ → New repository** → name `udhaya-prod`, **Private**, tick **Add a README**.
6. On the repo → **Add file → Upload files** → drag in the clean files → **Commit changes**.

**C. Deploy**
7. Vercel → **Add New → Project → Import** `udhaya-prod`.
8. Framework Preset: **Other** · Build Command: **empty** · Output Directory: **empty** → **Deploy**.
9. Open the `*.vercel.app` link → check all 5 pages + links work.

**D. Everyday workflow after launch**
- Change a file → upload/commit on GitHub → Vercel redeploys automatically (~20s).

## 9 · What comes next (after a clean deploy)
1. Create your login → set yourself as `super_admin`
2. Connect the front-end to Supabase (URL + anon key)
3. Build the admin portal (finance dashboard first) on real data
4. Wire up photo slots (see the photo map)
