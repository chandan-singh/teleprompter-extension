# Privacy Policy for Teleprompter Chrome Extension

**Last updated:** October 3, 2026  
**Extension Name:** Teleprompter  

---

## 1. Overview & Core Commitment

Teleprompter ("we", "our", or "the extension") is a privacy-first, offline-capable Google Chrome Extension designed for presenters, public speakers, educators, and video creators.

We believe that privacy is a fundamental human right. **Teleprompter does not collect, track, sell, or transmit any personally identifiable information (PII) or behavioral analytics to any first-party or third-party advertising servers.** All application logic, scripts, user preferences, and rehearsal reports reside strictly on your local machine.

---

## 2. Single Purpose & Data Minimization

Teleprompter has a single, narrow purpose:

> _Displays and auto-scrolls presentation scripts synchronized with the speaker's voice or configurable words-per-minute pace for video recordings and public speaking._

Every permission requested by the extension is strictly required to deliver this core teleprompting experience.

---

## 3. Permissions & Data Access

Teleprompter requests only the minimum permissions necessary under Google Chrome Manifest V3:

### 3.1. `storage` Permission

- **Purpose**: Persists your scripts, display configurations (font size, words-per-minute speed, reading guide position, dark/light theme, date format), custom tags, and rehearsal pacing reports.
- **Where Data is Kept**: Stored solely on your computer inside Chrome's sandboxed local extension storage (`chrome.storage.local`).
- **Data Sharing**: Never uploaded to any cloud database or telemetry server.

### 3.2. `microphone` Permission

- **Purpose**: Required exclusively when you actively choose to use the **Voice-Sync** teleprompting mode or the microphone test in the Quick Start sandbox.
- **How Audio is Handled**:
  - Audio captured from your microphone is processed **in real-time in temporary computer memory (RAM)** to match spoken words to your script.
  - **No Audio Recording**: Audio is never recorded to disk, never saved to persistent storage, and never transmitted to our servers.
  - **Local Processing**: Transcriptions are performed either by your browser's native Web Speech engine or locally on your device via in-browser WebAssembly/WebGPU (Whisper).
  - **Instant Release**: Microphone streams are immediately stopped and released the moment you pause playback, switch to WPM or Paragraph mode, or exit the presentation screen. Chrome’s native tab microphone indicator always clearly displays when the microphone is in use.

### 3.3. Host Permissions (`https://*/*`, `http://localhost/*`, `http://127.0.0.1/*`)

- **Purpose**:
  1. **User-Initiated Script Import**: Allows you to import public plain text or Google Docs documents from URLs you explicitly paste into the import box.
  2. **User-Configured AI & STT Providers**: Allows advanced users to optionally connect their own API keys for remote LLM speech re-anchoring or cloud speech-to-text endpoints (e.g., OpenAI, Anthropic, Google Gemini, Groq, xAI, Cohere, Azure OpenAI, or AWS Bedrock).
  3. **Local Offline AI**: Allows connecting to local offline AI instances (e.g., Ollama or LM Studio) running on `http://localhost` or `http://127.0.0.1` without sending data over the internet.
- **Data Sharing**: Outbound network requests occur **only** when initiated by you (either by testing/running an AI re-anchor provider or importing a script from a URL). Your API keys are encrypted in your local browser storage and communicated directly to the respective third-party provider endpoint over HTTPS.

---

## 4. No Remote Code Execution

In accordance with Chrome Web Store Manifest V3 policies:

- Teleprompter **does not use, download, or execute remote code**.
- All JavaScript bundles, React components, CSS stylesheets, icons, and WebAssembly binaries (ONNX Runtime / Whisper) are packaged and verified directly within the extension package (`dist/`).

---

## 5. Third-Party AI Providers (Optional Feature)

Teleprompter does not run any intermediary servers. If you choose to configure an external AI provider (such as OpenAI, Anthropic, or Google Gemini) for optional speech re-anchoring:

- Network requests are sent directly from your browser to the chosen provider's official API endpoint.
- Your credentials and prompt requests are subject to the terms and privacy policy of that provider.
- Teleprompter developers have zero visibility into your API keys, prompts, or transcript snippets.

---

## 6. Data Retention, Control & Deletion

You maintain complete control over all data stored by the extension:

- **Individual Script Deletion**: You can delete any script at any time from the script manager.
- **Clear Settings & API Keys**: You can remove or modify any API key in the Settings modal, or click **Restore defaults** to wipe all stored preferences.
- **Full Data Erasure**: Removing or uninstalling Teleprompter from Chrome (`chrome://extensions` → **Remove**) instantly and permanently erases all scripts, settings, rehearsal logs, and cached data from your computer.

---

## 7. Children’s Privacy

Teleprompter does not collect, solicit, or maintain data from anyone, including children under the age of 13, in compliance with COPPA (Children's Online Privacy Protection Act) and similar international regulations.

---

## 8. Data Sale & Commercial Use Certification

In compliance with Chrome Web Store Developer Program Policies:

- We **do not sell** user data to third parties.
- We **do not use or transfer** user data for purposes unrelated to the extension's single core function.
- We **do not use or transfer** user data to determine creditworthiness or for lending purposes.

---

## 9. Contact & User Feedback

If you have questions about this Privacy Policy, wish to report an issue, or want to submit feedback or feature requests:

- **Feedback & Bug Report Form**: [Teleprompter Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSe34ekGVdynD4YGC6GfHk-nqMhOSlxdULjd3iaSrR-wBe_fKw/viewform?usp=publish-editor)
- **GitHub Repository**: [https://github.com/chandan-singh/teleprompter-extension](https://github.com/chandan-singh/teleprompter-extension)
