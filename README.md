# project-pulse

AI-assisted project reporting: turns rough project notes into a status report, risk register, and vendor/partner tracker.

Takes the kind of informal notes you'd jot down after a stakeholder call or before a Monday status meeting — bullet points, half-sentences, whatever you have — and structures them into five outputs:

- **Status report** — executive summary plus a short narrative breakdown of progress, blockers, and next steps
- **Risk register** — extracted risks with severity, suggested mitigation, and owner
- **Vendor / partner tracker** — delivery status and flags for external agencies, vendors, or partners
- **Stakeholder communications plan** — who needs to hear what, on which channel, at what cadence
- **Change-management checklist** — a rollout checklist across the five standard phases (Prepare, Communicate, Train & Enable, Execute, Monitor & Sustain), tailored to your notes

Every tab can be exported as a single combined report, either as a print-ready PDF (via the browser's print dialog) or as a Word-compatible `.doc` file — no extra dependencies or accounts required.

## Why this exists

Most project management involves the same repeatable reporting: status dashboards, risk logs, vendor performance tracking, stakeholder updates — usually assembled by hand from scattered notes, emails, and calls, regardless of industry. This started as a personal tool to save myself that assembly work.

It's built to be generally useful for anyone running a project with moving parts and multiple stakeholders — not tied to any one industry or role. The sample notes are a composite, invented scenario (a website relaunch), not drawn from any real project.

It's a drafting aid, not a source of truth: every output is marked as a draft for review, and nothing here is intended to bypass the judgement of the person actually running the project.

## How it works

Single-file HTML/React tool, no build step. Paste project notes into the input panel, add your own Anthropic API key (kept in-browser, never stored or transmitted anywhere else), and it calls the Claude API with a system prompt constrained to extract only what's grounded in the notes provided (no invented names, figures, or details — except the change-management checklist, which may also include generally-applicable best-practice items for a rollout of that kind). It returns structured JSON rendered as five tabbed views: Status / Risks / Vendors / Comms Plan / Change Checklist.

## Usage

1. Open `index.html` in a browser (or serve it via GitHub Pages).
2. Paste your own project notes, or click "Load sample notes" to see a composite example (a generic three-market website relaunch).
3. Add an Anthropic API key — get one at [console.anthropic.com](https://console.anthropic.com) — and generate the report.
4. Check off items on the Change Checklist tab as you complete them (kept in memory for the session, not saved).
5. Use "Export PDF" or "Export Word (.doc)" above the tabs to download the full combined report for circulation.

## Stack

- Vanilla React (via CDN + Babel standalone) — no build step
- Anthropic Messages API (`claude-sonnet-4-5`)
- Self-contained single HTML file — bring your own API key

## Status

Early-stage personal project, actively evolving.

---
*AI-generated outputs require review before circulation.*
