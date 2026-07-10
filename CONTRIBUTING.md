# Contributing to Line Follower Robot (LFR)

Thanks for your interest in improving this project! This document outlines how to contribute effectively.

## Getting Started

1. **Fork** the repository and clone your fork locally.
2. Install the [Arduino IDE](https://www.arduino.cc/en/software) and the Arduino Nano board driver.
3. Review the [Control Logic](README.md#-control-logic) and [Working Flowchart](README.md#-working-flowchart) sections in the README before modifying the control code — most changes should preserve the core 5-sensor decision logic unless you're explicitly improving it.

## Branching & Commits

- Create a feature branch off `main`:
  ```bash
  git checkout -b feature/short-description
  ```
- Use clear, present-tense commit messages, e.g. `Tune PID gains for tighter curve tracking`.
- Keep commits focused — one logical change per commit where possible.

## Code Style

- Keep sensor-reading, decision logic, and motor-control code clearly separated (mirrors the block diagram: **Sensors → Arduino → Motor Driver → Motors**).
- Comment any changes to PID gains (`Kp`, `Ki`, `Kd`) or IR threshold calibration values, and note the track/lighting conditions they were tuned for.
- Avoid hard-coding pin numbers inline — define them as named constants at the top of the sketch.

## Testing Before You Submit

- Test on a physical track covering: a straight segment, at least one curve, a left turn, a right turn, and a dead end/end-of-path.
- Verify behavior under at least two different lighting conditions if you touch sensor calibration.
- If you change PID gains, note before/after tracking stability (e.g., oscillation, overshoot on turns).

## Submitting a Pull Request

1. Push your branch to your fork.
2. Open a PR against `main` with:
   - A clear title and description of the change
   - A short video or photos demonstrating the change on the track (add to `Assets/`)
   - Any updated PID/threshold values and the conditions they were tested under
3. Link any related issue with `Closes #<issue-number>`.

## Reporting Bugs / Requesting Features

Please open a GitHub Issue with:
- Steps to reproduce (for bugs), including track/surface/lighting conditions
- Expected vs. actual robot behavior
- Photos or video if applicable

## Code of Conduct

Be respectful and constructive. This is an academic/portfolio project — feedback and improvements are always welcome.
