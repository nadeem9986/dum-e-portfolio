# SEEDFILE - DUM-E portfolio robot arm

Durable context for this repo. Read this before changing anything.

## STATUS: CONCEPT ONLY - DO NOT BUILD YET

This repo captures an idea. No implementation until the owner has talked it
through. The moment this file exists, the next step is a conversation with
him about scope - not code.

## The concept

An interactive digital robot arm for his personal portfolio, inspired by
DUM-E - Tony Stark's claw-arm workshop assistant from Iron Man. The arm is
a character on the page: slightly clumsy, eager to help.

The headline interaction: when a visitor asks for his resume, the arm
animates in from off-screen, grabs a folder, opens it, and hands the resume
over to the visitor.

## Why it fits him

- Robotics is his hobby (RC cars, ESP32 builds) - a robot arm on the
  portfolio makes the "hardware guy becoming software guy" story visible.
- It is a conversation piece recruiters remember, built entirely in the
  browser.

## Design language (locked to his taste)

- Monochrome only: black base, grey/white elements. No hue, no chrome or
  metallic gradients.
- Typography: Departure Mono where text appears.
- Motion carries the personality, not color: small delays, slight
  overshoot, a "looking around" idle sway.

## Tech direction (proposal, not locked)

- Plain JS + CSS transforms for the arm articulation (segmented arm with
  inverse-kinematics-lite: each segment rotates, claw opens/closes).
- No framework requirement; must embed cleanly into the rebuilt portfolio.
- Keep the arm as SVG or DOM segments so it stays crisp and themeable.
- Resume source: link out to the actual resume PDF - the arm "handing it
  over" ends in the real file opening/downloading.
- Performance budget: idle animation must not jank the page; respect
  prefers-reduced-motion (arm stays parked, resume link renders normally).

## Interaction beats (draft)

1. Idle: arm parked at screen edge, occasional small sway.
2. Trigger: visitor clicks "Resume" (or asks for it).
3. Arm swings in, pauses ("looking at" the visitor), reaches for a folder.
4. Folder opens; arm presents the resume card toward the screen.
5. Resume opens; arm retreats to idle.

## Open questions for the owner

1. Which portfolio does this ship in - the rebuilt n4deem.site? Same repo
   or a component package?
2. SVG segments or pure DOM/CSS boxes for the arm?
3. Should the arm do more than resume handover (wave on load, react to
   scroll, celebrate on contact-form submit)?
4. Name the arm? DUM-E is Marvel's character - an original name avoids the
   trademark and gives it its own identity.
