---
layout: page
title: Architecture
---

The architecture of Escape the Geese is described in our Assessment 1 report, **Arch1.pdf**. This page holds every diagram at full size, together with the earlier versions that show how the design evolved. All diagrams use UML 2 and every class name matches the code.

<p class="arch-btns">
  <a href="{{ '/assets/pdf/Arch1.pdf' | relative_url }}" download>Download Arch1.pdf</a>
  <a class="alt" href="{{ '/assets/arch/class-diagram-v2.pdf' | relative_url }}">Final class diagram (PDF)</a>
  <a class="alt" href="#evidence">Design evolution</a>
</p>

<object class="arch-pdf" data="{{ '/assets/pdf/Arch1.pdf' | relative_url }}" type="application/pdf">
  <p><a href="{{ '/assets/pdf/Arch1.pdf' | relative_url }}">Open Arch1.pdf</a>.</p>
</object>

**On this page:** [Final class diagram](#class-v2) · [Behavioural diagrams](#seq-v2) · [CRC cards v2](#crc-v2) · [Design evolution](#evidence) · [Diagram sources](#sources)

## Final class diagram (version 2, 12 November 2026) {#class-v2}

<p><a href="{{ '/assets/arch/class-diagram-v2.pdf' | relative_url }}">Open full size (PDF, zoomable)</a> ·
   

<figure class="arch-fig">
  <a href="{{ '/assets/arch/v2/class-diagram-v2.svg' | relative_url }}"><img src="{{ '/assets/arch/v2/class-diagram-v2.png' | relative_url }}" alt="Final class diagram of Escape the Geese, grouped into presentation, logic and support layers"></a>
  <figcaption>Figure 1. Final class diagram. Blue = presentation, orange = logic, green = support. HUD's read-only links to GameTimer, Score, Inventory, ExhaustionMeter and WaveManager are omitted for clarity.</figcaption>
</figure>

| Layer | Classes | Responsibilities |
| --- | --- | --- |
| Presentation | Main, MenuScreen, TutorialScreen, GameScreen, EndScreen, HUD, GameResult | Switching screens, input, the pause menu, on-screen information and the win or loss screen |
| Logic | Player, Inventory, ExhaustionMeter, Item, Breadcrumbs, Pebble, Goose, GooseState, WaveManager, Event, ScoreBoost, GooseRush, Score | The rules of the game: movement, items, goose behaviour, waves, events and scoring |
| Support | GameMap, GameTimer, Settings | The campus map and its walls, the countdown, and volume and fullscreen options |
| Framework (LibGDX) | Game, Screen, SpriteBatch, Vector2, Rectangle | The main loop, rendering, input and geometry our classes build on |

## Behavioural diagrams (12 November 2026) {#seq-v2}

<figure class="arch-fig">
  <a href="{{ '/assets/arch/v2/seq-player-item.svg' | relative_url }}"><img src="{{ '/assets/arch/v2/seq-player-item.png' | relative_url }}" alt="Sequence diagram: player uses an item and clears a wave"></a>
  <figcaption>Figure 2. Player uses an item and clears a wave. Requirements: FR_ITEM_DISPERSE, FR_ITEM_TYPES, FR_ITEM_MISUSE, FR_SCORE_ITEMS, FR_SCORE_SPEED, FR_GEESE_WAVES, FR_WAVE_COUNTDOWN.</figcaption>
</figure>

<figure class="arch-fig">
  <a href="{{ '/assets/arch/v2/seq-gamescreen-frame.svg' | relative_url }}"><img src="{{ '/assets/arch/v2/seq-gamescreen-frame.png' | relative_url }}" alt="Sequence diagram: one GameScreen frame"></a>
  <figcaption>Figure 3. One GameScreen frame: pause, events, and the win and loss checks. Requirements: FR_PAUSE, FR_TIMER, FR_EXHAUSTION_METER, FR_EVENT_AUDIO, FR_EVENT_VISUAL, FR_WIN, FR_LOSE.</figcaption>
</figure>

<figure class="arch-fig">
  <a href="{{ '/assets/arch/v2/state-goose.svg' | relative_url }}"><img src="{{ '/assets/arch/v2/state-goose.png' | relative_url }}" alt="State machine for Goose" style="max-width:420px"></a>
  <figcaption>Figure 4. Goose state machine. Geese are distracted, enraged or dispersed, never harmed. Requirements: FR_ITEM_DISPERSE, FR_ITEM_MISUSE, CR_PEACE.</figcaption>
</figure>

## CRC cards, version 2 (12 November 2026) {#crc-v2}

<figure class="arch-fig">
  <a href="{{ '/assets/arch/v2/crc-v2.svg' | relative_url }}"><img src="{{ '/assets/arch/v2/crc-v2.png' | relative_url }}" alt="17 CRC cards grouped by layer"></a>
  <figcaption>17 classes in three layers. Each responsibility names the class it works with; these collaborations became the relationships in Figure 1.</figcaption>
</figure>

## Design evolution {#evidence}

Our architecture went through three versions: CRC cards (October), the first class and sequence diagrams (30 October), and the final design (12 November). The earlier versions are kept below with their content unchanged, as evidence of how the design developed. Section 3.2 of Arch1.pdf explains each change and the requirement behind it.

### CRC cards, version 1 (October 2026) {#crc-v1}

<div class="arch-note arch-old"><strong>Superseded.</strong> Game held eight responsibilities, Player asked "Health bar ?", and Score ended the game at 100% of geese dispersed. Version 2 split Game into Main and four screens, replaced health with an ExhaustionMeter, and moved the win to "every wave cleared".</div>

<figure class="arch-fig">
  <a href="{{ '/assets/arch/v1/crc-v1.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/crc-v1.png' | relative_url }}" alt="Six original CRC cards"></a>
</figure>

### Class diagrams, version 1 (30 October 2026) {#class-v1}

<div class="arch-note arch-old"><strong>Superseded on 12 November.</strong> Player and Goose had health, and Goose lost health from items. One Game class ran the timer, waves, events and the win check, and no relationships were drawn between classes. Replaced by Figure 1 above.</div>

<div class="arch-grid">
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/class-v1-fig1.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/class-v1-fig1.png' | relative_url }}" alt="Version 1 Game and Player classes"></a><figcaption>Figure 1 (v1). Game and Player</figcaption></figure>
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/class-v1-fig2.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/class-v1-fig2.png' | relative_url }}" alt="Version 1 Score and Event classes"></a><figcaption>Figure 2 (v1). Score and Event</figcaption></figure>
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/class-v1-fig3.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/class-v1-fig3.png' | relative_url }}" alt="Version 1 Goose and Item classes"></a><figcaption>Figure 3 (v1). Goose and Item</figcaption></figure>
</div>

### Sequence diagrams, version 1 (30 October 2026) {#seq-v1}

<div class="arch-note arch-old"><strong>Superseded on 12 November.</strong> Six overlapping scenarios built around the old Game class, including damage to the player and an "if item harms geese" branch. Merged into Figures 2 and 3 above, with Figure 4 added for goose behaviour.</div>

<div class="arch-grid">
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/seq-v1-fig4.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/seq-v1-fig4.png' | relative_url }}" alt="Version 1 player movement and item usage"></a><figcaption>Figure 4 (v1). Player movement and item usage</figcaption></figure>
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/seq-v1-fig5.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/seq-v1-fig5.png' | relative_url }}" alt="Version 1 goose dispersal and scoring"></a><figcaption>Figure 5 (v1). Goose dispersal and scoring</figcaption></figure>
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/seq-v1-fig6.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/seq-v1-fig6.png' | relative_url }}" alt="Version 1 event triggering and game completion"></a><figcaption>Figure 6 (v1). Event triggering and game completion</figcaption></figure>
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/seq-v1-fig7.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/seq-v1-fig7.png' | relative_url }}" alt="Version 1 goose behaviour and item effects"></a><figcaption>Figure 7 (v1). Goose behaviour and item effects</figcaption></figure>
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/seq-v1-fig8.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/seq-v1-fig8.png' | relative_url }}" alt="Version 1 item use and wave dispersal"></a><figcaption>Figure 8 (v1). Item use and wave dispersal</figcaption></figure>
  <figure class="arch-fig"><a href="{{ '/assets/arch/v1/seq-v1-fig9.svg' | relative_url }}"><img src="{{ '/assets/arch/v1/seq-v1-fig9.png' | relative_url }}" alt="Version 1 event triggering, item spawning and score modification"></a><figcaption>Figure 9 (v1). Event triggering, item spawning and score modification</figcaption></figure>
</div>

## Diagram sources {#sources}

Every diagram is generated from a text file, so its history is recorded in our repository.

- Final class diagram (Mermaid): [class-diagram-final.mmd]({{ '/assets/arch/sources/class-diagram-final.mmd' | relative_url }})
- Final sequence diagrams and state machine (PlantUML): [seq-player-item.puml]({{ '/assets/arch/sources/seq-player-item.puml' | relative_url }}), [seq-gamescreen-frame.puml]({{ '/assets/arch/sources/seq-gamescreen-frame.puml' | relative_url }}), [state-goose.puml]({{ '/assets/arch/sources/state-goose.puml' | relative_url }})
- Version 1 diagrams (PlantUML): `class-v1-fig1.puml` to `class-v1-fig3.puml` and `seq-v1-fig4.puml` to `seq-v1-fig9.puml` in `assets/arch/sources/`
- Change history: [commit history for these files](https://github.com/Sruthiksha-source/Escape-the-Geese-Web/commits/main/docs/assets/arch)
