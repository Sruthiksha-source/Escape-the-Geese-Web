---
layout: page
title: Requirements
---

<style>
  .req-btns a { display: inline-block; margin: 0 .5rem .5rem 0; padding: .45rem .9rem; border-radius: 6px;
                background: #1f3a5f; color: #fff !important; text-decoration: none; font-size: .95rem; }
  .req-btns a.alt { background: #eef2f7; color: #1f3a5f !important; border: 1px solid #c9d4e2; }
  .req-pdf { display: block; width: 100%; height: 800px; border: 1px solid #d0d7de; border-radius: 6px; margin: .5rem 0 1rem; }
  .req-pdf.short { height: 600px; }
  .req-note { background: #f6f8fa; border-left: 4px solid #7fa3cf; padding: .6rem .9rem; margin: .8rem 0 1.2rem; }
  .req-old { border-left-color: #d9a3a3; }
</style>

Our requirements for Escape the Geese are set out in our Assessment 1 report, **Req1.pdf**. They were elicited from the customer's product brief, the assessment paper and our customer meeting, and every requirement has a unique ID so it can be traced through the architecture, the code and testing. This page holds the full report, our customer meeting notes, and a record of how the requirements changed since our first version.

<p class="req-btns">
  <a href="{{ '/assets/Req1.pdf' | relative_url }}" download>Download Req1.pdf</a>
  <a class="alt" href="{{ '/assets/Customer%20Meeting%201.pdf' | relative_url }}">Customer meeting notes (PDF)</a>
  <a class="alt" href="#changes">What changed</a>
</p>

<object class="req-pdf" data="{{ '/assets/Req1.pdf' | relative_url }}" type="application/pdf">
  <p>Your browser can't show the PDF here. <a href="{{ '/assets/Req1.pdf' | relative_url }}">Open Req1.pdf</a>.</p>
</object>

**On this page:** [At a glance](#summary) · [User requirements](#user) · [Customer meetings](#meetings) · [What changed](#changes) · [Traceability](#traceability)

## Requirements at a glance {#summary}

Each requirement has a priority using the keywords of ISO/IEC/IEEE 29148: *Shall* (mandatory), *Should* (desirable) and *May* (optional, dropped first if time runs short). Every functional and quality requirement names the user requirement it satisfies, and every constraint and quality requirement has a measurable fit criterion.

| Type | Prefix | What it means | Count |
|---|---|---|---|
| User requirements | UR_ | What the customer and players need from the game, in plain language | 11 |
| Constraints | CR_ | Fixed conditions on the solution, such as platform, language and licensing, each with its source | 8 |
| Functional requirements | FR_ | Specific behaviours the game must perform: 27 Shall, 5 Should, 2 May | 34 |
| Quality requirements | QR_ | How well the game must perform, such as start-up time and frame rate | 6 |

- **Constraints:** runs on Windows, macOS and Linux on a standard computer without a dedicated graphics card; written in Java 17 with a well-documented 2D framework; delivered as one executable JAR; licensed assets only; geese and player are never shown being harmed and there is no health bar.
- **Gameplay:** the player moves around a campus map with York landmarks, avoiding waves of geese and using items to disperse or distract them before a 5-minute timer runs out. An exhaustion meter fills while geese are close, in place of health.
- **Winning and losing:** clear every wave to win; lose when the timer ends or the exhaustion meter fills.
- **Scoring and events:** points reward dispersing geese quickly; at least five events help or hinder the player, each with a distinct sound and a visual cue.
- **Accessibility:** a tutorial, starting paused, pause at any time, volume and full-screen settings, and non-colour cues on interactable objects.
- **Quality:** main menu within 3 seconds, at least 30 fps, a readable HUD in every display mode, and a game most players can win on their first attempt.
- **Out of scope:** saving progress, high scores, leaderboards and player data; mobile platforms; more than one map or entering buildings.

## User requirements {#user}

| ID | Requirement | Priority |
|---|---|---|
| UR_MOVEMENT | The user shall be able to control their character on the campus map | Shall |
| UR_GEESE | Geese shall be the main obstacle to the user completing the game | Shall |
| UR_ITEMS | The user shall have items they can use to disperse or distract geese | Shall |
| UR_EVENTS | The user shall encounter events that help or hinder them | Shall |
| UR_GAME_END | The game shall end in a clear win or loss | Shall |
| UR_SCORE | The user shall receive a score that rewards good item use and timely progress | Shall |
| UR_TUTORIAL | A first-time user shall be able to learn the controls and goal inside the game | Shall |
| UR_ACCESSIBILITY | The game shall be accessible to players of all skills and abilities | Shall |
| UR_RELATE | The game should be recognisable to York students and applicants through landmarks and references | Should |
| UR_PERFORMANCE | The game should start quickly and run smoothly so players stay engaged | Should |
| UR_EXTENSIBLE | New items, events and features should be addable in later iterations without a redesign | Should |

The constraints, functional and quality requirements, with their fit criteria, are in section (b) of [Req1.pdf]({{ '/assets/Req1.pdf' | relative_url }}).

## Customer meetings {#meetings}

| Meeting | Date | Focus | Notes |
|---|---|---|---|
| Meeting 1 | 9 October 2026 | Clarifying the product brief: platform, gameplay rules, accessibility and scope | [PDF]({{ '/assets/Customer%20Meeting%201.pdf' | relative_url }}) |

### Meeting 1: key outcomes (9 October 2026) {#meeting-1}

- **Platform:** Windows, macOS and Linux desktops, in a top-down 2D view (CR_PLATFORMS, CR_VIEW)
- **Technology:** Java with a stable, well-documented engine; all licences recorded (CR_JAVA, CR_ENGINE, CR_LICENCE)
- **Gameplay:** non-violent wave survival with an exhaustion meter instead of health; win by clearing the waves, lose when the timer ends or the meter fills (CR_PEACE, FR_EXHAUSTION_METER, FR_WIN, FR_LOSE)
- **Items:** different item types, and misusing a distraction item enrages a goose (FR_ITEM_TYPES, FR_ITEM_MISUSE)
- **Accessibility:** important information through at least two of sound, visuals and text, plus pause, volume and full screen (UR_ACCESSIBILITY, FR_EVENT_AUDIO, FR_EVENT_VISUAL)
- **Performance:** loads within a couple of seconds on an average computer (QR_STARTUP)
- **Scope:** a tutorial is required (FR_TUTORIAL); saving progress, leaderboards and storing player data are out of scope

The questions Q1 to Q16 referred to in Req1 are listed in full in the meeting notes:

<object class="req-pdf short" data="{{ '/assets/Customer%20Meeting%201.pdf' | relative_url }}" type="application/pdf">
  <p>Your browser can't show the PDF here. <a href="{{ '/assets/Customer%20Meeting%201.pdf' | relative_url }}">Open the meeting notes</a>.</p>
</object>

## What changed since our first version {#changes}

<div class="req-note req-old"><strong>Initial requirements (October 2026, after meeting 1):</strong> 8 user requirements, 7 constraints, 23 functional and 5 quality requirements. Functional requirements had no priorities, and several points agreed at the meeting were missing.</div>

We reviewed the first version against the full recording of the customer meeting and rewrote it as the final Req1 (11 user, 8 constraint, 34 functional and 6 quality requirements). The main changes:

| Change | Why | Requirements |
|---|---|---|
| Added a tutorial and extensibility as user requirements | The customer said a tutorial must be included and that the game will be extended later | UR_TUTORIAL, UR_EXTENSIBLE |
| Added an exhaustion meter in place of health, and "no health bar" to the non-violence constraint | Agreed at the meeting so geese feel threatening without violence | FR_EXHAUSTION_METER, CR_PEACE |
| Win changed from "100% of geese dispersed" to "every wave cleared"; loss added for a full meter | Matches how the customer described winning and losing | FR_WIN, FR_LOSE |
| Added 11 missing functional requirements | Points agreed at the meeting that were not yet recorded | FR_TUTORIAL, FR_ITEM_TYPES, FR_ITEM_MISUSE, FR_EVENT_VISUAL, FR_EVENT_ITEMS, FR_INTERACTABLES, FR_WAVE_COUNTDOWN, FR_ESCAPE_WIN, FR_DIFFICULTY and others |
| Pause, volume, full screen and event sounds raised from Should to Shall | The customer said the game must be accessible to everyone | FR_PAUSE, FR_VOLUME, FR_FULLSCREEN, FR_EVENT_AUDIO |
| Start-up target tightened from 7 to 3 seconds | The customer asked for loading within a couple of seconds | QR_STARTUP |
| Added a framework constraint and an extensibility quality requirement | Q4 and Q16 of the meeting | CR_ENGINE, QR_EXTENSIBILITY |
| Every functional requirement given a priority and grouped by area | Makes them easier to plan, test and trace | All FR_ |

## Traceability {#traceability}

The same IDs are used in our architecture: each class and diagram names the requirements it satisfies, and Table 5 of Arch1.pdf traces every user requirement to the classes and figures that meet it. See the [Architecture page]({{ '/architecture.html' | relative_url }}).
