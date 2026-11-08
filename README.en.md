# Life Guide · 生活指南

[简体中文](README.md) | **English**

![Zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)
![No build](https://img.shields.io/badge/build-none-blue)
![Four pages](https://img.shields.io/badge/web-4%20pages-lightgrey)
![Local-only data](https://img.shields.io/badge/data-local--only-orange)
![License: MIT](https://img.shields.io/badge/license-MIT-blue)

> Three practical guides to diet, exercise and sleep: turn daily decisions into concrete actions and numbers, with expandable evidence for key claims.

![Life Guide home page screenshot (Chinese UI)](https://cdn.jsdelivr.net/gh/isnotry/life-guide@main/docs/screenshot.png)

**[Open it online](https://kingsir.work/life-guide/)**

---

## What it is

Life Guide is a static four-page site: a home page plus three topic guides for diet, exercise and sleep. Each guide follows a day's timeline and turns "what should I do" into specific numbers, actions and boundary conditions.

All four pages are standalone single-file HTML documents with inline styles and scripts. There is no build step and no external runtime request; open `index.html` and read offline.

## Features

- **One entry, three topics** —— the home page orders three topic cards as diet, exercise and sleep, each with a one-line claim and its key numbers.
- **Built around a day** —— suggestions land on real time points, from breakfast, lunch and afternoon snacks to workout windows, caffeine cutoff and the bedtime environment.
- **Numbers for every recommendation** —— protein grams, plate proportions, weekly exercise minutes, step ranges, sleep duration and bedroom temperature all come with practical ranges.
- **Expandable, traceable evidence** —— 39 "What the research says" blocks expand in place, and 50 numbered sources are listed at the end; clicking an R badge jumps to and highlights the source.
- **Topics link to each other** —— persistent top navigation plus a "Read next" block at the end of each guide; from any topic you can reach the other two.
- **Boundaries, not absolute promises** —— sharp pain, dizziness and persistent insomnia are flagged with stop-or-seek-care guidance, and observational associations are kept separate from causal claims.
- **Four-week plans** —— each topic has a four-week schedule that starts at the lower bound and adds dose gradually.
- **Dark reading layout** —— 720px text width, sticky section navigation, timelines and two-column cards keep long pages scannable.
- **Recognizable icons and state** —— three inline SVG line icons represent diet, exercise and sleep; the current topic is highlighted in navigation.
- **Zero dependencies, zero upload** —— no backend, no account, no analytics; reading behaviour stays on your device.

## Quick start

### Use it online

Click **[Open it online](https://kingsir.work/life-guide/)** to start reading. No installation or sign-up required.

### Run it locally

```bash
git clone git@github.com:isnotry/life-guide.git
cd life-guide
open index.html
```

## Topics and key numbers

| Topic | Scenario | Number | Why it matters |
|---|---|---|---|
| Diet | Breakfast protein | 25–30 g | About one third of the day's protein; do not make it all carbohydrates |
| Diet | Plate proportions | 1/2 vegetables, 1/4 protein, 1/4 staples | Plate first, then eat; easier than stopping halfway |
| Diet | Dinner and bedtime | 4–6 hours, at least 3 hours | Leaves time for gastric emptying and reduces reflux |
| Diet | Daily protein | 0.8–1.2 g/kg, 20–30 g per meal | Total intake and distribution both affect satiety and muscle maintenance |
| Exercise | Aerobic | 150–300 min/week moderate, or 75–150 min vigorous | Can be accumulated; no need to do it all at once |
| Exercise | Strength | At least 2 sessions/week | Cover legs, push, pull, hips and core; it cannot replace aerobic work |
| Exercise | Daily steps | 7,000–8,000 steps/day; 6,000–8,000 for older adults | The step–risk link is observational, not a hard target |
| Sleep | Fixed wake time | Same time daily, within 30 minutes | Anchor the wake time first, then work on falling asleep |
| Sleep | Caffeine cutoff | 6–8 hours before bed; by 14:00–16:00 if sleeping at midnight | Half-life varies; sensitive people need an earlier cutoff |
| Sleep | Bedroom environment | 16–19°C, light below 1 lux | Temperature and light are variables you can physically change |

## UI reference

| Location | Element | Purpose |
|---|---|---|
| Home page | Three topic cards | Ordered diet, exercise, sleep; show icon, one-line claim, key numbers and entry |
| Topic page top | Topic navigation | Switch among Life Guide, Diet, Exercise and Sleep; current page highlighted |
| Topic page | Sticky section navigation | Jump by timeline or theme and auto-highlight the current section while scrolling |
| Body | Number badges, timelines, two-column cards | Break advice into time points, doses and "do / avoid" pairs |
| Body | "What the research says" button | Expand the study summary, sample size and limitations |
| End of page | Two "Read next" cards | Jump directly to the other two topics |
| Footer | GitHub open-source repository | Open the source code and README |

### Interactions

| Action | Location | Result |
|---|---|---|
| Click or press Enter / Space | "What the research says" button | Expand or collapse the evidence |
| Click an R badge | Inline evidence badge | Jump to the matching source at the end and highlight it briefly |
| Click a topic name | Top topic navigation | Open the corresponding topic page |
| Click a section name | Sticky section navigation | Smooth-scroll to that section |
| Scroll the article | Sticky section navigation | Auto-highlight the current section |
| Tab key | Links and buttons across the site | Show focus; press Enter to open a link |

## Reading and execution rules

```text
Start at the lower bound → Hold for two weeks → Add dose → Record the response
```

- Lower bound first: 150 aerobic minutes per week, 2 strength sessions and 7–9 hours of sleep already produce benefits; less is not "useless", just less beneficial.
- Add gradually: increase weekly volume by 5–10% or add one set; this is more sustainable than jumping to the upper bound.
- Boundaries first: stop and seek care for sharp pain, chest tightness, dizziness or palpitations; persistent insomnia at least 3 nights/week for more than 3 months should be treated with CBT-I first.
- Do not turn observational associations into causal claims: the step and strength-mortality numbers come from cohort studies, not a promise that hitting a number extends life.
- Judge weight by trend: 0.5–1 kg/week is a common sustainable range; do not expect a straight line.
- Environment beats willpower: snack visibility, where training gear sits, and bedroom light and temperature are more reliable than on-the-spot discipline.

## Data & privacy

The pages write nothing to local storage and read no account information. All content ships with the HTML, so reading makes no network requests.

| Item | Actual behaviour |
|---|---|
| localStorage / cookie / IndexedDB | None used |
| Runtime network requests | None; styles, scripts and icons are all inline |
| Data upload | None |
| Analytics | None |

## Project layout

```text
life-guide/
├── index.html          # Entry page: topic overview and smallest actions
├── diet.html           # Diet guide: daily food decisions and 15 sources
├── exercise.html       # Exercise guide: aerobic, strength, steps, recovery and 14 sources
├── sleep.html          # Sleep guide: daily time points and 21 sources
├── sitemap.xml         # Sitemap for the four pages
├── robots.txt          # Crawler rules and sitemap location
├── docs/
│   └── screenshot.png  # Real interface screenshot used by the READMEs
├── LICENSE             # MIT
├── README.md           # Chinese README
└── README.en.md        # This English README
```

## Development notes

- Each page inlines its own styles and scripts; when changing visual tokens, update all four files so topic pages and the home page stay in sync.
- The topic order is fixed as diet, exercise, sleep: home cards, top navigation, in-page "Read next" and footer links all follow it.
- When adding or removing a section, update that page's sticky navigation, scroll-spy and `sitemap.xml`.
- When adding evidence, add an `.ev` summary and an `.evref` badge in the body, then add the matching entry under `#refs`; do not skip or duplicate numbers.
- When changing the site URL or repository name, update canonical, Open Graph, JSON-LD, footer repository links and `sitemap.xml` on all four pages.
- Retake the screenshot after any UI change; both READMEs reference the same image.

## Browser support

- Current Chrome, Edge, Safari and Firefox are supported; the pages rely on CSS variables, Grid, `position: sticky` and `IntersectionObserver`.
- `backdrop-filter` is unavailable in a few older versions; the navigation keeps a readable background and functionality is unaffected.
- Pages open directly through `file://`; all cross-page links are relative, so the folder can be moved anywhere.
- Internet Explorer is not supported. With JavaScript disabled, evidence expansion and scroll highlighting stop working, but the article remains readable.

## License

[MIT](LICENSE) © 2026 isnotry
