---
layout: page
title: Risks
---

<style>
  .risk-btns a { display: inline-block; margin: 0 .5rem .5rem 0; padding: .45rem .9rem; border-radius: 6px;
                 background: #1f3a5f; color: #fff !important; text-decoration: none; font-size: .95rem; }
  .risk-btns a.alt { background: #eef2f7; color: #1f3a5f !important; border: 1px solid #c9d4e2; }
  .risk-pdf { display: block; width: 100%; height: 800px; border: 1px solid #d0d7de; border-radius: 6px; margin: .5rem 0 1rem; }
  .risk-note { background: #f6f8fa; border-left: 4px solid #7fa3cf; padding: .6rem .9rem; margin: .8rem 0 1.2rem; }
  table.risk-matrix { border-collapse: collapse; margin: .5rem 0 1.25rem; }
  table.risk-matrix th, table.risk-matrix td { border: 1px solid #c9d1d9; padding: .5rem .8rem; text-align: center; min-width: 7rem; }
  table.risk-matrix th { background: #f6f8fa; }
  .rm-low { background: #e6f4e4; } .rm-med { background: #fdf3d8; } .rm-high { background: #fbe1df; }
  .lvl { display: inline-block; min-width: 1.6rem; padding: 0 .3rem; border-radius: 4px; font-weight: bold; text-align: center; }
  .lvl-H { background: #fbe1df; color: #8a1f17; } .lvl-M { background: #fdf3d8; color: #7a5600; } .lvl-L { background: #e6f4e4; color: #1e5c1a; }
</style>

Our approach to risk management and our risk register are set out in our Assessment 1 report, **Risk1.pdf**. This page holds the report, the full register and a summary of where each risk sits.

<p class="risk-btns">
  <a href="{{ '/assets/Risk1.pdf' | relative_url }}" download>Download Risk1.pdf</a>
  <a class="alt" href="#register">Risk register</a>
  <a class="alt" href="#matrix">Risk matrix</a>
</p>

<object class="risk-pdf" data="{{ '/assets/Risk1.pdf' | relative_url }}" type="application/pdf">
  <p>Your browser can't show the PDF here. <a href="{{ '/assets/Risk1.pdf' | relative_url }}">Open Risk1.pdf</a>.</p>
</object>

**On this page:** [Our process](#process) · [Rating scale](#scale) · [Risk register](#register) · [Risk matrix](#matrix) · [Monitoring](#monitoring)

## Our process {#process}

We manage risk in four steps:

1. **Identify** risks across four categories: personnel, technical, planning and the product itself, so we look beyond purely technical problems.
2. **Analyse** each risk by how likely it is to happen and how severe its effect would be.
3. **Plan** mitigation that either prevents the risk or reduces its impact, for example keeping all code on GitHub, or making sure more than one person knows each task.
4. **Monitor** each risk through a named owner, and review the register at our weekly team meetings, updating ratings and mitigations as things change.

Escape the Geese is a short project, so we use a simple register with Low, Medium and High ratings rather than a more complex scoring method.

## Rating scale {#scale}

| Rating | Likelihood | Severity |
|---|---|---|
| <span class="lvl lvl-L">L</span> Low | Unlikely to happen | Minor delay or inconvenience, with little or no effect on the deliverables |
| <span class="lvl lvl-M">M</span> Medium | Plausible | Noticeable delay, or lower quality deliverables |
| <span class="lvl lvl-H">H</span> High | Very likely to happen | Serious delay, or failure to meet the project's requirements |

## Risk matrix {#matrix}

Where each risk sits by likelihood and severity. Risks towards the top right need the most attention.

<table class="risk-matrix">
  <tr><th>Likelihood ↓ / Severity →</th><th>Low</th><th>Medium</th><th>High</th></tr>
  <tr><th>High</th><td class="rm-med">R_3, R_6</td><td class="rm-high">R_5</td><td class="rm-high">–</td></tr>
  <tr><th>Medium</th><td class="rm-low">–</td><td class="rm-med">R_1, R_2, R_7, R_10</td><td class="rm-high">R_4, R_9</td></tr>
  <tr><th>Low</th><td class="rm-low">–</td><td class="rm-low">–</td><td class="rm-med">R_8, R_11</td></tr>
</table>

No risk is rated High for both likelihood and severity. The risks we watch most closely are merge conflicts (R_5), losing code (R_4) and underestimating time (R_9).

## Monitoring {#monitoring}

Every risk has an owner who checks that its mitigation is being followed. We review the register at our weekly team meetings and update a risk's ratings or mitigation when something changes.

<!-- To record a review, copy this block and fill it in:
### Review: DD Month 2026
<div class="risk-note">What changed: for example, R_5 likelihood lowered from H to M after we agreed module ownership.</div>
-->
