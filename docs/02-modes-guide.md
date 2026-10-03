# 02. Prompter Modes Guide

Teleprompter provides three operating modes engineered for different presentation environments, recording setups, and speaking styles. You can switch modes at any time before or during a presentation from the mode dropdown in the top bar.

---

## 1. 🎤 Voice-Sync Mode (Follows Your Speech)

### What It Does

Voice-Sync mode listens to your microphone and automatically tracks your spoken words against your script in real time. As you speak each word, the prompter highlights it and smoothly scrolls the text up to keep your reading position aligned with your camera guide line.

### Key Capabilities

- **Pause & Resume Freely**: Take a sip of water, wait for audience applause, or answer an unexpected question — scrolling pauses instantly when you stop speaking and resumes smoothly the moment you start again.
- **Natural Cadence**: Whether you speed up during an energetic section or slow down for dramatic emphasis, the prompter moves at your pace, not a fixed timer.
- **Visual Confidence Indicator**: A subtle status pill in the HUD displays recognition health (Green = Synced, Amber = Searching, Red = Lost).
- **Manual Nudge & Re-Anchor**:
  - Press `↓` or `↑` at any time to manually nudge the script forward or backward by ~3 words.
  - If you jump around or skip text, click the HUD **Re-anchor** button to snap the cursor back to your last spoken phrase.
- **Optional AI Re-Anchoring**: When enabled, if you improvise heavily or skip an entire page, the prompter can consult an on-device or cloud LLM to find where you jumped to.

### Best Used For

- Keynotes and live webinars.
- Interactive podcasts and Q&A sessions.
- Speakers who dislike feeling rushed by automated timers.

---

## 2. ⏱️ WPM Auto-Scroll Mode (Continuous Speed)

### What It Does

WPM Auto-Scroll scrolls your script continuously at a predictable, constant words-per-minute (WPM) rate. It uses a high-performance requestAnimationFrame (rAF) animation loop to deliver smooth, pixel-by-pixel scrolling without jitter or tearing.

### Key Capabilities

- **Configurable Speed**: Set your baseline speaking speed (default is **140 WPM**).
- **On-the-Fly Speed Adjustments**: Speed up or slow down during your talk using the keyboard shortcuts `+` / `=` (+10 WPM) and `-` / `_` (-10 WPM), or via the HUD controls.
- **Target Time Pacing**: Press `T` or click the ⏱ pill to assign an allocated presentation duration (e.g., a 10-minute conference slot). The player computes the exact target scroll rate to finish within your allotted time and displays time remaining.
- **WPM Calibration Wizard**: Unsure of your speaking pace? Run the built-in WPM Calibration Wizard (accessible from Settings) to read a short passage and measure your natural pace.

### Best Used For

- Timed presentations (e.g., 5-minute lightning talks, TED-style presentations, broadcast news).
- Video creators recording YouTube videos or course lectures who want a consistent, lively delivery rhythm.

---

## 3. 📄 Paragraph Click-Through Mode (Step-by-Step)

### What It Does

Paragraph mode splits your presentation into individual cards or bullet blocks. The prompter remains stationary until you trigger the next point.

### Key Capabilities

- **Step Forward / Backward**: Press `Space`, `Enter`, or the `→` (Right Arrow) key to animate smoothly to the next paragraph. Press `←` (Left Arrow) to jump back to the previous point.
- **Zero Drift**: Eliminates any possibility of the prompter scrolling ahead of you while you explain a complex visual slide.
- **Slide Alignment**: Each paragraph can correspond directly to a slide in your deck (e.g., PowerPoint, Keynote, Google Slides).

### Best Used For

- Slide-deck presentations where you talk freely on each slide before advancing.
- Boardroom pitches and investor presentations.
- Scripts containing structured bullet points, product demos, or code walkthroughs.

---

## Mode Comparison Summary

| Feature                 | 🎤 Voice-Sync          | ⏱️ WPM Auto-Scroll   | 📄 Paragraph Mode          |
| :---------------------- | :--------------------- | :------------------- | :------------------------- |
| **Pacing Control**      | Driven by your voice   | Driven by target WPM | Driven by keyboard/click   |
| **Microphone Required** | Yes                    | No                   | No                         |
| **Speech Tracking**     | Word-by-word           | Constant scrolling   | Block-by-block             |
| **Pause Mechanism**     | Automatic (on silence) | Manual (`Space`)     | Built-in (waits for click) |
| **Best For**            | Speeches, webinars     | Timed talks, YouTube | Slide decks, pitches       |

---

## Next Steps

- See the full keyboard control mapping: [**03. Keyboard Shortcuts**](03-keyboard-shortcuts.md)
- Learn how to rehearse with pacing analytics: [**05. Rehearsal & Pacing**](05-rehearsal-and-pacing.md)
