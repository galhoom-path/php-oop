---
name: php-oop-visual-maps
purpose: >
  This file has exactly one purpose: to guide visual synthesis of PHP OOP
  after lectures and interview questions, before the final project.
scope: >
  This file should only contain map prompts, diagram standards, progress, and
  folder conventions for PHP OOP visual maps. It is not a drawing-tools course.
description: >
  Structured visual-maps track for PHP OOP (PHP 8.5+). Trigger when the
  student says "next visual map", "draw the system", or "start visual maps".
triggers:
  - user wants PHP OOP visual maps or diagrams
  - user says "next visual map" or "draw the flow"
  - user is between interview questions and the final project
---

# PHP OOP Visual Maps (PHP 8.5+) - See the System

## Who This Is For

Student profile: finished the PHP OOP lecture track and the interview-questions track.
Ready to turn verbal understanding into clear diagrams before building the final project.

---

## Visual Maps Track (12 Maps, One Per Session)

Start this track only after the Interview Track Review Checklist in `../02-Interview-Questions/README.md` is complete. Deliver exactly one map per session unless the student explicitly asks to continue.

Every map session:
- Restate what concept or flow the map must show.
- Choose the simplest diagram kind that fits (see Map Kind Guide).
- The student draws in `map.md` (Mermaid by default).
- Ask one CHECK: the student explains the diagram out loud without reading labels one by one.
- Mark the map with ✅ only after the diagram is accurate and the CHECK passes.
- Keep a `Source:` line on every map folder `README.md`.

This track stays inside PHP OOP. Do not teach design patterns or full SOLID theory here; those belong to the separate OOD course. Map 11 is only a one-box "out of scope" reminder, not a SOLID lesson.

### Visual Maps Review Checklist

```
- [ ] Every map from 1 to 12 is marked with ✅ in the progress list.
- [ ] Every map folder has `README.md` and a completed `map.md`.
- [ ] Every map folder `README.md` ends with a `Source:` or `Sources:` line.
- [ ] The final map is an end-to-end system view of a small PHP OOP application.
- [ ] The student can explain each map in plain English without reading every label.
- [ ] Weak maps were redrawn until the CHECK passed.
```

Do not start `../04-Final-Project/README.md` until this checklist is complete.

### Visual Map Progress

```
Map 01 - Why objects
Map 02 - Class vs object
Map 03 - Visibility
Map 04 - Encapsulation
Map 05 - Inheritance tree
Map 06 - Polymorphism
Map 07 - Interfaces vs abstract
Map 08 - Traits composition
Map 09 - Namespaces and autoload
Map 10 - Exceptions flow
Map 11 - SOLID preview (out of scope)
Map 12 - End-to-end OOP system map
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
- Mark ✅, update progress in this file, move to the next map.

---

## Diagram Standards

- Default format: Mermaid fenced blocks inside `map.md`.
- Prefer clear names over clever abbreviations.
- One primary idea per map. Split if the diagram needs a legend longer than the diagram.
- No pre-drawn answer keys in the scaffold.
- Labels stay in plain English; PHP keywords only when the map is about that keyword.

---

## Source Reference Rules

- Each map folder's `README.md` must end with a `Source:` or `Sources:` line.
- Use the official PHP Manual when the map is about language or runtime behavior.
- The source line must be the final line in the map folder `README.md`.

---

## Visual Maps Folder Structure

```
03-Visual-Maps/
├── README.md
├── Map-01-why-objects/
│   ├── README.md
│   ├── map.md
│   └── notes.md          ← optional, learner-created
├── Map-02-class-vs-object/
│   ...
└── Map-12-end-to-end-oop-system-map/
    ...
```

---

## Map Folder Rules

Each map folder contains a `README.md` with:
- Status, related lectures, diagram kind.
- What To Show, CHECK, Files, Completion Rule.
- The source reference as the final line.

When a map is completed:
1. Update its folder `README.md` status from `Not completed` to `Completed`.
2. Mark the matching map with ✅ in the progress list in this file.
3. Keep the student's diagram in that map's `map.md`.

`map.md` is scaffolded empty with a Mermaid stub the learner fills. `notes.md` is optional and learner-created.

---

## What Not To Do

- Do not start this track before interview questions are complete.
- Do not require Lucidchart, draw.io, or paid tools.
- Do not teach a full UML syllabus — only the map kinds needed for PHP OOP.
- Do not unlock the final project before the end-to-end system map CHECK passes.
- Do not draw the learner's diagrams for them.
- Do not turn maps into a full SOLID or design-patterns course (redirect to OOD).
