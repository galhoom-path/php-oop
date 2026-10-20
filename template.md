# Study Repository Template — Lectures → Interview Questions → Visual Maps → Final Project

> A reusable blueprint for building a complete, source-backed study repository for **any subject**
> (PHP, Design Patterns, OOP, SQL, Docker, Laravel, System Design, English grammar, Accounting, ...).
>
> Every repository built from this template has the **same structure, the same files, the same rules,
> and the same learning method**. Only the subject-specific content changes.
>
> **Template last synced with the repository:** 2026-10-21
> This file must always mirror the repository. See [Section 19](#19-template-sync-rule-keep-this-file-a-mirror).

---

## Table of Contents

1. [How to Use This Template](#1-how-to-use-this-template)
2. [Placeholders (Fill These First)](#2-placeholders-fill-these-first)
3. [Core Principles of the Method](#3-core-principles-of-the-method)
4. [Source and Freshness Rules (Mandatory)](#4-source-and-freshness-rules-mandatory)
5. [Sizing Rules (How Many Lectures, Questions, Milestones)](#5-sizing-rules-how-many-lectures-questions-milestones)
6. [Repository Structure](#6-repository-structure)
7. [Naming Conventions](#7-naming-conventions)
8. [File Template — Root `README.md`](#8-file-template--root-readmemd)
9. [File Template — `01-Lectures/README.md`](#9-file-template--01-lecturesreadmemd)
10. [File Template — Lecture Folder Files](#10-file-template--lecture-folder-files)
11. [File Template — `02-Interview-Questions/README.md`](#11-file-template--02-interview-questionsreadmemd)
12. [File Template — Question Folder `README.md`](#12-file-template--question-folder-readmemd)
13. [File Template — `03-Visual-Maps/README.md`](#13-file-template--03-visual-mapsreadmemd)
14. [File Template — `04-Final-Project/README.md`](#14-file-template--04-final-projectreadmemd)
15. [Adapting to Non-Technical Subjects](#15-adapting-to-non-technical-subjects)
16. [Progress Update Protocol](#16-progress-update-protocol)
17. [Repository Creation Checklist](#17-repository-creation-checklist)
18. [Ready-to-Paste AI Prompt (Generate a New Repo)](#18-ready-to-paste-ai-prompt-generate-a-new-repo)
19. [Template Sync Rule (Keep This File a Mirror)](#19-template-sync-rule-keep-this-file-a-mirror)

---

## 1. How to Use This Template

1. Create a new empty folder/repository for the subject you want to study.
2. Copy this `template.md` into it.
3. Fill in every placeholder in [Section 2](#2-placeholders-fill-these-first).
4. Research the subject using the rules in [Section 4](#4-source-and-freshness-rules-mandatory).
   Pick the **latest stable version** and the **official sources** before writing anything.
5. Design the curriculum using the sizing rules in [Section 5](#5-sizing-rules-how-many-lectures-questions-milestones).
6. Generate the scaffold exactly as described in [Section 6](#6-repository-structure)
   using the file templates in Sections 8–14.
7. Run the [Repository Creation Checklist](#16-repository-creation-checklist).
8. Start studying from Lecture 01. Never skip the track order.

Shortcut: give an AI assistant the prompt in [Section 17](#17-ready-to-paste-ai-prompt-generate-a-new-repo)
together with this file, and it will generate the full scaffold for you.

### What gets generated vs. what the learner writes

| Created by the scaffold (AI or you, once) | Written by the learner (during study, by hand) |
|:---|:---|
| Root `README.md` | The content of every `code-N.<ext>` / `practice-N.md` file |
| `01-Lectures/README.md` (full curriculum + rules) | The blanks of every `review-N.md` stub |
| Lecture folders with empty `code-1`…`code-6` stubs and a `review-7.md` stub (see [Section 10.4](#104-lecture-scaffold-stubs)) | Every `Milestone/` solution |
| `02-Interview-Questions/README.md` | Every question's `code-N.<ext>` and `notes.md` |
| One `README.md` inside every question folder | All final-project source files, tests, `notes.md` |
| `03-Visual-Maps/README.md` + each map's `README.md` + empty `map.md` | Filled `map.md` diagrams and optional `notes.md` |
| `04-Final-Project/README.md` | Progress check marks (✅) after passing each CHECK |

> **Golden rule:** the guides teach; the learner writes. The tutor/AI shows examples in chat
> and never writes the learner's practice files.

---

## 2. Placeholders (Fill These First)

Replace every `{{PLACEHOLDER}}` in the file templates below with real values.

Placeholder conventions:

- **`{{UPPER_SNAKE_CASE}}`** — global values defined once in the table below and reused everywhere.
- **`{{lower case / Mixed Case}}`** — free-text slots filled per item
  (for example `{{slug}}`, `{{Topic}}`, `{{Title}}`, `{{url}}`, `{{concept}}`, `{{one-line description}}`).
- **`<!-- HTML comments -->`** inside templates are instructions for the author. Replace or delete them.
- **`NN`** means a two-digit number (`01`, `15`); **`N`** means a plain number (`1`, `7`).
- Expressions such as `{{LECTURE_COUNT - 1}}` or `{{N+1}}` mean "write the calculated number".

After generating a repo, a search for `{{` outside `template.md` must return no results (see [Section 16](#16-repository-creation-checklist)).

| Placeholder | Meaning | Example (from the PHP OOP repo) |
|:---|:---|:---|
| `{{SUBJECT}}` | Full subject name | `PHP OOP` |
| `{{SUBJECT_SLUG}}` | kebab-case slug used in skill names | `php-oop` |
| `{{SUBJECT_FULL_TITLE}}` | Long title for the README header | `Object-Oriented Programming in PHP` |
| `{{SUBJECT_VERSION}}` | Latest stable version targeted | `PHP 8.5+` |
| `{{SUBJECT_EMOJI}}` | One emoji representing the subject | `🐘` |
| `{{LANGUAGE_OR_TOOL}}` | Language/tool used for practice files | `PHP` |
| `{{FILE_EXT}}` | Extension of practice files | `php` (for non-technical subjects use `md` and name files `practice-N.md`, see [Section 14](#14-adapting-to-non-technical-subjects)) |
| `{{RUN_COMMAND}}` | How the learner runs a practice file | `php code-1.php` |
| `{{TEST_TOOL}}` | Testing tool, if any | `PHPUnit` |
| `{{PRIMARY_SOURCE_NAME}}` | Name of the main official source | `PHP Manual` |
| `{{PRIMARY_SOURCE_URL}}` | Root URL of the main official source | `https://www.php.net/manual/en/` |
| `{{SECONDARY_SOURCES}}` | Other official sources (tools, specs, standards) | `PHPUnit Docs, PSR-4 (php-fig.org)` |
| `{{LEARNER_PROFILE}}` | Who the learner is and what they already know | `No CS background, knows basic PHP` |
| `{{PREREQUISITES}}` | Exact prior knowledge required | `variables, functions, arrays, loops` |
| `{{LECTURE_COUNT}}` | Total lectures | `31` |
| `{{PART_COUNT}}` | Number of parts | `3` |
| `{{PART_1_NAME}}`, `{{PART_2_NAME}}`, `{{PART_3_NAME}}`, `{{PART_4_NAME}}` | Name of each part (Title-Case, hyphenated). Templates show 3 parts; add or remove part blocks to match `{{PART_COUNT}}` | `Foundations`, `Core-OOP`, `Modern-PHP` |
| `{{MILESTONE_LECTURES}}` | Lecture numbers that are milestones | `05, 15, 24, 31` |
| `{{M1}}`, `{{M2}}`, `{{M3}}` | The first three milestone lecture numbers (the 4th is always the last lecture) | `05`, `15`, `24` |
| `{{SUBJECT_URL_ENCODED}}` / `{{SUBJECT_VERSION_URL_ENCODED}}` | Values encoded for shields.io badges: space → `%20`, `+` → `%2B`, `/` → `%2F`, `-` → `--`. The version badge uses the **version number only**, because the badge label already shows `{{LANGUAGE_OR_TOOL}}` | `PHP%20OOP` / `8.5%2B` |
| `{{SPACED UPPERCASE SUBJECT}}` | Subject in spaced capitals for the ASCII banner | `P H P   O O P` |
| `{{QUESTION_COUNT}}` | Total interview questions | `42` |
| `{{MAP_COUNT}}` | Total visual maps (about 0.3–0.5 × lecture count) | `12` |
| `{{PROJECT_NAME}}` | Final project name | `SupportDesk Lite` |
| `{{PROJECT_MILESTONE_COUNT}}` | Final project milestones (from 00) | `15` (00–14) |
| `{{OUT_OF_SCOPE}}` | Topics explicitly excluded (they belong to another repo) | `Design patterns, SOLID` |
| `{{LAST_VERIFIED_DATE}}` | Date sources were last checked (YYYY-MM-DD) | `2026-10-15` |
| `{{PREVIOUS_REPO}}` / `{{PREVIOUS_REPO_URL}}` | The study repo that comes **before** this one in the series, or `None` | `PHP Fundamentals` / `https://github.com/...` |
| `{{NEXT_REPO}}` / `{{NEXT_REPO_URL}}` | The study repo that comes **after** this one in the series, or `None` | `OOD` / `https://github.com/...` |

---

## 3. Core Principles of the Method

These principles are copied into every repository and never change between subjects.

1. **Four tracks, strict order:** Lectures → Interview Questions → Visual Maps → Final Project.
   A track starts only after the previous track's Review Checklist is fully checked.
2. **One unit per session:** one lecture, one question, one visual map, or one project milestone per session,
   unless the learner explicitly asks to continue.
3. **Iterative cycle (PLAN → DO → CHECK → ACT)** runs for every unit.
4. **3-Phase Lecture Method:** Before (scope and skim) → During (analogy first, then examples) → After (study card).
5. **Maximum 2 new concepts per lecture.** A third concept moves to the next lecture.
6. **Analogy before code.** Every concept starts with a real-world analogy.
7. **Every line of every example is annotated.** Zero uncommented lines.
8. **The learner writes everything by hand.** The tutor only shows, explains, reviews, and debugs.
9. **Official sources only, latest stable version** (see [Section 4](#4-source-and-freshness-rules-mandatory)).
   Every review card, question, visual map, and project ends with its source.
10. **Milestones** check real understanding at fixed points (about 1/6, 1/2, 3/4, and the end of the lectures).
11. **No progress without proof:** a ✅ is added only after the learner passes the CHECK task.
12. **Plain language:** every technical term gets a one-line plain-language definition on first use.
13. **Strict scope:** each repo covers one subject. Neighboring subjects get a one-sentence answer and a redirect.
14. **20/80 focus:** teach the 20% of concepts that deliver 80% of real-world use first.
    Rare and edge-case features come late or are left out.
15. **Series without overlap:** every repo is one link in a learning series
    (`{{PREVIOUS_REPO}}` → this repo → `{{NEXT_REPO}}`). A lecture taught in another repo of the series
    is never taught again. This repo starts exactly where `{{PREVIOUS_REPO}}` stops and teaches everything
    `{{NEXT_REPO}}` assumes. Topics owned by a neighbor go into `{{OUT_OF_SCOPE}}` with a pointer to the
    matching lecture there.
16. **Living repo:** the repo always follows the latest stable version of `{{SUBJECT}}`. When a new version
    is released, the same repo is updated (never forked into a new one) using the procedure in
    [Section 4.4](#44-version-update-procedure-living-repo).

---

## 4. Source and Freshness Rules (Mandatory)

All content must be accurate, current, and traceable.

### 4.1 Source priority (use the highest available)

1. **Official documentation / manual** of the language, framework, or tool
   (for example `php.net/manual`, `docs.python.org`, `laravel.com/docs`, `react.dev`, `docs.docker.com`).
2. **Official specifications and standards** (RFCs, PSRs, ECMAScript spec, W3C, ISO, IETF).
3. **Official release notes / changelogs / migration guides** for version-specific features.
4. **Canonical books or the original authors** when no official docs exist
   (for example *Design Patterns* by the Gang of Four, *Refactoring* by Martin Fowler, refactoring.guru as a secondary reference).
5. **Recognized institutions** for non-technical subjects (universities, standards bodies, official exam boards, government bodies).

Not allowed as the only source: random blog posts, unverified tutorials, AI-generated answers, outdated Q&A threads.

### 4.2 Freshness rules

- Always target the **latest stable version** at the time the repo is created. Record it in `{{SUBJECT_VERSION}}`.
- Before writing a lecture outline, **verify** that every feature still exists and is not deprecated
  in the targeted version (check release notes and migration guides).
- Mark version-specific features in titles, for example `Property Hooks (PHP 8.4)`.
- Prefer modern idioms over legacy ones. When a legacy approach is still common in real code, show it once, label it as legacy, then show the modern way.
- Record `Last verified: {{LAST_VERIFIED_DATE}}` in the root README under Official Sources.
- When a new version is released, update the repo with the procedure in [Section 4.4](#44-version-update-procedure-living-repo).

### 4.3 Citation rules

| Location | Required format | Position |
|:---|:---|:---|
| Lecture outline (in `01-Lectures/README.md`) | `**{{PRIMARY_SOURCE_NAME}} Reference:** <url>` | Last line of each lecture outline |
| `review-N.md` | `## Official reference` + `[Source — Short Label](url)` | **Always the last section** |
| Question folder `README.md` | `Source: <url>` or `Sources: <url>, <url>` | **Always the last line** |
| `02-Interview-Questions/README.md` | Question Source Map block | Dedicated section |
| `03-Visual-Maps/` map folder `README.md` | `Source:` / `Sources:` | **Always the last line** |
| `04-Final-Project/README.md` | `## Source References` list | Last section |
| Root `README.md` | `## 🔗 Official Sources` table | Before the footer |

- Use deep links to the exact page or section, not only the homepage.
- One URL per concept is enough. Use `Sources:` (plural) when a question depends on more than one page.

### 4.4 Version update procedure (living repo)

Run this every time a new stable version of `{{SUBJECT}}` is released. The repo is updated in place.

1. Read the official release notes and migration guide: new features, deprecated features,
   backward-incompatible changes, and new functions.
2. Add each relevant new feature to the outline of the lecture where it fits, marked with its version,
   for example `(PHP 8.6)`. Add a new lecture only when a feature is a whole new concept that fits no
   existing lecture; then update every count, folder, and link (Section 16, Consistency).
3. Replace deprecated features with their modern alternative, or keep them once labeled as deprecated.
   Apply the same change to interview questions and the final project.
4. Features owned by `{{PREVIOUS_REPO}}` or `{{NEXT_REPO}}` go to that repo, not this one (principle 15).
5. Completed lectures keep their ✅. New items in a completed lecture become a short catch-up session,
   listed under Current Focus in the root README until the learner reviews them.
6. Update `{{SUBJECT_VERSION}}` everywhere (badges, titles, Requirements, Official Sources),
   update the `Last verified` date, and add a row to the Version History table in the root README.

---

## 5. Sizing Rules (How Many Lectures, Questions, Milestones)

Scale the repository to the subject. These are the default rules.

| Subject size | Example | Lectures | Parts | Questions | Visual maps | Project milestones |
|:---|:---|:---:|:---:|:---:|:---:|:---:|
| Small | Git basics, Regex | 10–15 | 2 | 15–20 | 4–8 | 6–8 |
| Medium | Docker, SQL, Design Patterns | 16–25 | 3 | 25–35 | 6–12 | 10–12 |
| Large | PHP OOP, Laravel, React | 26–35 | 3–4 | 35–50 | 10–15 | 12–15 |

Rules:

- **Parts:** group lectures into 2–4 parts that move from basics to advanced
  (for example `Foundations` → `Core` → `Advanced/Modern`). Parts should be roughly equal in size
  (about 5–12 lectures each) and each part should end at a natural checkpoint.
- **Milestones in lectures:** 4 milestones placed at about **1/6**, **1/2**, **3/4**, and the **last lecture**
  (PHP OOP: 05, 15, 24, 31 of 31).
- **Lecture 01** always explains **the problem** the subject solves, before any solution.
- **The second-to-last lecture** is always a **mini-project** that combines everything learned.
- **The last lecture** is always a **milestone** focused on verification (testing, assessment, or real practice).
- **Interview questions:** about **1.3–1.5 × the lecture count**. Every lecture maps to at least one question.
- **Visual maps:** about **0.3–0.5 × the lecture count**. The last map is always an end-to-end system map.
- **Final project milestones:** start at `Milestone 00 - Project Setup` and end with `Final Review`.
  Each project milestone covers 2–4 lectures, so together they cover every lecture.

---

## 6. Repository Structure

````
📦 {{SUBJECT_SLUG}}/
│
├── README.md                                   ← Repo overview · progress dashboard · start here
├── template.md                                 ← This file (keep it: Sections 15 and 17 are used while studying)
├── .gitignore                                  ← Only if the subject installs dependencies
├── .cursor/rules/template-sync.mdc             ← Enforces Section 19 automatically (always applied)
│
├── 01-Lectures/                                ← Track 1 · guide + workspace
│   ├── README.md                               ← Tutor skill: curriculum, method, rules, outlines
│   ├── Part-1-{{PART_1_NAME}}/                 ← Lectures 01–NN
│   │   ├── Lecture-01-{{topic-slug}}/
│   │   │   ├── code-1.{{FILE_EXT}}             ← 1st example of the lecture (learner-written)
│   │   │   ├── code-2.{{FILE_EXT}}             ← 2nd example, in the order shown
│   │   │   ├── code-N.{{FILE_EXT}}             ← ...
│   │   │   └── review-{{N+1}}.md                ← Study card (always the highest number = last)
│   │   ├── Lecture-05-Milestone-{{topic-slug}}/
│   │   │   ├── code-1.{{FILE_EXT}} ...
│   │   │   ├── review-N.md
│   │   │   └── Milestone/                      ← Learner's milestone solution
│   │   │       └── {{SolutionFile}}.{{FILE_EXT}}
│   │   └── ...
│   ├── Part-2-{{PART_2_NAME}}/
│   │   └── ...
│   └── Part-3-{{PART_3_NAME}}/
│       └── ...
│
├── 02-Interview-Questions/                     ← Track 2 · guide + workspace
│   ├── README.md                               ← Interview skill: questions, sources, rules
│   ├── Question-01-{{question-slug}}/
│   │   ├── README.md                           ← Scaffolded (the only pre-created file)
│   │   ├── code-1.{{FILE_EXT}}                 ← Learner-created only if needed
│   │   ├── code-2.{{FILE_EXT}}                 ← Learner-created improved version
│   │   └── notes.md                            ← Learner's final interview answer
│   └── ...
│
├── 03-Visual-Maps/                             ← Track 3 · guide + workspace
│   ├── README.md                               ← Visual skill: map list, standards, rules
│   ├── Map-01-{{map-slug}}/
│   │   ├── README.md                           ← Scaffolded prompt + CHECK + Source
│   │   ├── map.md                              ← Mermaid stub (learner fills)
│   │   └── notes.md                            ← Optional learner reflection
│   └── ...
│
└── 04-Final-Project/                           ← Track 4 · guide + workspace
    ├── README.md                               ← Project guide: scenario, milestones, rules
    ├── src/                                    ← Learner-created gradually
    ├── tests/                                  ← Learner-created gradually
    ├── playground.{{FILE_EXT}}                 ← Manual runner (learner-created)
    └── notes.md                                ← Design decisions + final reflection
````

What exists **at scaffold time** (before studying starts):

- `README.md` (root), `01-Lectures/README.md`, `02-Interview-Questions/README.md`, `03-Visual-Maps/README.md`, `04-Final-Project/README.md`.
- Every `Part-N-*/Lecture-NN-*/` folder, each containing empty `code-1` … `code-6` files and a
  `review-7.md` stub as described in [Section 10.4](#104-lecture-scaffold-stubs).
- Every `Question-NN-*/README.md`.
- Every `Map-NN-*/README.md` plus empty `map.md` stub.
- `.cursor/rules/template-sync.mdc` — copied as-is from [Section 19](#19-template-sync-rule-keep-this-file-a-mirror).
- `.gitignore` only when the subject uses a package manager or produces build output.
  List the dependency and build folders only (for example `vendor/`, `node_modules/`, `__pycache__/`, `.venv/`, `bin/`, `obj/`)
  plus local secrets (`.env`). Never ignore learner files.

Everything else is created by the learner during study.

If the subject needs more than 3 parts, add `Part-4-{{PART_4_NAME}}/` and an extra part block wherever the
templates list parts (root README progress, Track 1 table, curriculum, folder structure). If it needs only 2, remove Part 3.

---

## 7. Naming Conventions

| Item | Pattern | Example |
|:---|:---|:---|
| Track folder | `NN-Title-Case-Name/` (numeric prefix keeps GitHub order) | `01-Lectures/` |
| Part folder | `Part-N-Title-Case-Name/` | `Part-2-Core-OOP/` |
| Lecture folder | `Lecture-NN-kebab-topic/` (two-digit number) | `Lecture-07-encapsulation/` |
| Milestone lecture folder | `Lecture-NN-Milestone-kebab-topic/` | `Lecture-15-Milestone-polymorphism/` |
| Example file | `code-N.{{FILE_EXT}}` numbered in the order shown | `code-3.php` |
| Study card | `review-N.md` — **lowercase**, N = last code number + 1 | `review-7.md` after `code-6.php` |
| Milestone solution | `Milestone/<RealName>.{{FILE_EXT}}` | `Milestone/Product.php` |
| Question folder | `Question-NN-kebab-question-summary/` | `Question-22-abstract-class-vs-interface/` |
| Question notes | `notes.md` | — |
| Project milestones | `Milestone NN - Title` (starting at `00`) | `Milestone 03 - Enums and Safe State` |

Rules:

- Slugs are short (2–5 words), lowercase, kebab-case, and describe the concept, not the lecture title.
- **Include rule:** when one example loads another file (`require`, `import`, `include`, `source`),
  reference it by its `code-N` filename, never by the class/module name
  (correct: `require 'code-1.php';` — wrong: `require 'Car.php';`).
- Code naming inside examples follows the official style guide of the language
  (for example PSR-12 for PHP, PEP 8 for Python).

---

## 8. File Template — Root `README.md`

The root README is the **visual dashboard**: purpose, progress, learning path, and links into every track.
It is the only file that uses decorative emojis and ASCII boxes. Other files use only the progress marks (✅, ⬜).

### Required sections (in this exact order)

1. Centered header: title, subtitle, badges, ASCII banner, one-line purpose, quick links.
2. 📑 Table of Contents.
3. 📊 My Progress — overall status table, lecture progress grid, progress bar, current focus, per-part tables (collapsible), milestones table, sync note.
4. 🎯 Purpose.
5. 👤 Who This Is For.
6. 🗺️ Learning Path.
7. 📚 Track 1 — Lectures.
8. 💼 Track 2 — Interview Questions.
9. 🗺️ Track 3 — Visual Maps.
10. 🏗️ Track 4 — Final Project.
10. 🚀 How to Start.
11. 📁 Repository Structure.
12. ⚙️ Requirements.
13. 🔄 Staying Current — living-repo rule and Version History table.
14. 🔗 Official Sources (with `Last verified` date).
15. Centered footer.

### Template

````markdown
<div align="center">

# 📘 {{SUBJECT}} Documentation

### *Your Complete Guide to {{SUBJECT_FULL_TITLE}}*

<br/>

![Version](https://img.shields.io/badge/{{LANGUAGE_OR_TOOL}}-{{SUBJECT_VERSION_URL_ENCODED}}-2563EB?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-{{SUBJECT_URL_ENCODED}}-2563EB?style=for-the-badge)
![Source](https://img.shields.io/badge/Source-Official%20Docs-059669?style=for-the-badge)
![Tracks](https://img.shields.io/badge/Tracks-4-D97706?style=for-the-badge)
![Progress](https://img.shields.io/badge/Lectures-0%2F{{LECTURE_COUNT}}%20Done-2563EB?style=for-the-badge)
![Current](https://img.shields.io/badge/Current-Lecture%2001-F59E0B?style=for-the-badge)

<br/>

```
╔══════════════════════════════════════════════════════════════════════╗
║                                                                      ║
║     {{SUBJECT_EMOJI}}  {{SPACED UPPERCASE SUBJECT}}   D O C U M E N T A T I O N  📖      ║
║                                                                      ║
║   Lectures ──▶ Interviews ──▶ Visual Maps ──▶ Final Project      ║
║                                                                      ║
╚══════════════════════════════════════════════════════════════════════╝
```

<br/>

> 🎯 **This repo is for those who want to study everything related to {{SUBJECT}}**
> with **{{SUBJECT_VERSION}}**. All lectures follow the
> [**official {{PRIMARY_SOURCE_NAME}}**]({{PRIMARY_SOURCE_URL}}),
> with interview questions and a final project to master it all.

<br/>

[📊 My Progress](#-my-progress) · [🚀 Get Started](#-how-to-start) · [📚 Lectures](#-track-1--lectures) · [💼 Interviews](#-track-2--interview-questions) · [🗺️ Visual Maps](#-track-3--visual-maps) · [🏗️ Project](#-track-4--final-project)

</div>

---

## 📑 Table of Contents

| | Section | What’s inside |
|:---:|:---|:---|
| 📊 | [My Progress](#-my-progress) | Status, lecture list, milestones |
| 🎯 | [Purpose](#-purpose) | Why this book exists |
| 👤 | [Who This Is For](#-who-this-is-for) | Is this for you? |
| 🗺️ | [Learning Path](#-learning-path) | Lectures → Interviews → Visual Maps → Project |
| 📚 | [Track 1 — Lectures](#-track-1--lectures) | {{LECTURE_COUNT}} sessions in {{PART_COUNT}} parts |
| 💼 | [Track 2 — Interviews](#-track-2--interview-questions) | {{QUESTION_COUNT}} questions |
| 🗺️ | [Track 3 — Visual Maps](#-track-3--visual-maps) | {{MAP_COUNT}} diagrams |
| 🏗️ | [Track 4 — Final Project](#-track-4--final-project) | {{PROJECT_NAME}} |
| 🚀 | [How to Start](#-how-to-start) | Your first step |
| 📁 | [Repository Structure](#-repository-structure) | Folder map |
| ⚙️ | [Requirements](#-requirements) | What you need |
| 🔄 | [Staying Current](#-staying-current) | Always on the latest version |
| 🔗 | [Official Sources](#-official-sources) | Trusted references |

---

## 📊 My Progress

### 🗓️ Overall Status

| Track | Progress | Status |
|:---|:---:|:---|
| 📚 **Lectures** | **0 / {{LECTURE_COUNT}}** | 🟡 In Progress — *Lecture 01 next* |
| 💼 **Interview Questions** | **0 / {{QUESTION_COUNT}}** | 🔒 Locked — *starts after Lecture {{LECTURE_COUNT}}* |
| 🗺️ **Visual Maps** | **0 / {{MAP_COUNT}}** | 🔒 Locked — *starts after interviews* |
| 🏗️ **Final Project** | **0 / {{PROJECT_MILESTONE_COUNT}} milestones** | 🔒 Locked — *starts after visual maps* |

<div align="center">

**Lecture Progress**

<table align="center">
<tr>
<!-- one <td align="center">⬜</td> per lecture; switch to ✅ when done -->
</tr>
<tr>
<!-- one <td align="center"><sub>N</sub></td> per lecture -->
</tr>
</table>

**[░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░] 0%**

</div>

> 🎯 **Current focus:** [Lecture 01 — {{Lecture 01 Title}}](01-Lectures/Part-1-{{PART_1_NAME}}/Lecture-01-{{slug}}/)
> 🏁 **Last completed:** —
> 🏅 **Milestone 1** *(after Lecture {{M1}})* — ⬜ Not yet

### 📚 Lecture Progress

<details open>
<summary><strong>📗 Part 1 — {{PART_1_NAME}}</strong> &nbsp;·&nbsp; Lectures 01–NN &nbsp;·&nbsp; <code>Part-1-{{PART_1_NAME}}/</code></summary>

| # | Folder | Topic | Status |
|:---:|:---|:---|:---:|
| 01 | [`{{slug}}`](01-Lectures/Part-1-{{PART_1_NAME}}/Lecture-01-{{slug}}/) | {{Topic}} | 🟡 **Next** |
| 02 | [`{{slug}}`](01-Lectures/Part-1-{{PART_1_NAME}}/Lecture-02-{{slug}}/) | {{Topic}} | ⬜ |

</details>

<!-- Repeat one <details> block per part. Only the part containing the current lecture has `open`. -->

### 🏅 Milestones

| Milestone | After Lecture | Status |
|:---|:---:|:---:|
| 🥉 Milestone 1 — {{Name}} | {{M1}} | ⬜ Not yet |
| 🥈 Milestone 2 — {{Name}} | {{M2}} | ⬜ Not yet |
| 🥇 Milestone 3 — {{Name}} | {{M3}} | ⬜ Not yet |
| 🏆 Milestone 4 — Full Track Complete | {{LECTURE_COUNT}} | ⬜ Not yet |

> 📝 *Progress is synced from [`01-Lectures/README.md`](01-Lectures/README.md). Update both files when a lecture is completed.*

---

## 🎯 Purpose

<!-- 1 short paragraph: why this subject matters in the real world. -->

### 📖 This book gives you one complete, structured path:

- 🧩 **Learn every core concept** of {{SUBJECT}} using {{SUBJECT_VERSION}}
- 📜 **Study from official sources** — grounded in {{PRIMARY_SOURCE_NAME}}, not random blog posts
- 💬 **Practice interview questions** — explain what you know with confidence
- 🗺️ **Draw visual maps** — flows, sequences, and one end-to-end system diagram (Mermaid)
- 🏆 **Build a real capstone project** — prove mastery from scratch

> 🚫 **No shortcuts.** ✅ **Just {{SUBJECT}} and real skill.**

---

## 👤 Who This Is For

| 🧑‍💻 You are… | 📈 This book helps you… |
|:---|:---|
| 🌱 A beginner<br/><sub>{{PREREQUISITES}}</sub> | {{benefit}} |
| 🔍 A self-taught learner | Fill gaps with a clear, ordered curriculum |
| 🎤 Preparing for interviews | Practice {{QUESTION_COUNT}} focused questions |
| 📜 A learner who wants official sources | Follow lectures tied directly to {{PRIMARY_SOURCE_NAME}} |

---

## 🗺️ Learning Path

```
   📚 TRACK 1    💼 TRACK 2    🗺️ TRACK 3    🏗️ TRACK 4
   Lectures  ──▶ Interviews ──▶ Visual Maps ──▶ Final Project
   {{LECTURE_COUNT}} sessions   {{QUESTION_COUNT}} questions   {{MAP_COUNT}} diagrams     {{PROJECT_NAME}}
   Learn         Explain        See the system  Build
                                   │
                                   ▼
                       🏅 {{SUBJECT}} Mastery Achieved
```

> ⚠️ **Complete the tracks in order.** Each track builds on the previous one.

### 🔗 Series — no repeated lessons

| Order | Repository | Covers |
|:---:|:---|:---|
| **N-1** | [{{PREVIOUS_REPO}}]({{PREVIOUS_REPO_URL}}) | {{what it covers}} |
| **N** | **{{SUBJECT}}** *(this repo)* | {{what this repo covers}} |
| **N+1** | [{{NEXT_REPO}}]({{NEXT_REPO_URL}}) | {{what it covers}} |

<!-- Drop the previous or next row when it is None. -->

> 🧭 Each repo continues where the previous one stops. A topic taught in one repo is **never** re-taught in another.

---

## 📚 Track 1 — Lectures

| | |
|:---|:---|
| 📂 **Track folder** | [`01-Lectures/`](01-Lectures/) — guide + workspace |
| 🔢 **Sessions** | **{{LECTURE_COUNT}} lectures** — one concept per session |
| 🗂️ **Structure** | {{PART_COUNT}} parts: {{PART_1_NAME}} → {{PART_2_NAME}} → {{PART_3_NAME}} |
| 📜 **Source** | Official [{{PRIMARY_SOURCE_NAME}}]({{PRIMARY_SOURCE_URL}}) |

**How lectures are organized:**

```
Part-1-{{PART_1_NAME}}/   →  Lectures 01–NN
Part-2-{{PART_2_NAME}}/   →  Lectures NN–NN
Part-3-{{PART_3_NAME}}/   →  Lectures NN–{{LECTURE_COUNT}}
```

**What you will learn:**

```
<!-- 6–8 short topic highlights, two per line, each with an emoji -->
```

> 📊 **My current progress:** **0 / {{LECTURE_COUNT}}** lectures done — next is [Lecture 01 — {{Lecture 01 Title}}](01-Lectures/Part-1-{{PART_1_NAME}}/Lecture-01-{{slug}}/).

---

## 💼 Track 2 — Interview Questions

| | |
|:---|:---|
| 📂 **Track folder** | [`02-Interview-Questions/`](02-Interview-Questions/) — guide + workspace |
| 🔢 **Questions** | **{{QUESTION_COUNT}} questions** — realistic & practice-based |
| 🔗 **Linked to** | Every question maps back to a lecture |

**What interviewers test:**

```
<!-- 8–10 sample questions, two per line, each starting with ❓ -->
```

> 💡 Start this track **only after** completing all {{LECTURE_COUNT}} lectures.

| Progress | Status |
|:---:|:---|
| **0 / {{QUESTION_COUNT}}** | 🔒 Not started yet |

---

## 🗺️ Track 3 — Visual Maps

| | |
|:---|:---|
| 📂 **Track folder** | [`03-Visual-Maps/`](03-Visual-Maps/) — guide + workspace |
| 🔢 **Maps** | **{{MAP_COUNT}} diagrams** — Mermaid-first, one idea each |
| 🎯 **Goal** | See the subject as flows, sequences, and one system map before building |

> 💡 Start this track **only after** completing all {{QUESTION_COUNT}} interview questions.

| Progress | Status |
|:---:|:---|
| **0 / {{MAP_COUNT}}** | 🔒 Not started yet |

---

## 🏗️ Track 4 — Final Project

| | |
|:---|:---|
| 📂 **Track folder** | [`04-Final-Project/`](04-Final-Project/) — guide + workspace |
| 🎯 **Project** | **{{PROJECT_NAME}}** — {{one-line description}} |
| 🛠️ **Stack** | {{stack and constraints}} |

**What you will build:**

```
<!-- 5–8 feature bullets with emojis -->
```

> 🏅 This is your **final proof** — not a lecture replacement.

| Progress | Status |
|:---:|:---|
| **0 / {{PROJECT_MILESTONE_COUNT}} milestones** | 🔒 Not started yet |

---

## 🚀 How to Start

| Step | Action | Where |
|:---:|:---|:---|
| **1️⃣** | 📖 Open the lecture guide and start **Lecture 01** | [`01-Lectures/`](01-Lectures/) |
| **2️⃣** | ✍️ Type each example into that lecture’s `code-N.{{FILE_EXT}}` files — one session at a time | Lecture folder |
| **3️⃣** | 💼 After all lectures, practice interview answers | [`02-Interview-Questions/`](02-Interview-Questions/) |
| **4️⃣** | 🗺️ Draw the flows and the system map | [`03-Visual-Maps/`](03-Visual-Maps/) |
| **5️⃣** | 🏗️ Build the capstone when visual maps are done | [`04-Final-Project/`](04-Final-Project/) |
| **5️⃣** | ➡️ Continue the series with [{{NEXT_REPO}}]({{NEXT_REPO_URL}}) | Next repository |

<!-- Drop step 5 when {{NEXT_REPO}} is None. -->

> ✍️ **Remember:** You write all the code. The guides teach; your practice files live inside each lecture folder.

---

## 📁 Repository Structure

```
<!-- Paste the tree from Section 6, with real folder names and a "🟡 you are here" marker -->
```

---

## ⚙️ Requirements

- {{SUBJECT_EMOJI}} **{{SUBJECT_VERSION}}**
- 📖 {{PREREQUISITES}}
- 💻 {{local environment needed}}
- 📦 {{TEST_TOOL}} and {{other tools}} <sub>(introduced later)</sub>

---

## 🔄 Staying Current

> ♻️ **This is a living repo.** It always follows the latest stable {{SUBJECT}} release.
> When a new version comes out, this same repo is updated: new features are added to the matching lectures,
> deprecated features are replaced, and completed lectures get a short catch-up session.
> The full procedure is in `template.md` Section 4.4.

| Version | Updated on | What changed in this repo |
|:---|:---|:---|
| {{SUBJECT_VERSION}} | {{LAST_VERIFIED_DATE}} | Initial curriculum |

---

## 🔗 Official Sources

> 📜 All lecture and interview content is built on **trusted, official documentation.**

| Source | Link |
|:---|:---|
| {{SUBJECT_EMOJI}} {{PRIMARY_SOURCE_NAME}} | [{{short url}}]({{PRIMARY_SOURCE_URL}}) |
| 📖 {{Secondary source}} | [{{short url}}]({{url}}) |

<!-- Add one row per entry in {{SECONDARY_SOURCES}}. -->

> 🗓️ **Last verified:** {{LAST_VERIFIED_DATE}} against {{SUBJECT_VERSION}}.

---

<div align="center">

```
╔══════════════════════════════════════════════════════════════╗
║   📘  Read.  ✍️  Write.  💬  Explain.  🏗️  Build.  🏅  Master.  ║
╚══════════════════════════════════════════════════════════════╝
```

*Documentation provided for learning purposes.*
*Refer to the official {{PRIMARY_SOURCE_NAME}} for authoritative behavior.*

**{{SUBJECT_EMOJI}} Happy Learning!**

</div>
````

---

## 9. File Template — `01-Lectures/README.md`

This file is the **tutor skill** for the lecture track. It is written so that an AI tutor (or a human)
can teach the whole curriculum from it alone. It starts with YAML front matter.

### Required sections (in this exact order)

1. YAML front matter (`name`, `purpose`, `scope`, `description`, `triggers`).
2. `# {{SUBJECT}} ({{SUBJECT_VERSION}}) - Iterative Tutor Skill`
3. `## Who This Is For`
4. `## Curriculum ({{LECTURE_COUNT}} Lectures, One Per Session)` — with ✅ markers.
5. `## Lecture Track Review Checklist`
6. `## The Iterative Cycle (Run Once Per Lecture)` — PLAN / DO / CHECK / ACT.
7. `## The 3-Phase Lecture Method` — including the `review-N.md` study-card format.
8. `## Analogy Bank` — one analogy per lecture.
9. `## Language Rules` — including the glossary of plain-language definitions.
10. `## Code Standards`
11. `## Tutor Role: Show Code — Student Writes Code (Mandatory)`
12. `## File and Folder Conventions for This Course`
13. `## Lecture Content Outline` — one block per lecture.
14. `## Session Flow (Follow This Order Every Time)`
15. `## Milestone Checks`
16. `## Skip Ahead Policy`
17. `## What Not To Do`

### Template

````markdown
---
name: {{SUBJECT_SLUG}}-tutor
purpose: >
  This file has exactly one purpose: to serve as the single learning source for
  studying everything related to {{SUBJECT}} ({{SUBJECT_VERSION}}).
scope: >
  This file should only contain guidance, curriculum, rules, examples, and
  progress notes that directly support learning {{SUBJECT}} ({{SUBJECT_VERSION}}).
description: >
  Structured, iterative tutoring skill for teaching {{SUBJECT}} (targeting
  {{SUBJECT_VERSION}}) to {{LEARNER_PROFILE}}. Trigger this skill whenever the
  user wants to learn {{SUBJECT}}, says "next lecture", "continue {{SUBJECT}}
  course", or asks anything about {{SUBJECT}} at a beginner level.
triggers:
  - user wants to learn {{SUBJECT}}
  - user says "teach me {{SUBJECT}}"
  - user says "next lecture" or "continue {{SUBJECT}} course"
  - user asks what {{core concept 1}}, {{core concept 2}}, or {{core concept 3}} is
  - user mentions {{SUBJECT}} at beginner or intermediate level
---

# {{SUBJECT}} ({{SUBJECT_VERSION}}) - Iterative Tutor Skill

## Who This Is For

Student profile: {{LEARNER_PROFILE}}. Knows {{PREREQUISITES}}. Assumes nothing beyond that.

**Series position:**

- **Comes after:** [{{PREVIOUS_REPO}}]({{PREVIOUS_REPO_URL}}) (or "nothing — this is the starting point").
- **Leads to:** [{{NEXT_REPO}}]({{NEXT_REPO_URL}}), which assumes exactly what this repo teaches.
- **No-overlap rule:** every topic taught in a neighboring repo is excluded here (see "What Not To Do"). When a lecture touches one of those topics, give one sentence and point to the matching lecture there.

---

## Curriculum ({{LECTURE_COUNT}} Lectures, One Per Session)

Deliver exactly one lecture per session unless the student explicitly requests to continue.

```
Part 1 — {{PART_1_NAME}} (Lectures 1–NN)  →  Part-1-{{PART_1_NAME}}/
Lecture 1  - {{slug}}                            {{Full lecture title}}
Lecture 2  - {{slug}}                            {{Full lecture title}}
Lecture 5  - Milestone-{{slug}}                  {{Full lecture title}}
...

Part 2 — {{PART_2_NAME}} (Lectures NN–NN)  →  Part-2-{{PART_2_NAME}}/
...

Part 3 — {{PART_3_NAME}} (Lectures NN–{{LECTURE_COUNT}})  →  Part-3-{{PART_3_NAME}}/
...
Lecture {{LECTURE_COUNT - 1}} - mini-project-{{slug}}     Build a {{small project}} End to End
Lecture {{LECTURE_COUNT}} - Milestone-{{slug}}           {{Verification topic, e.g. testing}}
```

Mark a lecture with ✅ (placed between the slug and the title) only after the student passes its CHECK.

Milestone checks run after Lectures {{MILESTONE_LECTURES}} (see below).

---

## Lecture Track Review Checklist

Use this checklist before moving from the lecture track to the interview-question track.

```
- [ ] Every lecture from 1 to {{LECTURE_COUNT}} is marked with ✅ in the curriculum.
- [ ] Every lecture has a saved `review-N.md` file in its lecture folder.
- [ ] Every `review-N.md` uses the study-card format and ends with the Official reference section.
- [ ] Every milestone check after Lectures {{MILESTONE_LECTURES}} was completed.
- [ ] The student can explain each completed lecture in plain English without reading the full notes.
- [ ] The student can write the core examples again without copying them.
- [ ] The student can identify the main concept of each lecture, not only remember syntax.
- [ ] The student knows which topics still feel weak and has reviewed them before moving on.
```

Do not start `../02-Interview-Questions/README.md` until this checklist is complete.

---

## The Iterative Cycle (Run Once Per Lecture)

### PLAN
Before teaching anything, state:
- The single goal of this lecture in one sentence
- The 2 to 3 concepts the student will know by the end
- What from previous lectures is needed to understand this one

### DO
Deliver the lecture using the 3-Phase Method defined below.

### CHECK
After the lecture, ask one targeted question or give one small task.
The question must test understanding of the core concept, not recall of words.
Wait for the student's answer before proceeding.

### ACT
- Correct answer: confirm it, summarize the lecture in 3 bullet points, ask "Ready for Lecture N+1?"
- Partially correct: identify exactly what is right, explain only the missing part, re-ask differently
- Stuck: return to the analogy, rephrase it, offer a smaller version of the task
- Always name the gap explicitly before re-teaching: "The part that needs one more pass is..."

---

## The 3-Phase Lecture Method

### Phase 1 - Before: Scope and Skim (under 150 words)
- Open with one paragraph: what this lecture covers and why it matters now
- List 3 to 5 key terms that will appear, with one-line plain-language definitions
- State the link to the previous lecture: "Last time we learned X. This builds on that by..."

### Phase 2 - During: Active Session
- Lead with a real-world analogy before showing any code
- After the analogy, ask "Does that picture make sense?" and wait for a yes/no
- Only then introduce code
- **Show code in the chat only.** Tell the student which file to create (for example `code-1.{{FILE_EXT}}`) and that they must type it themselves before running it
- Annotate every line of every code snippet. Zero uncommented lines
- Show the simplest possible version first, then build up step by step
- If a feature is needed that a beginner may not know, explain it in 2 to 3 sentences before using it
- Introduce at most 2 new concepts per lecture. If a third concept appears, defer it to the next lecture

### Phase 3 - After: Review
End every lecture with this study-card block. Save it as `review-N.md`. The **Official reference** section is mandatory and must always be the last section in the file:

```markdown
# Lecture NN — Short Topic Title

> [One or two sentences that capture the heart of this lecture for the learner.]

---

## What you learned

1. [point 1]
2. [point 2]
3. [point 3]

---

## Key rule

> [one sentence to remember]

---

## Watch out

Avoid this common mistake — [one sentence].

---

## Official reference

[{{PRIMARY_SOURCE_NAME}} — Short Label](https://...)
```

Use the `{{PRIMARY_SOURCE_NAME}} Reference` URL from the current lecture's outline. The Official reference section must appear at the very end of the file — no exceptions.

Then run the CHECK step from the iterative cycle.

---

## Analogy Bank

Use these analogies in the matching lectures. Build similar ones for anything not covered here.

**Lecture 1 - {{Title}}:**
{{A 3–5 sentence everyday analogy (kitchen, house, hotel, airport, school, traffic...). No technical comparisons.}}

**Lecture 2 - {{Title}}:**
{{...}}

<!-- One analogy for every lecture except the mini-project and the final milestone. -->

---

## Language Rules

- Never use a technical term without a plain-language explanation on first use:
  - "{{term}}" -> "{{plain-language definition in one line}}"
  - "{{term}}" -> "{{...}}"
  <!-- Add one entry for every key term in the curriculum (15–30 entries). -->
- Use everyday analogies, not comparisons to other technical concepts
- Short sentences. No paragraph longer than 4 lines
- No emojis at any point during teaching
- No sarcasm, no condescension, no motivational filler phrases
- If the student asks something outside the current lecture, answer it briefly in one or two sentences, then redirect: "Let us finish this lecture and come back to that after the summary."

---

## Code Standards

All code in every lecture must follow these rules:

1. Version: target {{SUBJECT_VERSION}}. Mention the version in Lecture 1 and never assume an older version
2. {{Language-specific file header rules, e.g. "Every PHP block starts with `<?php` and `declare(strict_types=1);`"}}
3. {{File organization rule, e.g. "One class per file"}}
4. Naming follows the official style guide: {{e.g. PascalCase classes, camelCase methods, UPPER_SNAKE_CASE constants}}
5. Always show the full example unless a snippet is explicitly labeled "partial example"
6. Annotate every line of every code snippet. Zero uncommented lines
7. Every code block has a label above it stating what file it belongs to (`code-N.{{FILE_EXT}}`)
8. When introducing a new feature, explain what it is in 2 to 3 sentences before using it in code
9. Examples must be secure by default: no hardcoded secrets, validate inputs, no deprecated or unsafe APIs

---

## Tutor Role: Show Code — Student Writes Code (Mandatory)

**The student writes all code. The tutor only displays it.**

This is a deliberate learning rule, not a limitation. The tutor teaches by showing annotated code examples in the chat. The student must type, save, and run that code themselves in their own files.

### What the tutor does

- **Show** code examples inside the chat as part of teaching (required).
- Explain every line, answer questions, review code the student shares, and help debug errors the student reports.
- Mark lecture progress (the ✅ mark) only in this README.md and in the root README.md progress dashboard. No other files.

### What the student does

- **Write** the content of every `code-N.{{FILE_EXT}}` file by hand in the matching lecture folder (the files already exist as empty stubs).
- **Complete** every `review-N.md` stub by hand (replace each `_Write ... here._` blank and the reference placeholder).
- Run the code locally (`{{RUN_COMMAND}}`) and fix errors before moving on.

### What the tutor must NOT do

- Do NOT write content into any `code-N` files, `review-N.md` files, or other lecture files for the student (the empty scaffold stubs are the only exception).
- Do NOT use file-writing tools to produce the lecture's code, milestone solutions, or answers.
- Do NOT treat showing code in chat as a substitute for the student writing it themselves.

**After each code block in a lecture, remind the student once (briefly):** open the matching file and type the code yourself before running it.

---

## File and Folder Conventions for This Course

### Repository root order

```
README.md                           // Repo overview — start here
01-Lectures/                        // Track 1 · guide + workspace
02-Interview-Questions/             // Track 2 · guide + workspace
03-Visual-Maps/                     // Track 3 · guide + workspace
04-Final-Project/                   // Track 4 · guide + workspace
```

Use **numeric prefixes** (`01-`, `02-`, `03-`, `04-`) so GitHub lists tracks in learning-path order.

### Folder structure

```
01-Lectures/
  README.md
  Part-1-{{PART_1_NAME}}/                                // Lectures 1–NN
    Lecture-01-{{slug}}/
      code-1.{{FILE_EXT}}                                // First code block of the lecture
      code-2.{{FILE_EXT}}                                // Second code block, in the order shown
      review-N.md                                        // The Phase 3 study card (always last)
    Lecture-NN-Milestone-{{slug}}/
      code-1.{{FILE_EXT}}
      review-N.md
      Milestone/                                         // The student's milestone solution
  Part-2-{{PART_2_NAME}}/
    ...
  Part-3-{{PART_3_NAME}}/
    ...
```

- Every lecture folder is scaffolded with empty `code-1.{{FILE_EXT}}` … `code-6.{{FILE_EXT}}` and a `review-7.md` stub (title and one-sentence summary filled in; the remaining sections are blanks for the student). If a lecture needs fewer or more code blocks, delete or add files and renumber `review-N.md` so it stays last.
- Each lecture folder is named `Lecture-NN-concise-topic`.
- Milestone lectures use `Lecture-NN-Milestone-topic` for {{MILESTONE_LECTURES}}.
- Code blocks are saved as `code-1`, `code-2`, ... numbered in the order they appear in the lecture.
- The study card is saved as `review-N.md` in **lowercase** so it sorts after all `code-N` files.
- Every `review-N.md` uses the Phase 3 study-card format and **ends** with the Official reference section.

### Include naming rule

When a code block loads another file, the filename MUST match the student's `code-N` file name, never the class/module name.

- Correct: `{{include statement with 'code-1.{{FILE_EXT}}'}}`
- Wrong:   `{{include statement with the class/module file name}}`

---

## Lecture Content Outline

Below is what each lecture must cover. The tutor must follow this outline but deliver it using the 3-Phase Method and the Iterative Cycle defined above.

---

### Lecture 1 - The Problem: {{Why the subject exists}}
**Goal:** {{One sentence.}}
**Concepts:**
- {{concept 1}}
- {{concept 2}}
**Content:**
- {{What to show first (the pain without this subject)}}
- {{What to show next}}
- Do NOT show the solution syntax yet. This lecture is about the problem, not the solution
**{{PRIMARY_SOURCE_NAME}} Reference:** {{deep link}}

---

### Lecture N - {{Title}}
**Goal:** {{One sentence.}}
**Concepts:**
- {{max 2–3 concepts}}
**Content:**
- Use the {{analogy name}} analogy
- {{Step 1: simplest example}}
- {{Step 2: build up}}
- {{Step 3: show the common error / what breaks}}
- {{Explain the key rule}}
**{{PRIMARY_SOURCE_NAME}} Reference:** {{deep link}}

<!-- Repeat for every lecture. Version-specific lectures include the version in the title. -->

---

### Lecture {{LECTURE_COUNT - 1}} - Mini-Project: {{Project}} End to End
**Goal:** Apply everything learned in a cohesive project.
**Concepts:**
- Combining {{list of major concepts}}
**Content:**
- Build {{small project}} with these components: {{component list}}
- Walk through the entire project file by file

---

### Lecture {{LECTURE_COUNT}} - {{Verification topic, e.g. Testing}}
**Goal:** {{One sentence.}}
**Concepts:**
- {{...}}
**Content:**
- {{...}}
**{{TEST_TOOL}} Reference:** {{deep link}}

---

## Session Flow (Follow This Order Every Time)

```
1. If this is not the first session: ask "Which lecture did we finish last and do you remember the key rule from it?"
   - If they remember: confirm it in one sentence and move on
   - If they do not: re-state the key rule from the previous lecture in two sentences, then move on
2. Announce: "Lecture N - [Title]"
3. Run Phase 1 (scope and skim)
4. Run Phase 2 (active session: analogy first, then code)
5. Run Phase 3 (study card)
6. Ask the CHECK question
7. Wait for the student's answer
8. Run ACT based on the answer
9. If correct: "Ready for Lecture N+1?"
   If not: re-teach the gap, then re-ask the CHECK question in a different form
```

---

## Milestone Checks

Run these in place of the normal CHECK at the end of Lectures {{MILESTONE_LECTURES}}.

**After Lecture {{M1}}:**
{{A from-scratch build task using only Lectures 1–M1. Grade on concept accuracy first, syntax second.}}

**After Lecture {{M2}}:**
{{A design-in-words task (no code needed) proving understanding of the core idea of the middle part.}}

**After Lecture {{M3}}:**
{{A small scenario with 3 numbered steps combining several concepts.}}

**After Lecture {{LECTURE_COUNT}}:**
{{A verification task, e.g. write tests covering one normal case and one failure case.}}

---

## Skip Ahead Policy

If the student wants to skip to a later lecture:
- Do not refuse
- At the start of that lecture, list in one sentence each concept from the skipped lectures that this one depends on
- Offer to go back after the current lecture to fill any gaps if needed

---

## What Not To Do

- Do not write or save lecture code files for the student; show examples in chat and let the student type them
- Do not introduce more than 2 new concepts per lecture
- Do not write a code example without annotating every line
- Do not use the words "simply" or "just" - these words dismiss difficulty
- Do not ask more than one question at a time during the CHECK step
- Do not move to the next lecture until the student passes the CHECK step
- Do not skip the analogy and go straight to code
- Do not repeat the full summary if the student already passed the CHECK and is ready to move on
- Do not teach {{OUT_OF_SCOPE}} in this course. If a student asks, give a one-sentence answer and redirect
- Do not assume the student knows {{tools not yet taught}}. If any of these are needed, explain the minimum required steps
- Do not teach deprecated or outdated features as the main approach
````

---

## 10. File Template — Lecture Folder Files

Every lecture folder starts as a scaffold of empty stubs ([Section 10.4](#104-lecture-scaffold-stubs)).
The learner writes all of their content.

### 10.1 `code-N.{{FILE_EXT}}`

- One file per code block shown in the lecture, numbered in display order (`code-1`, `code-2`, ...).
- Every line has a comment explaining it.
- Example files that intentionally fail (to show an error) say so in a comment, including the expected error message.
- Includes reference other examples by `code-N` file name.

Example format (from the PHP OOP repo):

```php
<?php // Opening PHP tag.

declare(strict_types=1); // Strict types.

require 'code-1.php';       // Load the blueprint.

$car = new Car();        // ERROR: the constructor requires a color, but none was given.
                         // PHP stops: "Too few arguments to function Car::__construct()".
```

### 10.2 `review-N.md` (study card)

- `N` = the number after the last `code-N` file (for example `code-1`…`code-6` → `review-7.md`).
- Exactly these sections, in this order. **Official reference is always last.**

```markdown
# Lecture NN — Short Topic Title

> One or two sentences that capture the heart of this lecture.

---

## What you learned

1. First key point, in plain language.
2. Second key point.
3. Third key point.

---

## Key rule

> One sentence to remember.

---

## Watch out

Avoid this common mistake — one sentence.

---

## Official reference

[{{PRIMARY_SOURCE_NAME}} — Short Label](https://deep-link-to-the-exact-page)
```

### 10.3 `Milestone/` (milestone lectures only)

- Created only inside `Lecture-NN-Milestone-*` folders.
- Contains the learner's solution to the milestone check, using real descriptive file names
  (for example `Milestone/Product.php`), not `code-N`.

### 10.4 Lecture scaffold stubs

Every lecture folder is scaffolded so the learner can start studying immediately:

- Empty files `code-1.{{FILE_EXT}}` … `code-6.{{FILE_EXT}}` (no content at all).
- A `review-7.md` stub with only the title and the one-sentence summary filled in; every other part is a blank:

```markdown
# Lecture NN — Short Topic Title

> One or two sentences that capture the heart of this lecture (written by the scaffold).

---

## What you learned

1. _Write your first summary point here._
2. _Write your second summary point here._
3. _Write your third summary point here._

---

## Key rule

> _Write one clear sentence to remember._

---

## Watch out

Avoid this common mistake — _write one clear sentence here._

---

## Official reference

[_Link label — add the {{PRIMARY_SOURCE_NAME}} URL from the lecture outline_]({{PRIMARY_SOURCE_URL}})
```

- If a lecture needs fewer or more code blocks, the learner deletes or adds `code-N` files and renames
  `review-N.md` so it is always the highest number.
- `Milestone/` folders are not scaffolded; the learner creates them during the milestone check.

---

## 11. File Template — `02-Interview-Questions/README.md`

The **interview skill** file. Same style as the lecture skill, but each unit is one interview question.

### Required sections (in this exact order)

1. YAML front matter.
2. `# {{SUBJECT}} Interview Questions ({{SUBJECT_VERSION}}) - Iterative Practice Track`
3. `## Who This Is For`
4. `## Interview Questions Track ({{QUESTION_COUNT}} Questions, One Per Session)` — rules + Review Checklist + Progress list.
5. `## Question Source Map`
6. `## Interview Question Session Cycle` — PLAN / DO / CHECK / ACT.
7. `## Code Standards`
8. `## Source Reference Rules`
9. `## Interview Questions Folder Structure`
10. `## Question Folder Rules`
11. `## What Not To Do`

### How to write the questions

- Cover every lecture at least once, in lecture order.
- Mix three types: **definition** ("What is X?"), **comparison** ("X vs Y?"), and **reasoning / internals**
  ("Why…?", "What happens when…?", "How is this managed internally?").
- Use the wording real interviewers use. Prefer questions that commonly appear in real interviews.
- Slug each question folder as a short summary (`Question-22-abstract-class-vs-interface`).

### Template

````markdown
---
name: {{SUBJECT_SLUG}}-interview-questions
purpose: >
  This file has exactly one purpose: to serve as the single learning source for
  realistic {{SUBJECT}} interview questions after the {{SUBJECT}} lectures are complete.
scope: >
  This file should only contain interview-question guidance, progress, practice
  rules, and folder conventions related to {{SUBJECT}} interview preparation.
description: >
  Structured, iterative interview-preparation skill for {{SUBJECT}}. Trigger this
  skill when the student wants {{SUBJECT}} interview questions, asks to practice
  interview answers, or says "next interview question".
triggers:
  - user asks for {{SUBJECT}} interview questions
  - user wants to practice {{SUBJECT}} interview answers
  - user says "next interview question"
---

# {{SUBJECT}} Interview Questions ({{SUBJECT_VERSION}}) - Iterative Practice Track

## Who This Is For

Student profile: finished or is close to finishing the {{SUBJECT}} lecture track and wants to prepare for realistic interview questions.

---

## Interview Questions Track ({{QUESTION_COUNT}} Questions, One Per Session)

Start this track only after Lecture {{LECTURE_COUNT}} in `../01-Lectures/README.md` is complete. Deliver exactly one interview question per session unless the student explicitly asks to continue.

Every interview question must be handled like a lecture:
- Understand the question first.
- Explain what the interviewer is really testing.
- Build the answer step by step.
- Write code only when the answer genuinely needs code.
- Ask one CHECK task at the end.
- Mark the question with ✅ only after the student can answer it clearly and pass the practice task.
- Always keep a `Source:` line at the end of each question folder's `README.md`.

This track stays inside {{SUBJECT}}. Do not teach {{OUT_OF_SCOPE}} here.

### Interview Track Review Checklist

```
- [ ] Every interview question from 1 to {{QUESTION_COUNT}} is marked with ✅ in the progress list.
- [ ] Every question folder has a `README.md`.
- [ ] Every question folder `README.md` ends with a `Source:` or `Sources:` line.
- [ ] Every completed question folder has `Status: Completed`.
- [ ] The student can answer each question out loud in interview style.
- [ ] The student can explain the code-based questions without copying the answer.
- [ ] The student can connect each interview question back to the related lecture.
- [ ] The student has written `notes.md` for any question that felt difficult.
- [ ] Weak questions were repeated until the student could answer clearly and confidently.
```

Do not start `../03-Visual-Maps/README.md` until this checklist is complete.

### Interview Question Progress

```
Question 01 - {{Question text}}
Question 02 - {{Question text}}
...
```

---

## Question Source Map

```
Question 01 Source: {{url}}
Question 02 Sources: {{url}}, {{url}}
...
```

---

## Interview Question Session Cycle

### PLAN
Before answering, state:
- The exact interview question.
- The real skill the interviewer is testing.
- Which lecture or lectures this question depends on.

### DO
- Start with a plain-English answer that could be said in an interview.
- Explain each important term before using it deeply.
- If code is needed, show the smallest possible {{SUBJECT_VERSION}} example first.
- Annotate every line of every code snippet.
- Then improve the answer into a stronger interview-ready version.

### CHECK
- For theory questions: ask the student to answer in their own words.
- For code questions: ask the student to write or fix one small code example.
Wait for the student's answer before moving on.

### ACT
- Correct answer: confirm it, give a polished interview answer, and mark the question with ✅.
- Partially correct: identify the missing point, re-teach only that point, then re-ask.
- Stuck: return to the simplest analogy, give a smaller version of the question, then re-ask.

---

## Code Standards

1. Target {{SUBJECT_VERSION}}.
2. {{Language-specific header rules}}
3. Naming follows the official style guide.
4. Keep code examples focused on the interview question.
5. Annotate every line of every code snippet. Zero uncommented lines.
6. Every code block has a label above it stating what file it belongs to.
7. Do not pre-write final solution files for the student.

---

## Source Reference Rules

- Each question folder's `README.md` must end with a `Source:` line.
- Use the official documentation when the question is about language/subject behavior.
- Use official tool documentation when the question is about a tool.
- If one question depends on more than one official page, write `Sources:` and include all relevant links.
- The source line must be the final line in the `README.md`.

---

## Interview Questions Folder Structure

```
02-Interview-Questions/
  Question-01-{{slug}}/
    README.md
    code-1.{{FILE_EXT}}
    code-2.{{FILE_EXT}}
    notes.md
  ...
```

Only `README.md` is created as a scaffold. The code files and `notes.md` are created only when the student works through that question.

---

## Question Folder Rules

Each question folder contains a `README.md` with:
- The exact interview question.
- The related lecture or lectures.
- What the interviewer is testing.
- What a strong answer should cover.
- A practice task.
- The completion rule.
- The source reference as the final line.

When a question is completed:
1. Update its folder `README.md` status from `Not completed` to `Completed`.
2. Mark the matching question with ✅ in the progress list in this file.
3. If code was practiced, keep the student's code inside that question folder.

---

## What Not To Do

- Do not answer more than one interview question per session unless the student explicitly asks to continue.
- Do not turn the track into generic career advice.
- Do not teach {{OUT_OF_SCOPE}} in this file.
- Do not pre-write final answers before the student tries the CHECK task.
- Do not create solution files unless the student is actively working through that question.
- Do not move lecture curriculum content into this file.
````

---

## 12. File Template — Question Folder `README.md`

One per question folder. This is the only file scaffolded inside question folders.
The `Source:` line is **always the final line**.

````markdown
# Question NN - {{Exact interview question}}

Status: Not completed
Related lecture: Lecture {{N}}{{, Lecture M}}
Folder: `02-Interview-Questions/Question-NN-{{slug}}/`

## Interview Question

{{Exact interview question}}

## What The Interviewer Is Testing

{{One or two sentences: the real skill behind the question.}}

## A Strong Answer Should Cover

- {{Key point 1}}
- {{Key point 2}}
- {{Key point 3}}

## Practice Task

{{One concrete task: explain in 2–3 sentences, write a small example, or fix a broken snippet.}}

## Files You May Create Here

- `code-1.{{FILE_EXT}}` for the first code attempt if the answer needs code.
- `code-2.{{FILE_EXT}}` for an improved version after feedback.
- `notes.md` for the final interview-style answer in your own words.

## Completion Rule

After you can answer this question clearly and solve the practice task, mark the question with the check mark in `../README.md`.

## Source

Source: {{deep link}}
````

---

## 13. File Template — `03-Visual-Maps/README.md`

The **visual synthesis** track. After the learner can explain the subject in words (interviews),
they prove they can **see** it: flows, sequences, layers, and one end-to-end system map.
Diagrams use **Mermaid inside Markdown** by default (git-friendly, no proprietary tools).

### How to design the maps

- Cover the subject's core mental models — not a UML course.
- About **0.3–0.5 × lecture count** maps (Section 5). Every major part of the curriculum appears at least once.
- Mix map kinds as needed: concept map, flowchart, sequence, state, layers/placement, compare, end-to-end system.
- The **last map** is always the end-to-end system map. Completing it unlocks the final project.
- Each map folder ships with a scaffolded `README.md` and an empty `map.md` stub (Mermaid fences ready to fill).
- The learner draws; the tutor reviews. Do not pre-draw the answers in the scaffold.

### Required sections in `03-Visual-Maps/README.md` (in this exact order)

1. YAML front matter.
2. `# {{SUBJECT}} Visual Maps ({{SUBJECT_VERSION}}) - See the System`
3. `## Who This Is For`
4. `## Visual Maps Track ({{MAP_COUNT}} Maps, One Per Session)` — rules + Review Checklist + Progress list.
5. `## Map Kind Guide` — short plain-language list of allowed diagram kinds.
6. `## Visual Map Session Cycle` — PLAN / DO / CHECK / ACT.
7. `## Diagram Standards` — Mermaid-first, plain labels, one idea per map.
8. `## Source Reference Rules`
9. `## Visual Maps Folder Structure`
10. `## Map Folder Rules`
11. `## What Not To Do`

### Template — track README

````markdown
---
name: {{SUBJECT_SLUG}}-visual-maps
purpose: >
  This file has exactly one purpose: to guide visual synthesis of {{SUBJECT}}
  after lectures and interview questions, before the final project.
scope: >
  This file should only contain map prompts, diagram standards, progress, and
  folder conventions for {{SUBJECT}} visual maps. It is not a drawing-tools course.
description: >
  Structured visual-maps track for {{SUBJECT}}. Trigger when the student says
  "next visual map", "draw the system", or "start visual maps".
triggers:
  - user wants {{SUBJECT}} visual maps or diagrams
  - user says "next visual map" or "draw the flow"
  - user is between interview questions and the final project
---

# {{SUBJECT}} Visual Maps ({{SUBJECT_VERSION}}) - See the System

## Who This Is For

Student profile: finished the {{SUBJECT}} lecture track and the interview-questions track.
Ready to turn verbal understanding into clear diagrams before building the final project.

---

## Visual Maps Track ({{MAP_COUNT}} Maps, One Per Session)

Start this track only after the Interview Track Review Checklist in `../02-Interview-Questions/README.md` is complete. Deliver exactly one map per session unless the student explicitly asks to continue.

Every map session:
- Restate what concept or flow the map must show.
- Choose the simplest diagram kind that fits (see Map Kind Guide).
- The student draws in `map.md` (Mermaid by default).
- Ask one CHECK: the student explains the diagram out loud without reading labels one by one.
- Mark the map with ✅ only after the diagram is accurate and the CHECK passes.
- Keep a `Source:` line on every map folder `README.md`.

This track stays inside {{SUBJECT}}. Do not teach {{OUT_OF_SCOPE}} here.

### Visual Maps Review Checklist

```
- [ ] Every map from 1 to {{MAP_COUNT}} is marked with ✅ in the progress list.
- [ ] Every map folder has `README.md` and a completed `map.md`.
- [ ] Every map folder `README.md` ends with a `Source:` or `Sources:` line.
- [ ] The final map is an end-to-end system view of {{SUBJECT}}.
- [ ] The student can explain each map in plain English without reading every label.
- [ ] Weak maps were redrawn until the CHECK passed.
```

Do not start `../04-Final-Project/README.md` until this checklist is complete.

### Visual Map Progress

```
Map 01 - {{Map title}}
Map 02 - {{Map title}}
...
Map {{MAP_COUNT}} - End-to-end system map
```

---

## Map Kind Guide

| Kind | Use when |
|:---|:---|
| Concept map | Ideas connect to each other |
| Flowchart | A process has ordered steps and decisions |
| Sequence | Actors exchange steps over time |
| State | One thing changes status |
| Layers / placement | Show where pieces live relative to each other |
| Compare | Two options side by side |
| System map | The whole subject in one picture (always last) |

---

## Visual Map Session Cycle

### PLAN
- Name the map and the single idea it must communicate.
- Pick one diagram kind from the Map Kind Guide.

### DO
- Student drafts the Mermaid diagram in `map.md`.
- Tutor reviews accuracy and simplicity (one idea, clear labels).

### CHECK
- Student explains the diagram aloud as if at a whiteboard.
- One targeted fix if a relationship or order is wrong.

### ACT
- Mark ✅, update progress (Section 16), move to the next map.

---

## Diagram Standards

- Default format: Mermaid fenced blocks inside `map.md`.
- Prefer clear names over clever abbreviations.
- One primary idea per map. Split if the diagram needs a legend longer than the diagram.
- No pre-drawn answer keys in the scaffold.

---

## Source Reference Rules

Every map folder `README.md` ends with `Source:` or `Sources:` pointing at the official docs (or lecture outline) that justify the map.

---

## Visual Maps Folder Structure

```
03-Visual-Maps/
├── README.md
├── Map-01-{{slug}}/
│   ├── README.md
│   ├── map.md
│   └── notes.md          ← optional, learner-created
└── ...
```

---

## Map Folder Rules

- `README.md` is scaffolded (prompt, kind, CHECK, Source).
- `map.md` is scaffolded empty with a Mermaid stub the learner fills.
- `notes.md` is optional and learner-created.

---

## What Not To Do

- Do not start this track before interview questions are complete.
- Do not require Lucidchart, draw.io, or paid tools.
- Do not teach a full UML syllabus — only the map kinds needed for {{SUBJECT}}.
- Do not unlock the final project before the end-to-end system map CHECK passes.
- Do not draw the learner's diagrams for them.
````

### Template — map folder `README.md`

````markdown
# Map {{NN}} - {{Map title}}

Status: Not completed
Related lectures: Lecture {{N}}, Lecture {{M}}
Folder: `03-Visual-Maps/Map-{{NN}}-{{slug}}/`
Diagram kind: {{flowchart | sequence | concept map | state | layers | compare | system}}

## What To Show

{{One paragraph: the single idea this map must communicate.}}

## CHECK

Explain the diagram out loud in under two minutes without reading every label.

## Files

- `map.md` — your Mermaid (or ASCII) diagram.
- `notes.md` — optional short reflection.

## Completion Rule

After the diagram is accurate and you pass the CHECK, mark this map with ✅ in `../README.md`.

## Source

Source: {{deep link or lecture outline reference}}
````

### Template — `map.md` stub

````markdown
# {{Map title}}

```mermaid
%% Draft your diagram here.
```
````

---

## 14. File Template — `04-Final-Project/README.md`

The **capstone guide**. It describes one realistic, intentionally small project that proves mastery of
every lecture, every interview question, and the visual maps. The learner writes all project code.

### How to design the project

- Choose a **real-world business scenario** (ticketing, inventory, booking, invoicing, library, ...).
- Keep it small: no framework, no database at first, no UI, no authentication — unless the subject itself is about those.
- List 12–20 concrete **core features**.
- Define a **target folder structure** that follows the subject's best-practice organization
  (domain, contracts, infrastructure, application, exceptions, tests — or the subject's equivalent).
- Split the work into **milestones `00`–`NN`**: `00` is setup and design in words, the last is the final review.
  Each milestone maps to 2–4 lectures, in lecture order.
- Every milestone has: **Goal**, **The student must create**, **Required concepts**,
  **Behavior to implement**, and a **Completion check**.
- End with a **Concept Coverage Checklist** listing every lecture, the interview track, and the visual-maps track.

### Required sections (in this exact order)

1. YAML front matter.
2. `# {{SUBJECT}} Final Project ({{SUBJECT_VERSION}}) - {{PROJECT_NAME}}` + status line.
3. `## Rule`
4. `## When To Start`
5. `## Final Project Review Checklist`
6. `## Project Summary`
7. `## Student Role (Mandatory)`
8. `## Business Scenario`
9. `## Core Features`
10. `## Required Folder Structure`
11. `## Development Rules`
12. `## Milestone Plan`
13. `## Concept Coverage Checklist`
14. `## Mentor Session Flow` — PLAN / DO / CHECK / ACT.
15. `## Progress`
16. `## Source References`

### Template

````markdown
---
name: {{SUBJECT_SLUG}}-final-project
purpose: >
  This file has exactly one purpose: to guide one realistic final project that
  proves the student understands the {{SUBJECT}} lecture track and interview track.
scope: >
  This file should only contain the final project plan, milestones, validation
  checklist, folder conventions, and mentor rules for the {{SUBJECT}} final project.
description: >
  Structured final-project guide for building one real-world {{SUBJECT}} project
  after finishing the lectures, interview questions, and visual maps. Trigger when the student
  says "start final project", "continue final project", or "review my final project".
triggers:
  - user wants to start the {{SUBJECT}} final project
  - user wants to continue the {{SUBJECT}} final project
  - user asks for project review after finishing lectures, interviews, and visual maps
---

# {{SUBJECT}} Final Project ({{SUBJECT_VERSION}}) - {{PROJECT_NAME}}

> **Status:** Not started — This folder is the student's workspace for the {{SUBJECT}} final project.

## Rule

The student writes all implementation code. The mentor may guide, review, debug, and ask focused questions, but must not write the solution files.

## When To Start

Start only after:
1. All {{LECTURE_COUNT}} lectures in `../01-Lectures/README.md` are completed.
2. All {{QUESTION_COUNT}} interview questions in `../02-Interview-Questions/README.md` are completed.
3. All {{MAP_COUNT}} visual maps in `../03-Visual-Maps/README.md` are completed.
4. The student explicitly says they are ready to start the final project.

This project is the final proof step. It is not a lecture replacement.

**Next step when ready:** Start with Milestone 00 in this README.

---

## Final Project Review Checklist

```
- [ ] Every milestone from 00 to NN is marked with ✅ in the progress list.
- [ ] The project runs from `playground.{{FILE_EXT}}` or the chosen manual runner.
- [ ] {{One line per major concept group that must appear in real code}}
- [ ] Tests cover the most important behavior.
- [ ] `notes.md` explains the main design decisions in interview style.
- [ ] The student can explain every major part and design choice without reading the code line by line.
```

The project is complete only when the code works and the student can explain why the design works.

---

## Project Summary

Build **{{PROJECT_NAME}}**, {{one-sentence description}}.

The project stays intentionally small:
- {{constraint 1, e.g. No framework}}
- {{constraint 2, e.g. No database required at first}}
- {{constraint 3}}

The goal is not to build a huge product. The goal is to prove the student can design and build a complete {{SUBJECT}} solution from scratch.

---

## Student Role (Mandatory)

The mentor may:
- Explain requirements.
- **Show** short annotated examples in the chat (not full solution files).
- Ask design questions.
- Review code written by the student.
- Point out missing concepts.
- Suggest the next small step.
- Help debug errors after the student shares code or error output.

The mentor must not:
- Write complete solution files.
- Create the student's implementation files.
- Build the project on behalf of the student.
- Skip the student's design decisions.
- Turn this into a course on {{OUT_OF_SCOPE}}.

---

## Business Scenario

{{2–4 sentences describing a realistic business need.}}

The business wants to answer questions like:
- {{question 1}}
- {{question 2}}
- {{question 3}}

---

## Core Features

1. {{feature}}
2. {{feature}}
...

---

## Required Folder Structure

```
04-Final-Project/
  README.md                      // This guide
  src/
    {{organized folders and files}}
  tests/
    {{test files}}
  playground.{{FILE_EXT}}        // Student-created manual runner
  notes.md                       // Student's design notes and final reflection
```

This structure is a target, not a starting dump. The student creates files gradually as each milestone requires them.

---

## Development Rules

1. Use {{SUBJECT_VERSION}}.
2. {{Language/tool rules}}
3. Keep each unit focused on one clear responsibility.
4. Do not add features outside the checklist until the core project is complete.
5. Every important rule must be enforced by code, not by comments.
6. Never hardcode secrets or credentials.

---

## Milestone Plan

### Milestone 0 - Project Setup

**Goal:** Create the project workspace and explain the first design.

The student must create:
- `notes.md`
- A first draft of the folder structure.

The student must answer:
- What problem does this project solve?
- What are the main parts of the system?
- {{one design question specific to the subject}}

Completion check:
- The student can explain the project in plain English without code.

---

### Milestone N - {{Title}}

**Goal:** {{One sentence.}}

The student must create:
- {{files/units}}

Required concepts:
- {{concepts from lectures X–Y}}

Behavior to implement:
- {{observable behavior}}

Completion check:
- The student can explain {{the key reasoning}}.

<!-- Repeat. The last milestone is "Final Review": answer 8–10 reflection questions in notes.md. -->

---

## Concept Coverage Checklist

```
Lecture 01 - {{concept}}
Lecture 02 - {{concept}}
...
Interview Questions 01-{{QUESTION_COUNT}} - Explain every major design choice in interview form
```

---

## Mentor Session Flow

### PLAN
Ask:
- Which milestone are you working on?
- What files did you create or change?
- What behavior should work now?

### DO
The student writes the code in their own files. The mentor may explain the next step and show small examples in chat, but must not write or save the implementation.

### CHECK
The mentor asks one focused question or gives one small verification task.

### ACT
- If correct: mark the milestone as complete.
- If partially correct: name the missing concept and ask for one focused change.
- If stuck: reduce the task to a smaller version.

---

## Progress

```
Milestone 00 - Project Setup
Milestone 01 - {{Title}}
...
Milestone NN - Final Review
```

Mark a milestone with ✅ only after the student can explain it and the code behavior works.

---

## Source References

This project is based on the same official learning sources used by the lecture and interview tracks.

Sources:
- {{url}}
- {{url}}
````

---

## 15. Adapting to Non-Technical Subjects

The structure stays identical. Only the practice files and a few labels change.

| Technical repo | Non-technical repo (languages, business, exams, soft skills...) |
|:---|:---|
| `code-N.{{FILE_EXT}}` | `practice-N.md` (exercise written by hand in Markdown) |
| "Annotate every line of code" | "Explain every step of every worked example" |
| `{{RUN_COMMAND}}` | "Read it aloud / solve it on paper, then compare with the worked example" |
| Code Standards | Practice Standards (format, terminology, citation style) |
| Official documentation | Official textbook, exam board, standards body, recognized university material |
| Milestone = build a class | Milestone = solve a realistic case, write an essay, or explain a concept from memory |
| Final project = an application | Final project = a real deliverable (case study, portfolio, report, mock exam, presentation) |
| Testing lecture (last) | Self-assessment lecture (last): mock test with answer key and grading rubric |
| `{{TEST_TOOL}}` | The exam format or rubric used for self-assessment |
| Interview questions | Oral-exam / viva / interview questions for that field |
| `Milestone/` solution files | `Milestone/answer.md` (or the real deliverable name) |
| Final project `src/` and `tests/` | `deliverable/` (the work itself) and `self-check/` (rubric and self-grading) |
| `playground.{{FILE_EXT}}` | `deliverable/README.md` (entry point that explains the deliverable) |
| `.gitignore` | Not needed |

All other rules stay the same: four tracks in order, one unit per session, PLAN–DO–CHECK–ACT,
analogy first, maximum 2 new concepts per lecture, study card with an official reference at the end,
and the learner writes everything.

---

## 16. Progress Update Protocol

When a unit is completed (after the learner passes the CHECK), update **all** of these places:

### After a lecture

1. `01-Lectures/README.md` → add ✅ to the lecture line in the Curriculum block.
2. Root `README.md`:
   - Overall Status table → lecture count and "next" lecture.
   - Lecture progress grid → switch ⬜ to ✅.
   - Progress bar and percentage (`completed / total`, rounded).
   - Badges → `Lectures-X%2FTotal%20Done` and `Current-Lecture%20NN`.
   - Current focus / Last completed lines.
   - The part's table → ✅ for done, `🟡 **Next**` for the next lecture; move `open` to the part with the next lecture.
   - Milestones table → `✅ Passed` when a milestone lecture is completed.
   - "My current progress" line in Track 1.
3. Confirm the lecture folder has its `code-N` files and `review-N.md`.

### After an interview question

1. Question folder `README.md` → `Status: Completed`.
2. `02-Interview-Questions/README.md` → ✅ in the progress list.
3. Root `README.md` → Overall Status and the Track 2 progress table.

### After a visual map

1. Map folder `README.md` → `Status: Completed`.
2. `03-Visual-Maps/README.md` → ✅ in the progress list.
3. Root `README.md` → Overall Status and the Track 3 progress table.

### After a final project milestone

1. `04-Final-Project/README.md` → ✅ in the Progress block; update the status line.
2. Root `README.md` → Overall Status and the Track 4 progress table.

### Suggested commit messages

```
lecture: complete Lecture NN - {{topic}}
interview: complete Question NN - {{slug}}
visual: complete Map NN - {{slug}}
project: complete Milestone NN - {{title}}
docs: update progress dashboard
```

---

## 17. Repository Creation Checklist

Run this after generating a new repository from the template.

```
Sources and freshness
- [ ] Latest stable version identified and recorded in {{SUBJECT_VERSION}}.
- [ ] Every lecture outline ends with a deep link to an official source.
- [ ] Every question README ends with a `Source:` / `Sources:` line.
- [ ] No deprecated feature is taught as the main approach.
- [ ] `Last verified` date written in the root README.
- [ ] Root README has the Staying Current section with a Version History row for {{SUBJECT_VERSION}}.

Structure
- [ ] Root has exactly: README.md, template.md, .cursor/rules/template-sync.mdc, 01-Lectures/, 02-Interview-Questions/, 03-Visual-Maps/, 04-Final-Project/ (+ optional .gitignore).
- [ ] `template.md` has a `Template last synced` date at the top.
- [ ] Every lecture folder exists with the correct `Lecture-NN-slug` name inside the correct part.
- [ ] Every lecture folder contains empty `code-1` … `code-6` stubs and a `review-7.md` stub (Section 10.4).
- [ ] Milestone lectures use `Lecture-NN-Milestone-slug` and match {{MILESTONE_LECTURES}}.
- [ ] Every question folder exists with its README.md.
- [ ] Every map folder exists with its README.md and empty `map.md` stub.
- [ ] No learner content was pre-written (only the empty lecture stubs from Section 10.4 and empty map stubs exist).

Content
- [ ] Lecture 01 explains the problem, not the solution.
- [ ] Each lecture introduces at most 2 new concepts (3 listed concepts at most), and has a goal, content steps, and a reference.
- [ ] Every lecture (except the mini-project and the final milestone) has an analogy in the Analogy Bank.
- [ ] Every key term has a plain-language definition in the Language Rules glossary.
- [ ] Milestone checks are written for all 4 milestones.
- [ ] Every lecture is covered by at least one interview question.
- [ ] Every lecture appears in the final project's Concept Coverage Checklist.
- [ ] Visual maps cover each major part; the last map is the end-to-end system map.
- [ ] Out-of-scope topics are listed in every "What Not To Do" section.
- [ ] No lecture or interview question repeats one from {{PREVIOUS_REPO}} or {{NEXT_REPO}}; overlapping topics point to the neighbor repo.
- [ ] The first lecture starts where {{PREVIOUS_REPO}} stops, and the track covers everything {{NEXT_REPO}} assumes.

Consistency
- [ ] Counts match everywhere (lectures, questions, maps, milestones) in all five README files.
- [ ] All relative links in the root README resolve to real folders.
- [ ] Progress dashboard starts at 0 with Lecture 01 marked as Next.
- [ ] Part count matches {{PART_COUNT}} everywhere (no leftover Part-3 block in a 2-part repo, no missing Part-4 block).
- [ ] Every Table of Contents anchor link works on GitHub.
- [ ] Badge values are URL-encoded correctly and render.
- [ ] A search for `{{` across the repo (excluding `template.md`) returns no results (every placeholder is filled).
- [ ] No `<!-- author instruction -->` comments are left in the generated files.
```

---

## 18. Ready-to-Paste AI Prompt (Generate a New Repo)

Copy this prompt, fill in the first block, and give it to an AI assistant together with this `template.md`.

````text
You are generating a study repository using the attached template.md exactly.

SUBJECT: <e.g. Design Patterns in PHP>
LEARNER PROFILE: <e.g. knows PHP OOP well, no design-pattern experience>
PREREQUISITES: <e.g. PHP 8.5 OOP: classes, interfaces, abstract classes, traits>
OUT OF SCOPE: <e.g. framework-specific implementations, architecture styles>
PREVIOUS REPO IN THE SERIES: <name + URL, or None>
NEXT REPO IN THE SERIES: <name + URL, or None>
PRACTICE LANGUAGE / FILE EXTENSION: <e.g. PHP / php>  (use md for non-technical subjects)
PREFERRED SIZE: <small | medium | large | let the template decide>

Rules:
1. Research first. Use only official documentation, official specs, release notes,
   or canonical books/authors (Section 4). Do not rely on memory for versions or features:
   check the official releases/changelog page to find the latest stable version as of today,
   and verify that no feature you teach is deprecated or removed. Record the version and today's date.
   Every reference URL must be a real, working deep link you have checked.
2. Apply the 20/80 principle: teach the most-used concepts first; leave rare edge cases late or out.
3. Size the curriculum with Section 5 (parts, milestones at ~1/6, 1/2, 3/4, end;
   Lecture 01 = the problem; second-to-last = mini-project; last = verification milestone).
4. Generate ONLY the scaffold described in Section 6:
   - Root README.md (Section 8 template, progress at 0, Lecture 01 = Next)
   - 01-Lectures/README.md (Section 9 template, fully filled: curriculum, analogy for every lecture,
     glossary, code standards, full outline for every lecture with a deep-link reference, milestone checks)
   - Every Part-N-*/Lecture-NN-*/ folder with empty code-1..code-6 stubs and a review-7.md stub (Section 10.4)
   - 02-Interview-Questions/README.md (Section 11 template, full question list + source map)
   - One README.md per question folder (Section 12 template, Source line last)
   - 03-Visual-Maps/README.md (Section 13 template, full map list + standards)
   - One README.md + empty map.md per map folder (Section 13 templates)
   - 04-Final-Project/README.md (Section 14 template, real business scenario, milestones 00..NN,
     concept coverage for every lecture)
   - .cursor/rules/template-sync.mdc (copied exactly from Section 19)
   - Keep template.md in the repo root and set its "Template last synced" date to today
5. Do NOT write any learner content: the code-N stubs stay empty, review-N.md stubs keep their blanks,
   and notes.md, Milestone/, src/, tests/ are not created.
6. Follow every naming convention in Section 7.
7. Finish by running the Repository Creation Checklist in Section 17 and report any item that failed.
8. Series without overlap (Section 3, principle 15): read the curricula of the previous and next repos first.
   Do not repeat any of their lectures or questions; list their topics in OUT OF SCOPE with pointers.
9. From now on, follow the Template Sync Rule (Section 19): any change to structure, conventions,
   or method must update template.md in the same change.
10. Living repo (Section 3, principle 16): include the Staying Current section in the root README.
    When a new version is released, update this same repo with Section 4.4.
````

### Session prompts (daily use in a new chat)

Attach the track's `README.md` (and the root `README.md` for progress) with each prompt.

````text
Start / continue lectures:
  Act as the tutor defined in 01-Lectures/README.md. Check the curriculum for the last ✅ lecture,
  run the Session Flow for the next lecture, and follow every rule in the file. Do not create my files.

Interview practice:
  Act as defined in 02-Interview-Questions/README.md. Take the next question without ✅
  and run the Interview Question Session Cycle.

Visual maps:
  Act as defined in 03-Visual-Maps/README.md. Take the next map without ✅
  and run the Visual Map Session Cycle. Do not draw my diagram for me.

Final project:
  Act as the mentor defined in 04-Final-Project/README.md. I am on Milestone NN.
  Run the Mentor Session Flow. Review my code; do not write the solution files.

Mark progress (after I pass the CHECK):
  Apply the Progress Update Protocol in template.md Section 16 for Lecture NN / Question NN / Map NN / Milestone NN.

Update to a new version (when a new version is released):
  Run the Version update procedure in template.md Section 4.4 for {{SUBJECT}} <new version>.
  Read the official release notes and migration guide, update the lecture outlines, questions, and project,
  list catch-up items for lectures I already completed, and add a Version History row.

Sync the template (after changing structure, conventions, or method):
  Apply the Template Sync Rule in template.md Section 19. Compare the repo with template.md,
  update every outdated section, and report what changed.
````

---

## 19. Template Sync Rule (Keep This File a Mirror)

`template.md` is only useful if it matches the repository exactly. An outdated template silently
spreads old structure and old rules into every future repo. Therefore:

> **Rule:** `template.md` must always be an exact, subject-neutral mirror of the repository's
> structure, conventions, and method. Any change that makes it outdated must update it **in the same change**.

### 19.1 What triggers an update

| Change in the repo | Update in `template.md` |
|:---|:---|
| Track, part, folder, or file naming changes | Sections 6, 7 (+ 8–14 where names appear) |
| Root `README.md` sections added, removed, or reordered | Section 8 |
| `01-Lectures/README.md` rules, method, or section order | Section 9 |
| `code-N`, `review-N.md`, or `Milestone/` format | Section 10 |
| `02-Interview-Questions/README.md` rules or section order | Section 11 |
| Question folder `README.md` format | Section 12 |
| `03-Visual-Maps/README.md` or map folder format | Section 13 |
| `04-Final-Project/README.md` rules or section order | Section 14 |
| Source, citation, or freshness rules | Sections 3, 4 |
| Lecture / question / map / milestone sizing logic | Section 5 |
| Progress tracking (which files get updated, how) | Section 16 |
| New required file, tool, or check | Sections 6, 17, 18 |
| A new placeholder | Section 2 |
| This rule file changes | Section 19.3 |

### 19.2 What does NOT trigger an update

Learner and subject-specific content: `code-N` files, `review-N.md` text, filled `map.md` diagrams,
progress check marks, lecture/question/map wording that only applies to the current subject,
and final-project code.

### 19.3 Enforcement (copy into every repo)

Every repository built from this template contains this file at `.cursor/rules/template-sync.mdc`.
Because it is always applied, the AI assistant checks the sync on every change automatically.

````markdown
---
description: Keep template.md an exact mirror of this repository's structure, conventions, and method
alwaysApply: true
---

# Template Sync Rule (Mandatory)

`template.md` is the reusable blueprint for every future study repo. It must always mirror this repository.
A change that makes `template.md` outdated is an incomplete change.

## When `template.md` MUST be updated (in the same change)

Any change to the repo's **structure, conventions, or method**, for example:

- Adding, removing, renaming, or reordering tracks, part folders, or folder/file naming patterns
- Changing the format of `review-N.md`, `code-N` files, question `README.md`, `notes.md`, `map.md`, or `Milestone/`
- Adding, removing, or reordering sections in the root `README.md` or any track `README.md`
- Changing rules: the iterative cycle, 3-phase method, language rules, code standards, tutor role,
  source/citation rules, checklists, milestone rules, session flow, or "What Not To Do"
- Changing how progress is tracked or which files are updated on completion
- Adding new files, tools, or rule files to the repo root (for example `.gitignore`, `composer.json`)

## What does NOT require an update

Learner content and subject-specific content: `code-N` files, `review-N.md` text, filled `map.md` diagrams,
progress check marks, lecture/question/map wording that only applies to this subject, and project code.

## How to update

1. Edit the matching section of `template.md` in a subject-neutral way, using the placeholders
   defined in its Section 2 instead of subject-specific values.
2. If a new placeholder is introduced, define it in Section 2.
3. If a new required file or check is introduced, add it to Section 6 (structure),
   Section 17 (checklist), and Section 18 (AI prompt).
4. If this rule file itself changes, update its copy in Section 19 of `template.md`.
5. Update the `Template last synced` date at the top of `template.md` to today.
6. Verify: code fences are balanced, Table of Contents links resolve, and every upper-case placeholder is defined.
7. In the final response, state which `template.md` sections were updated, or state
   "template.md: no update needed" with the reason.
````

### 19.4 Manual sync check (when in doubt)

Run this whenever you are unsure whether the template is still accurate:

```
- [ ] Every folder/file pattern in the repo matches Sections 6 and 7.
- [ ] Every section heading of each README in the repo appears, in the same order, in Sections 8–14.
- [ ] The study card, question README, and map README formats match Sections 10, 12, and 13 exactly.
- [ ] The progress steps actually used match Section 16.
- [ ] `.cursor/rules/template-sync.mdc` matches the copy in Section 19.3.
- [ ] The `Template last synced` date at the top is updated.
```

### 19.5 Improvements flow back

If a future repo improves the method (a better rule, a clearer file format, a new useful check),
apply the same improvement to `template.md` in that repo **and** to your master copy of `template.md`,
so the next repository starts from the best version.
