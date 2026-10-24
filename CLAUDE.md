# Road Trip (Nullarbor Adventures) — read first

Personal trip diary for Heather, Ossie, Garry and Margaret (Aug–Sep 2026).
NKW-wide rules and build standards live in
`..\Indexes\_ref_build_standards.md` and `..\Indexes\NKW_Automations_Index.md` (row 11).

## Architecture (Pattern A — static HTML + Supabase)
- **Runs:** shared link in a phone browser / home-screen icon.
- **Data:** Supabase project `fmmltsrmyhxtmqseuxck` (Nullarbor Adventure org).
  **Shared with Backtrack — do not change project settings, keys or other tables.**
  Tables `roadtrip_*`, storage bucket `roadtrip`. Publishable key is embedded in
  `index.html`; no Supabase Auth, so no auth redirect URLs to maintain.
- **Deploy:** GitHub Pages from `nwebb16/nullarbor`, branch `main`, root.
  This folder is the git working copy: edit, commit, `git push`, and Pages
  rebuilds in about a minute. (Moved from Netlify 25/10/2026.)

## Live links
- Site: https://nwebb16.github.io/nullarbor/
- Heather (can post): https://nwebb16.github.io/nullarbor/heather.html
- Margaret (can post): https://nwebb16.github.io/nullarbor/margaret.html

`heather.html` / `margaret.html` just redirect to `index.html?post=<code>`;
the posting code is what lets that person add posts.

## What is and isn't in the repo
Published: `index.html`, `heather.html`, `margaret.html`, `manifest.webmanifest`,
`assets/`, `CLAUDE.md`. Not published (see `.gitignore`): the `.zip` files and
`supabase-setup.sql`.

## Rules
- Additive changes only; take a dated backup (`name.backup-YYYY-MM-DD.ext`)
  before changing a live file. Backups are git-ignored.
- New Supabase tables/views/functions need explicit grants (see build standards §2).
- Paths are relative (`assets/...`), so the site works under the `/nullarbor/` subpath.
