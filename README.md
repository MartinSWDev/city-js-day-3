# CityJS London 2026 · Day 3 Schedule

An unofficial single-page schedule for Day 3 of [CityJS London 2026](https://london.cityjsconf.org/schedule) — all four tracks side by side, with clickable talks that open speaker bios and descriptions.

Built because the official schedule splits tracks across four tabs, which makes it hard to see what's clashing at any given time.

## Deploying to GitHub Pages

1. Create a new public repo on GitHub (e.g. `cityjs-london-day3`).
2. From this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. On GitHub, go to **Settings → Pages**, set **Source** to `Deploy from a branch`, pick `main` / `/ (root)`, and save.
4. The site will be live at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

## Editing the schedule

Everything lives in `index.html` as a single standalone file — no build step, no dependencies beyond a Google Fonts link.

The schedule data is a plain JavaScript `rows` array near the bottom of the `<script>` tag. Each row has:

- `time` — the start time as a string (e.g. `"14:25"`)
- one of `t1` / `t2` / `t3` / `t4` per track the talk belongs to
- or a `shared` object for breaks and lunch that spans multiple tracks

Track keys map to: `t1` = Great Hall, `t2` = Small Hall, `t3` = Session Room 1, `t4` = Session Room 2.

Each talk object supports `title`, `description`, `tags` (array), `isIntro` (flag for track-opening slots) and `speakers` (array of `{ name, company, bio, twitter, bluesky, linkedin }`).

## Known gaps

Session Room 1 (from 11:25 onwards) and Session Room 2 talks are listed with titles and speaker names only — the original source data was truncated before those descriptions could be captured. Filling those in is a matter of editing the relevant entries in the `rows` array.

## Credits

Schedule data from [london.cityjsconf.org](https://london.cityjsconf.org/schedule). This is a personal companion — not affiliated with the conference organisers.
