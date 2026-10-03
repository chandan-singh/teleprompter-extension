# 05. Rehearsal & Pacing Analytics Guide

Going over your allotted speaking time is one of the most common presentation pitfalls. Teleprompter includes a dedicated **Rehearsal Mode** with real-time pacing alerts and automated post-session performance analytics to help you master your timing.

---

## 1. What is Rehearsal Mode?

Unlike normal prompter mode where you simply read text, **Rehearsal Mode** acts as an intelligent speech coach:

- It tracks the exact time spent on each individual paragraph (lap timing).
- It compares your current pace against your target finish time.
- It displays non-intrusive pacing alerts if you start falling behind.
- When you finish, it generates a comprehensive **Rehearsal Performance Report**.

---

## 2. Setting Up a Rehearsal Session

1. In your script library, locate the script you want to practice.
2. Click the **Rehearse** button (or launch the player and press `T` to set target time).
3. Specify your **Target Time**:
   - For example: `05:00` for a 5-minute lightning talk, or `15:00` for a keynote.
   - The app immediately calculates the exact target words-per-minute (WPM) needed to finish comfortably within that window.
4. Press **Start Rehearsal** (or hit `Space`).

---

## 3. Real-Time Lap Tracking & Pacing Alerts

As you speak or advance through the script:

- Every time you cross a paragraph boundary, Teleprompter automatically records a **lap timestamp**.
- **The Pacing Alert Banner**:
  - **🟢 On Pace**: You are within your projected time window.
  - **🟡 Slight Drift**: You are trending slightly slower than planned (projected 10–20% overtime).
  - **🔴 Overtime Warning**: If you spend too much time on an introductory point, an alert banner notifies you that your projected finish will exceed your time slot.
  - **Quick Action**: The alert gives you immediate options: you can pick up your pace, skip a paragraph, or (if AI is configured) click "Condense remaining" to trim excess words automatically.

---

## 4. Reading the Rehearsal Performance Report

When you reach the end of your script or press `Esc`, Teleprompter presents your **Rehearsal Report**:

### Key Summary Metrics

- **Total Duration**: Actual time taken vs. Target time (e.g., `04:52` vs `05:00`).
- **Average Speaking Rate**: Your true delivery speed across the talk (e.g., `142 WPM`).
- **Pacing Consistency Score**: Measures whether you maintained a steady rhythm or rushed through the end to beat the clock.

### Paragraph-by-Paragraph Breakdown Table

The report lists every paragraph in your presentation with color-coded status badges:

|     Paragraph #     | Word Count | Target Time | Actual Time | Pace Delta |       Status       |
| :-----------------: | :--------: | :---------: | :---------: | :--------: | :----------------: |
|   **P1 — Intro**    |  85 words  |    00:36    |    00:34    |    -2s     |    🟢 On Track     |
|  **P2 — Problem**   | 140 words  |    01:00    |    01:25    |    +25s    | 🔴 Slow (Overtime) |
|  **P3 — Solution**  | 120 words  |    00:51    |    00:48    |    -3s     |    🟢 On Track     |
| **P4 — Conclusion** |  95 words  |    00:40    |    00:37    |    -3s     |    🟢 On Track     |

- **Green Rows**: Delivered cleanly within predicted time.
- **Red Rows**: Identifies the exact sections where you paused too long, improvised, or spoke too slowly.

---

## 5. Iterative Practice Workflow

Use this 3-step workflow to prepare for high-stakes presentations:

1. **Run 1 (Baseline)**: Read naturally without watching the clock. Check the Rehearsal Report to identify which specific paragraphs ran long.
2. **Edit Script or Adjust Delivery**: Shorten wordy sentences in problem paragraphs, or insert `[fast]` or `[pause 1s]` cues.
3. **Run 2 (Validation)**: Rehearse again. Compare your new report against the previous session to ensure all red rows turn green.

---

## Next Steps

- Learn about the available speech recognition engines: [**06. Speech Engines & Offline Setup**](06-speech-engines-and-offline.md)
- Set up intelligent AI re-anchoring: [**07. AI Re-Anchoring Setup**](07-ai-reanchoring-setup.md)
