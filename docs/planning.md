 ---
layout: page
title: Planning
---

<style>
  .plan-btns a { display: inline-block; margin: 0 .5rem .5rem 0; padding: .45rem .9rem; border-radius: 6px;
                 background: #1f3a5f; color: #fff !important; text-decoration: none; font-size: .95rem; }
  .plan-btns a.alt { background: #eef2f7; color: #1f3a5f !important; border: 1px solid #c9d4e2; }
  .plan-pdf { display: block; width: 100%; height: 800px; border: 1px solid #d0d7de; border-radius: 6px; margin: .5rem 0 1rem; }
  .plan-fig { margin: 1rem 0 1.75rem; }
  .plan-fig img { max-width: 100%; height: auto; border: 1px solid #d0d7de; border-radius: 6px; }
  .plan-fig figcaption { font-size: .9rem; color: #57606a; margin-top: .4rem; }
  .plan-note { background: #f6f8fa; border-left: 4px solid #7fa3cf; padding: .6rem .9rem; margin: .8rem 0 1.2rem; }
</style>

Our software engineering method, tools, team organisation and project plan are set out in our Assessment 1 report, **Plan1.pdf**. This page holds the report, the weekly snapshots of our plan, and a record of how the plan changed as the project progressed.

<p class="plan-btns">
  <a href="{{ '/assets/Plan1.pdf' | relative_url }}" download>Download Plan1.pdf</a>
  <a class="alt" href="#snapshots">Weekly snapshots</a>
  <a class="alt" href="#evolution">How the plan evolved</a>
</p>

<object class="plan-pdf" data="{{ '/assets/Plan1.pdf' | relative_url }}" type="application/pdf">
  <p>Your browser can't show the PDF here. <a href="{{ '/assets/Plan1.pdf' | relative_url }}">Open Plan1.pdf</a>.</p>
</object>

**On this page:** [Method and tools](#method) · [Team organisation](#team) · [Weekly snapshots](#snapshots) · [How the plan evolved](#evolution)

## Method and tools {#method}

We used an **Agile** approach with short iterations and flexible weekly planning. Requirements, architecture and implementation were revisited as we learned more, for example rewriting the requirements after reviewing the customer meeting and revising the architecture before implementation. We rejected Waterfall, because it fixes the whole plan up front, and Scrum-style weekly sprints, which carried more ceremony than a seven-person, six-week project needed.

| Purpose | Tool | Why it fits our method |
|---|---|---|
| Version control and task tracking | GitHub (repository, Issues, Milestones, Projects board) | Code, tasks and this website in one place; branches and pull requests let several people work at once; issues and milestones track each week's tasks |
| Game framework and build | LibGDX with Gradle (Java 17), generated with gdx-liftoff | Meets CR_JAVA and CR_ENGINE; Gradle builds one executable JAR for Windows, macOS and Linux (CR_JAR, CR_PLATFORMS) |
| IDE | IntelliJ IDEA | Free for students, with built-in Gradle and Git support; one shared IDE lets team members help each other |
| Diagrams | PlantUML, Mermaid in Lucidchart | Diagrams written as text are version-controlled alongside the code, so changes to the design are recorded |
| Communication | WhatsApp, email and weekly in-person meetings | Quick day-to-day contact, with Monday reviews and Tuesday lab sessions for planning and joint work |

## Team organisation {#team}

Each member owned specific features and documents, while decisions were discussed and agreed as a team. Tasks were shared out by a mix of volunteering and assignment and tracked as GitHub Issues on the project board. We met twice a week: Monday meetings reviewed progress and agreed the direction, and Tuesday lab sessions were for working together. This gave members clear ownership while keeping the whole team aligned on one deadline.

Owners named in our final Gantt chart (week of 9 November):

| Team member | Tasks in the final plan |
|---|---|
| Ben Smejko | Goose pathfinding; goose wave spawning |
| Henrik Bowden | Map and map obstacles; main game loop; game timer and pause |
| June Njiru | Risk assessment; items and events counter; unit testing |
| Louis Price | Risk assessment; exhaustion meter; win and lose screens |
| Sarah James | Event, Item and Score classes |
| Sruthiksha Ananth | Unit testing |
| Tim Giles | Design of items and events |

## Weekly snapshots {#snapshots}

Snapshots of our plan, oldest first. Each image opens at full size.

### Snapshot 1: first Gantt chart (October 2026) {#snapshot-1}

<div class="plan-note">Phase 1 (requirements, customer interview, CRC cards, class diagrams, risk assessment) planned in detail from 5 to 29 October. Implementation was a single broad "Create Map" block for all teammates, starting on 30 October, with the JAR built on 14 November.</div>

<figure class="plan-fig">
  <a href="{{ '/assets/plan/gantt-v1.png' | relative_url }}"><img src="{{ '/assets/plan/gantt-v1.png' | relative_url }}" alt="First Gantt chart, October 2026"></a>
  <figcaption>First Gantt chart: start and end dates, durations and owners for each task, with implementation kick-off on 29 October.</figcaption>
</figure>

### Snapshot 2: week plan, 27 October to 1 November {#snapshot-2}

<div class="plan-note">Our first detailed week plan. Every task has an ID, an output, a linked requirement or report section, a priority (High or Medium), a due date and its dependencies, across four workstreams: Planning and Method, Risk Assessment, Requirements and Implementation.</div>

<figure class="plan-fig">
  <a href="{{ '/assets/plan/week-plan-27oct-part1.png' | relative_url }}"><img src="{{ '/assets/plan/week-plan-27oct-part1.png' | relative_url }}" alt="Week plan part 1: planning and method tasks"></a>
  <figcaption>Part 1: Planning and Method tasks (PM1 to PM4).</figcaption>
</figure>
<figure class="plan-fig">
  <a href="{{ '/assets/plan/week-plan-27oct-part2.png' | relative_url }}"><img src="{{ '/assets/plan/week-plan-27oct-part2.png' | relative_url }}" alt="Week plan part 2: planning, risk and requirements tasks with due dates and dependencies"></a>
  <figcaption>Part 2: Planning, Risk Assessment and Requirements tasks, with due dates and dependencies.</figcaption>
</figure>
<figure class="plan-fig">
  <a href="{{ '/assets/plan/week-plan-27oct-part3.png' | relative_url }}"><img src="{{ '/assets/plan/week-plan-27oct-part3.png' | relative_url }}" alt="Week plan part 3: implementation and architecture tasks linked to requirements"></a>
  <figcaption>Part 3: Implementation tasks (IM1 to IM11), each linked to the requirements it delivers.</figcaption>
</figure>

### Snapshot 3: final Gantt chart (week of 9 November) {#snapshot-3}

<div class="plan-note">Implementation broken into named tasks with owners and dependencies, from design work on 30 October to the final JAR and licences on 14 November. Scoring is marked low priority.</div>

<figure class="plan-fig">
  <a href="{{ '/assets/plan/gantt-final.png' | relative_url }}"><img src="{{ '/assets/plan/gantt-final.png' | relative_url }}" alt="Final Gantt chart, week of 9 November"></a>
  <figcaption>Final Gantt chart: arrows show dependencies between implementation tasks.</figcaption>
</figure>

<!-- To add another weekly snapshot, copy this block, change the number, date and image name, and put the image in docs/assets/plan/
### Snapshot 4: week of DD Month (DD Month 2026) {#snapshot-4}
<div class="plan-note">One or two sentences on what changed this week.</div>
<figure class="plan-fig">
  <a href="{{ '/assets/plan/IMAGE.png' | relative_url }}"><img src="{{ '/assets/plan/IMAGE.png' | relative_url }}" alt="Describe the snapshot"></a>
</figure>
-->

## How the plan evolved {#evolution}

Comparing our first and final Gantt charts shows how the plan became more detailed as our understanding of the architecture improved.

| What changed | First plan | Final plan |
|---|---|---|
| Class diagrams | 10 days (20 to 29 October) | 20 days (20 October to 8 November), with a "Revise architecture" task added on 4 November |
| Implementation kick-off | 29 October | 3 November |
| Implementation tasks | One broad "Create Map" block for all teammates, plus a few features from 9 November | Design tasks from 30 October, then separate tasks for the map, main loop, Event, Item and Score classes, goose pathfinding, wave spawning, timer and pause, exhaustion meter and win and lose screens |
| Ownership | "teammates" | A named owner for each task |
| Dependencies | Few links between tasks | Arrows from design and architecture to each implementation task, and from features to testing and the final JAR |
| Priorities | Not shown | High and Medium priorities in the week plan; scoring marked low priority in the final chart |
| Testing and release | "Build executable JAR" on 14 November | Unit testing on 13 November, then the final JAR and licences on 13 and 14 November |

Our requirements and architecture pages record the changes to the design itself: see [Requirements]({{ '/requirements.html#changes' | relative_url }}) and [Architecture]({{ '/architecture.html#evidence' | relative_url }}).
