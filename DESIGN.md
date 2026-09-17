# Design direction

Canonical public page: `public/index.html`. Everything in `experiments/` is an unpublished variant, kept for reference, not deployed (see `netlify.toml`, `publish = "public"`).

## Audience

Senior iOS developer portfolio for recruiters and engineering leaders. Readers are scanning for scope of ownership, technical range, and evidence (crash-free rate, team size, years), not browsing for entertainment.

## Identity

Editorial craft language: warm paper background, one restrained bronze accent, serif display face over a plain sans body. The page reads like a considered piece of writing, not a product landing page or a developer-tool dashboard.

## Dials

- **Energy 2** — one accent color, no gradients or glow, hover/active states only.
- **Rhythm 2** — generous section spacing, content-led hierarchy (Work, Experience, Skills, Education, Contact), no dense grid of cards.
- **Motion 1** — hover/active feedback only, `prefers-reduced-motion` respected everywhere.

## Palette

| Token | Role | Reason |
|---|---|---|
| `--color-paper` / `-2` | Background | Warm off-white instead of pure white — matches the editorial, printed-page feel. |
| `--color-ink` / `-dim` | Text | Near-black warm ink, dimmed variant for secondary text — keeps contrast high without going flat black. |
| `--color-accent` | Bronze | Single accent color used for links, focus rings, and one hero highlight — scarcity keeps it meaningful. |
| `--color-border` | Dividers | Low-contrast hairlines instead of shadows — section breaks read as typographic rules, not UI chrome. |

## Typography

- **Fraunces** (display, headings) — a serif with editorial weight, signals craft and seniority rather than a generic startup sans stack.
- **Inter** (body) — a plain, highly legible sans so long paragraphs of experience copy stay easy to scan; the pairing puts personality in headings only.

## Techniques and why

- **Sticky blurred nav** — keeps section jump-links reachable on a long single page without permanently occupying vertical space.
- **Restrained corner radii (3px)** — enough to soften edges, not enough to read as "app UI."
- **Content-led work/experience sections** — evidence (metrics, dates, org names) is the layout's organizing principle, not decorative cards.
- **750px masthead reflow:** the stacked navigation remains active until the full masthead fits without squeezing the name.
- **Mobile spacing step:** narrow screens use smaller wrapper, section, button, and card padding so the content stays dominant.
- **Context-aware focus colors:** bronze identifies focus on paper, while the paper color keeps the same indicator visible on the dark footer.
- **Employer inside the role heading:** five roles share the same job title, so the employer belongs in the heading text or a screen-reader heading list reads as five identical entries.
- **One neutral descriptor per employer:** every Experience entry carries exactly one plain factual line about the company, so the pattern has a rule instead of appearing on some entries and not others, and none of them borrows the employer's marketing language.
- **Earlier roles compressed into one entry:** three roles had no contribution evidence to show, so they are grouped rather than padded out to look equal to roles that do have evidence.
- **Skills grouped, verifiable only:** three named groups (languages and frameworks, architecture, tooling and delivery) let a recruiter scan by category; unverifiable soft-skill claims and routine activities every developer performs were removed because the Experience bullets already demonstrate them with proof.
- **Footer colophon:** the closing display line signs the page the way the masthead opens it, instead of repeating a metric already stated in Experience.

## Technical variant (`experiments/technical/`)

Kept the dark phosphor palette and monospace type — that's the theme's actual identity (an engineering-audience read) and the green left-border accent on stat/job blocks, which functions as a scan aid for grouping discrete evidence entries. Removed the terminal-costume layer that didn't serve scanning: `$`/`//`/`>` prompt-and-comment-syntax decorations, and the `.log`/`.json`/`contact()` fake-file-extension labels — these were genre signaling with no functional payoff.

## Why seven variants exist

The other six pages in `experiments/` are exploratory alternatives to the canonical identity above, not user-facing choices. They are excluded from the Netlify publish directory so only one identity ships.
