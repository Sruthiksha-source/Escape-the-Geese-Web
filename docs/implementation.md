---
layout: page
title: Implementation
---

Our implementation of *Escape the Geese* is documented in our Assessment 1 report, Impl1.pdf. This page gives access to the report, the source code and the executable JAR, with extracts of the code that show how key requirements were implemented.

**On this page:** [Implementation report](#implementation-report) · [Source code](#source-code) · [Executable JAR](#executable-jar) · [Implementation evidence](#implementation-evidence)

## Implementation report {#implementation-report}

Impl1.pdf lists the third-party libraries and assets we use with their licences, and every requirement that is not yet fully implemented, by requirement ID.

[Download Impl1.pdf]({{ '/assets/Impl1.pdf' | relative_url }})

<iframe src="{{ '/assets/Impl1.pdf' | relative_url }}" width="100%" height="800px" style="border: 1px solid #ddd; border-radius: 6px;" title="Implementation report (Impl1.pdf)"></iframe>

## Source code {#source-code}

*Escape the Geese* is written in Java 17 using the LibGDX framework, following the architecture in [Arch1.pdf]({{ '/assets/Arch1.pdf' | relative_url }}). The code is kept in Git on GitHub, where the commit history, issues and pull requests record how the game was developed.

**Repository:** [github.com/Sruthiksha-source/Escape-The-Geese.github.io](https://github.com/Sruthiksha-source/Escape-The-Geese.github.io)

## Executable JAR {#executable-jar}

The game is a single executable JAR that includes all of its libraries and needs no set-up (CR_JAR). It runs on Windows, macOS and Linux with Java 17 or later (CR_PLATFORMS, CR_JAVA).

[Download Escape-the-Geese-1.0.0.jar]({{ '/assets/Escape-the-Geese-1.0.0.jar' | relative_url }})

To run it, download the file and run this in a terminal from the download folder:

    java -jar Escape-the-Geese-1.0.0.jar

## Implementation evidence {#implementation-evidence}

These extracts show how three parts of the architecture were implemented. Each caption gives the source file and the requirements the code meets.

### Items: an abstract class with one subclass per item

<figure>
  <img src="{{ '/assets/impl/item-class.png' | relative_url }}" alt="Item.java: abstract Item class with an abstract apply method" width="100%" style="border: 1px solid #ddd; border-radius: 6px;">
  <figcaption><code>Item.java</code>. Item is abstract: it holds what every item shares (name, effect type, strength, duration, image and position), and declares <code>apply(target, geese)</code> without implementing it. Each item, such as <code>Birdseed</code> and <code>Bell</code>, overrides <code>apply()</code> with its own effect, so a new item is added as a new subclass without changing Player or Goose (FR_ITEM_TYPES, FR_ITEM_DISPERSE, QR_EXTENSIBILITY).</figcaption>
</figure>

### Waves: spawning each wave of geese

<figure>
  <img src="{{ '/assets/impl/wave-timer.png' | relative_url }}" alt="GooseGame.java: getNextWave method" width="100%" style="border: 1px solid #ddd; border-radius: 6px;">
  <figcaption><code>GooseGame.getNextWave()</code>. The game moves to the next wave and spawns one goose per place in that wave, at a valid position away from the player and clear of obstacles, until all five waves (3, 5, 7, 10 and 15 geese) have been spawned. Clearing the last wave is the win condition (FR_GEESE_WAVES, UR_GEESE, FR_WIN).</figcaption>
</figure>

### Timer: the 5-minute countdown on the HUD

<figure>
  <img src="{{ '/assets/impl/timer.png' | relative_url }}" alt="Main.java: getCountdownClock method" width="100%" style="border: 1px solid #ddd; border-radius: 6px;">
  <figcaption><code>Main.getCountdownClock()</code>. The time remaining is the game length (300 seconds) minus the time elapsed, formatted as minutes and seconds (for example 04:07) for the HUD, which shows it throughout play (FR_TIMER, FR_HUD_DISPLAY). The timer stops while the game is paused (FR_PAUSE).</figcaption>
</figure>
