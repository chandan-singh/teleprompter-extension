# teleprompter-extension
Chrome Extension - Teleprompter
# Teleprompter Help Center & User Guide

Welcome to the **Teleprompter** documentation and support hub!

Teleprompter is a privacy-first, offline-capable Google Chrome Extension designed for public speakers, content creators, keynote presenters, educators, and video producers. It runs entirely inside your browser in a dedicated, distraction-free tab.

---

## 📚 Documentation Index

Find step-by-step guides, configuration tips, and troubleshooting solutions below:

| Guide                                                                      | Description                                                                                    |
| :------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------- |
| [**01. Getting Started**](./docs/01-getting-started.md)                           | How to install, launch the app, create your first script, and test in the sandbox.             |
| [**02. Prompter Modes Guide**](./docs/02-modes-guide.md)                          | Detailed walkthrough of Voice-Sync, WPM Auto-Scroll, and Paragraph Click-Through.              |
| [**03. Keyboard Shortcuts**](./docs/03-keyboard-shortcuts.md)                     | Complete hands-free keyboard shortcuts cheat sheet for presentation remotes and keyboards.     |
| [**04. Camera & Display Setup**](./docs/04-camera-and-display-setup.md)           | Eye-contact alignment, reading line presets, font calculator, and script annotations.          |
| [**05. Rehearsal & Pacing**](./docs/05-rehearsal-and-pacing.md)                   | How to set target times, track paragraph lap times, and read post-session pacing reports.      |
| [**06. Speech Engines & Offline Setup**](./docs/06-speech-engines-and-offline.md) | Comparing Web Speech, in-browser Local Whisper (offline), and remote speech engines.           |
| [**07. AI Re-Anchoring Setup**](./docs/07-ai-reanchoring-setup.md)                | Setting up local AI (Ollama / LM Studio) or cloud LLMs to recover your place if you improvise. |
| [**08. Troubleshooting & FAQ**](./docs/08-troubleshooting-and-faq.md)             | Solutions for microphone permissions, speech drift, choppy scrolling, and file import.         |
| [**09. Feedback & Support**](./docs/09-feedback-and-support.md)                   | How to report bugs, suggest features, and reach community support.                             |

---

## ⚡ Quick Reference

### The 3 Core Modes

- **🎤 Voice-Sync Mode**: Follows your spoken words in real time using speech recognition. Pause to answer questions or take a sip of water — the prompter automatically halts and resumes when you speak.
- **⏱️ WPM Auto-Scroll**: Rolls the script at a steady, configurable words-per-minute pace (e.g., 140 WPM). Adjust speed on the fly with `+` and `-`.
- **📄 Paragraph Click-Through**: Advances one slide cue or paragraph at a time on `Space` or click. Ideal for structured slide decks and keynotes.

### Essential Keyboard Shortcuts

- **`Space`**: Play / Pause (or Advance paragraph in Paragraph mode)
- **`↓` / `↑`**: Nudge text forward or backward by ~3 words
- **`+` / `-`**: Increase or decrease scrolling speed (±10 WPM)
- **`[` / `]`**: Move the horizontal reading line up or down
- **`R`**: Restart the presentation from the beginning
- **`Esc`**: Exit the prompter and return to your script library
- **`?`**: Show in-player shortcut cheat sheet

---

## 🔒 Privacy & Local Storage

- **100% Local**: Scripts, settings, rehearsal logs, and tags are stored strictly in your browser (`chrome.storage.local`).
- **No Cloud Telemetry**: Teleprompter never collects, tracks, or sells user data. No user accounts or logins required.
- **Microphone Privacy**: Audio from your microphone is analyzed strictly in temporary memory (RAM) for real-time speech matching and is never recorded or saved to disk.
- [Read our full Privacy Policy](./PRIVACY_POLICY.md)

---

## 💬 Community & Help

- **Submit Feedback or Report a Bug**: [Teleprompter Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSe34ekGVdynD4YGC6GfHk-nqMhOSlxdULjd3iaSrR-wBe_fKw/viewform)
- **GitHub Issues**: [Open an issue on GitHub](https://github.com/chandan-singh/teleprompter-extension/issues)
