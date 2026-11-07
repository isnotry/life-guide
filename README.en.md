# Sleep Guide · 睡眠修复指南

[简体中文](README.md) | **English**

![Zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)
![No build step](https://img.shields.io/badge/build-none-blue)
![Single file](https://img.shields.io/badge/web-1%20file-lightgrey)
![Data stays local](https://img.shields.io/badge/data-local--only-orange)
![License: MIT](https://img.shields.io/badge/license-MIT-blue)

> Sleep broken down into what to do at each hour of the day — 21 numbered sources and 13 expandable evidence notes, in one file, with no dependencies and no network calls.

![Screenshot](https://cdn.jsdelivr.net/gh/isnotry/sleep-guide@main/docs/screenshot.png)

**[Live demo](https://kingsir.work/sleep-guide/)**

---

## What it is

A sleep-repair guide **organized by time of day**, not a list of vague advice like "go to bed earlier, exercise more". From the moment you get up to the moment you turn off the light, each step is one concrete action with its numeric spec attached: how many hours, how many lux, how many degrees.

The whole thing is **a single `index.html`**: markup, styles and interactions are all inline, 41 KB, no npm, no framework, no backend — double-click and it opens.

Nine sections, 13 expandable evidence notes, 21 numbered sources (R1–R22, R3 is vacant). Every recommendation links back to its original study or clinical guideline, and the numbers were corrected against the research rather than recalled from memory.

The page makes **zero network requests** — it reads nothing but itself.

Note: the interface is written in Chinese; this README is the English companion to that page. The screenshot above shows the actual Chinese UI.

## Features

- **A two-engine framework** — sleep onset needs both the circadian phase and the sleep pressure; everything else is built on that split
- **Nine sections in order of the day** — principle / morning / daytime / before bed / environment / can't sleep / four-week plan / when to see a doctor / sources
- **A numeric spec on every recommendation** — 30-minute window, 10,000 lux, 6–8 hours before bed, 16–19°C, all written as values you can check
- **Evidence you can expand** — 13 "show the evidence" buttons, 11 of them carrying a numbered badge that smooth-scrolls to the reference and highlights it for 1.8 seconds
- **Counter-intuitive findings called out** — blue light is not the main problem, "a little alcohol helps me sleep" costs you REM in the second half of the night, weekend catch-up sleep is about jet lag rather than the extra hours
- **Stimulus control in full** — the five steps of leaving the bed after 20 minutes awake, and why it is so hard to do
- **A four-week ramp, not everything at once** — week 1 is only the anchor, week 3 adds the environment, week 4 calibrates by sleep efficiency
- **Red lines in plain sight** — loud snoring with observed apnoea, daytime sleepiness, restless legs, severe difficulty falling asleep: four cases that point straight to a clinic
- **Dark by design** — the page stays dark and does not follow the system theme
- **No dependencies, no build** — no web fonts, no icon library, no CDN; offline it renders exactly the same

## Quick start

### Use it online

Click **[Live demo](https://kingsir.work/sleep-guide/)** to open it — nothing to install, no sign-up.

### Run it locally

```bash
open index.html
```

There is no build step; edit and refresh.

## Cheat sheet

| Time of day | What to do | Numeric spec |
|---|---|---|
| The moment you get up | Rise at a fixed time | Off by no more than 30 minutes |
| 30–60 min after waking | Go outside for daylight, clouds included | 10,000 lux · 10–20 minutes |
| Within 1 hour of waking | One glass of warm water | 200–250 ml |
| Within 2 hours of waking | Breakfast plus the day's physical activity | Exercise ends 3 hours before bed |
| Daytime | Caffeine cut-off | 6–8 hours before bed (asleep at 00:00 → last cup 14:00–16:00) |
| Daytime | Nap limit | ≤20 minutes · none after 15:00 |
| Dinner | Gap before lying down | Ideal 4–6 hours · minimum 2–3 hours |
| 1–2 hours before bed | A warm bath or shower | Warm, not hot |
| 30–60 min before bed | Screen cut-off | Phone out of the bedroom, dim the lights, notifications off |
| 20 minutes awake in bed | Leave the bed, return when sleepy | Repeat; fixed wake time regardless |
| Bedroom temperature | Air-conditioner set point | 16–19°C (20–25°C for older adults) |
| Bedroom light level | Physical blocking | Target <1 lux |

## UI reference

| Where | Element | What it does |
|---|---|---|
| Top | Title block and five spec pills | Adults 7–9 h / fixed wake time / 10,000 lux / caffeine 6 h / 16–19°C |
| Nav bar | Nine sticky anchors | Highlights the section you are currently reading |
| Body | Timeline (`tl-item`) | The morning section runs in minutes after waking |
| Body | "Show the evidence" button | Expands or collapses the research note; label toggles between the two |
| Body | Blue `R# ↗` badge at the end of a note | Smooth-scrolls to the matching entry under sources and highlights it for 1.8 s |
| Body | Advice / avoid twin panel | The do-and-don't list in the daytime section |
| Body | Red card | The four see-a-doctor cases |
| Footer | "GitHub 开源仓库" text link | Opens this repository in a new tab |

## Interaction

| Action | Result |
|---|---|
| Click "show the evidence" | Expands that research note; click again to collapse |
| Click the `R# ↗` badge | Scrolls to the reference entry, adds a `hit` class, clears it after 1.8 seconds |
| Click a nav anchor | Smooth-scrolls to the section (`scroll-behavior: smooth`) |
| Scroll the page | Uses `scrollY + 130` to decide which nav item is highlighted |
| What is not there | No keyboard shortcuts, no search box, no forms — this is a reading page |

## Content model

```text
sleep onset = circadian phase aligned ∧ sleep pressure sufficient
sleep pressure = hours awake × adenosine built up − (caffeine block + naps withdrawn early)
```

- **Engine one · circadian clock** — the suprachiasmatic nucleus only knows "what time it is"; it is anchored by morning light and a fixed wake time
- **Engine two · sleep pressure** — adenosine accumulates while you are awake and is cleared by sleep; caffeine blocks the receptors, naps spend the budget early
- **Three saboteurs** — caffeine, alcohol, and daytime naps with weekend lie-ins; every section is organised around them
- **How badges are wired** — the `MAP` object in the script has 13 keys, 11 of which point at a real entry; `e2` (warm bath) and `v3` (noise) have no dedicated source, so they expand without a jump
- **Reference numbering** — 21 entries under R1–R22; R3 is currently vacant and can be filled directly

## Data & privacy

This page **creates and stores nothing**: no `fetch`, no `localStorage`, no cookies, no analytics; every font and icon comes from the system.

| Item | Status |
|---|---|
| Network requests | None; the page has no external resources |
| `localStorage` / `sessionStorage` | Not used |
| Cookies / analytics | None |
| Server side | No backend, static hosting only |
| Offline | Behaves exactly as it does online |

## Project layout

```text
sleep-guide/
├── index.html            # Markup, inline styles and inline interaction script
├── docs/
│   └── screenshot.png    # README image
├── LICENSE               # MIT
├── README.md             # Chinese README
└── README.en.md          # This file
```

## Development notes

- Styles, structure and script all live in `index.html`: `<style>` at the top, `<section>` blocks in the middle, `<script>` at the bottom. Edit and refresh.
- To add an evidence note you touch three places: `class="ev" data-for="<key>"` on the note, a `<button class="evtog" data-t="<key>">` below it, and `<key>: 'r<number>'` in `MAP` (use `null` for no jump).
- To add a reference, drop `<div class="ref" id="r<number>">` into the right group under sources — the `id` is what the badge scrolls to.
- If you reorder sections, update the nav too: the nine `<a href="#...">` entries map one-to-one to the `section` `id`s.
- Change a number and change the evidence with it — the footer states the content is based on public research up to October 2026, and the spec has to match its source.
- The footer link points at the upstream repository; if you fork it, swap that `href` for your own.

## Browser support

- Modern Chrome / Edge / Firefox / Safari all work; IE is not supported.
- Required capabilities: `scroll-behavior: smooth`, `scrollIntoView({behavior:'smooth'})`, `classList.toggle`, `backdrop-filter` (the frosted nav bar).
- Without `backdrop-filter` the nav bar falls back to a solid background and everything else still works.
- Below 640 px the title and the twin panels collapse to one column; the timeline and evidence toggles behave the same.
- The page is dark by design and does not follow the system theme.

## License

[MIT](LICENSE) © 2026 isnotry
