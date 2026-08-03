# CLAUDE.md · juliaburmistrova.com

Personal site for Julia Burmistrova, built as a Jekyll site and deployed via GitHub Pages at the custom domain www.juliaburmistrova.com. Replaces a Squarespace-designed site. The domain stays registered with Squarespace, only the website builder is being dropped.

## Identity & framing

- Julia is a **data engineer**. Lead with that everywhere: hero copy, About. She's worked in data engineering / data and coding since **February 2020**. Don't hardcode a year count in copy: `index.html` computes "X+ years" client-side on load from that start date (see the `<script>` at the bottom of the file, targeting `#years-badge` and `#years-text`), so it stays correct without edits. If you add the years figure anywhere else, wire it into that same script rather than writing a static number.
- She has a background in environmental/geospatial data (ecosystem monitoring, fieldwork, lab work). Frame this as *why* she's comfortable with varied, messy data sources, never as a past career she's stepping away from or might return to. Don't write copy implying she wants to go back to environmental work.
- Drone/UAV work is her own skill/experience. **Do not name specific companies she has applied to but not heard back from** (e.g. Zipline) anywhere on the site.

## Voice

All first-person prose on the site (About, project descriptions, contact copy) must follow **`~/career/career-ops/voice-dna.md`**. Read that file at the start of any session that writes or edits site copy. Don't rely on a cached summary of it.

Key things from it that matter most here:
- Short paragraphs (1-2 sentences, 3 max). No warm-up laps.
- Contractions, "I"/"you", active voice. Take a stance, don't hedge into "may/could/often."
- Genuine hedging when it's real ("I think," "probably") is fine and matches her actual voice, but don't oversmooth confidence out of statements she'd actually make plainly.
- **No em dashes, anywhere on the site, including titles, captions, and placeholder text.** Use a period, comma, colon, or the mono-label eyebrow style (`·`) instead.
- Hard-banned AI vocabulary and phrases (see the file's section 3): things like "delve," "leverage," "seamless," "it's important to note," and especially negative-parallelism constructions ("This isn't X, it's Y") are fatal, rewrite on sight.
- Sentence case in headers, not Title Case.

This applies to prose content. Standard, functional UI copy (button labels like "Send," nav items) stays plain UX copy and doesn't need to perform voice.

## Hard content rules

- **No email address or `mailto:` link anywhere on the site.** She doesn't want to get spammed. All contact goes through the contact form only.
- **No blog.** No blog nav item, no blog layout in active use. She doesn't have time to maintain one. (The repo has leftover Jekyll blog scaffolding from 2021; treat it as dead unless she asks to revive it.)
- **Never fabricate or AI-generate photos of Julia or her fieldwork.** Use clearly-marked placeholder slots until she supplies real images, then swap in directly. Don't invent a face or a scene standing in for a real one.

## Site structure (decided)

- Nav: Home, About, Projects, Field Notes, Contact
- **No CV/resume page.** She tailors her resume per job application, so a static on-site version would go stale or conflict with the tailored copy. LinkedIn (already linked in nav/footer) covers the always-current formal work history instead. Don't add a CV page or "download resume" button unless she asks again.
- **Field Notes** is a dedicated gallery page for fieldwork/lab photos (chosen over a homepage photo strip).
- Contact section includes an "Areas of Expertise" tag row (Programming/Coding, Laboratory Analysis, Fieldwork, Remote Sensing, Teaching & Mentorship) above the form.
- Contact form submits via Formspree (or equivalent) since GitHub Pages is static-only.

## Design system (approved, ask before changing)

- **Palette**: sage paper background, deep teal primary accent, muted ochre secondary accent. Named tokens: `--ink #172420`, `--paper #eef1ea`, `--accent #2f6f6a` (teal), `--ochre #a97a34`, `--line #c7cdbd`. Full light/dark pairs live in the approved mockup artifact.
- **Type**: serif display face (Georgia-based stack) for headings, system sans for body copy, monospace for labels/tags/metadata (e.g. project eyebrows, field/lab instrument tags).
- **Visual language**: field-notebook / data-catalog feel. Hairline rules, square-ish cards (not heavily rounded), metadata tags instead of decorative numbering, a restrained topographic-line accent in the hero.

## Git / commits

- **Never commit without asking first, every time.** Not a one-time approval; check before each commit, even small ones.
- **Never add Claude as a co-author or contributor.** No `Co-Authored-By: Claude` trailer, no mention of Claude/AI generation in commit messages. Commits should read as Julia's own work, attributed only to her git identity.
- Never push to `main`/`origin` without explicit permission in the moment.

## Tech

- Jekyll, built natively by GitHub Pages (no CI/Actions needed).
- Custom domain: `CNAME` file in repo root (`www.juliaburmistrova.com`), custom domain set in repo Settings → Pages, HTTPS enforced. `www` is canonical; apex redirects to it.
- DNS is managed in Squarespace's advanced/custom-records mode (domain-only, no connected Squarespace site).
