# 08. Troubleshooting & FAQ Guide

Encountering an issue? This guide covers the most common questions and fixes.

---

## 🛠️ Step 1: Run System Diagnostics

Teleprompter includes a built-in health diagnostic tool:

1. Click the **Help & Docs** icon (`F1`) in the top navigation bar.
2. Select **System Diagnostics**.
3. Click **Run diagnostics**.

The diagnostics panel probes your browser environment and displays:

- **Microphone Permission**: Granted vs. Blocked.
- **Web Speech API**: Available vs. Unavailable.
- **WebGPU / WebAssembly**: Checked for local Whisper capability.
- **Storage Subsystem**: Verifies local persistence.
- **Active AI Provider**: Checks reachability and response latency.

---

## 2. Microphone & Audio Issues

### Symptom: "Microphone permission denied" or engine will not start

#### How to Fix:

1. Look at the left side of Chrome's address bar on the Teleprompter tab.
2. Click the **tune / padlock icon** (View site information).
3. Find **Microphone** and switch the toggle to **Allow**.
4. Reload the tab (`Cmd + R` on Mac, `Ctrl + R` on Windows).
5. **Alternative**: In Chrome, open `chrome://settings/content/microphone` and verify that the Teleprompter extension origin is listed under "Allowed to use your microphone".

### Symptom: Microphone is allowed, but no words are being recognized

- **Check Default Input Device**: If you have multiple microphones (e.g., laptop internal mic, USB webcam, AirPods, external audio interface), Chrome may be listening to the wrong device. In Chrome, go to `chrome://settings/content/microphone` and select your primary microphone from the dropdown.
- **Background Noise**: Loud background noise, desk fans, or ambient music can drown out speech. Use an external USB mic or headset for the clearest signal.

---

## 3. Voice-Sync Drift & Lost Tracking

### Symptom: The highlighted word lags behind, skips ahead, or gets stuck

#### How to Fix:

1. **Manual Re-Anchor**: Click the **Re-anchor** button in the HUD to instantly snap the cursor to your last heard phrase.
2. **Nudge Position**: Tap `↓` or `↑` to manually adjust your position by ~3 words without stopping.
3. **Turn on AI Re-Anchoring**: If you frequently improvise or skip slides, enable AI Re-Anchoring in Settings so an LLM can re-orient you automatically.
4. **Switch to Paragraph Mode**: For presentations with repeated phrases or slide decks with lots of ad-libbing, **Paragraph Mode** gives you 100% deterministic control with zero drift.

---

## 4. Local Whisper & WebAssembly Issues

### Symptom: Whisper model fails to download or throws WebAssembly errors

#### How to Fix:

1. **Wait for First-Time Download**: Local Whisper downloads model files on its very first run (~40 MB for "Tiny", ~75 MB for "Base"). Ensure you have an active internet connection during this initial setup. Once downloaded, it is cached and works 100% offline.
2. **Enable Hardware Acceleration**:
   - In Chrome, open `chrome://settings/system`.
   - Ensure **Use graphics acceleration when available** is toggled **ON**.
   - Restart Chrome.
3. **Corporate / Managed Browser Restrictions**: Some enterprise networks restrict WebAssembly (WASM) evaluation for security reasons. If your company laptop blocks WASM, switch to the built-in **Web Speech API** or a **Remote OpenAI-compatible endpoint**.

---

## 5. AI Connection Errors

### Symptom: "Test connection" fails or returns an error

| Error                        | Root Cause                                  | Solution                                                                                                  |
| :--------------------------- | :------------------------------------------ | :-------------------------------------------------------------------------------------------------------- |
| **CORS Blocked (Localhost)** | Ollama / LM Studio rejecting browser origin | Start Ollama with `OLLAMA_ORIGINS="*" ollama serve`. In LM Studio, turn ON CORS in local server settings. |
| **401 Unauthorized**         | Invalid or expired API Key                  | Double-check that you copied the complete API key without leading/trailing spaces.                        |
| **404 Not Found**            | Incorrect Base URL or Model Name            | Use the provider preset buttons in Settings, and verify your account has access to the specified model.   |
| **Network Error**            | Firewall or VPN blocking endpoint           | Verify internet connectivity or test with a local server like Ollama.                                     |

---

## 6. Pacing & Choppy Scrolling

### Symptom: Scrolling feels jerky or moves too fast

#### How to Fix:

1. **Calibrate Your True WPM**: Run the **WPM Calibration Wizard** (accessible from Settings → Default WPM) to measure your natural speaking tempo. Conversational speaking is typically **120–150 WPM**.
2. **Adjust Font Size**: Extremely large font sizes (e.g., 90px+ on small laptop screens) mean fewer words fit per line, causing scrolling jumps to appear larger. Use the **Distance Font Calculator** to pick an optimal size.
3. **Check Target Time**: If you set a 5-minute target on a 1,500-word script, the prompter is forced to scroll at 300 WPM to finish in time! Check your script word count and target duration.

---

## 7. File Import Issues

### Symptom: An imported document comes through blank or garbled

#### How to Fix:

1. **Clean DOCX**: Save your file as a clean `.docx` without password protection, macros, or complex nested table layouts.
2. **Google Docs**: In Google Docs, go to **File** → **Download** → **Microsoft Word (.docx)** or **Plain text (.txt)** before importing.
3. **Fallback**: Copy the text from your document and paste it directly into the **+ New Script** editor.

---

## ❓ Frequently Asked Questions (FAQ)

### Can I use Teleprompter completely offline?

**Yes.** All script storage, paragraph click-through, and WPM auto-scroll work completely offline. For voice tracking, select **Whisper (Local In-Browser)** in Settings to run speech recognition 100% offline without internet.

### Does Teleprompter record or store my audio?

**No.** Audio captured from your microphone is processed strictly in temporary computer memory (RAM) for real-time speech matching and is discarded immediately. It is never recorded, saved to disk, or uploaded to any first-party server.

### Where are my scripts saved?

All scripts, custom tags, display settings, and rehearsal performance reports are stored exclusively on your local computer using Chrome's built-in local storage (`chrome.storage.local`).

### Can I use a wireless presenter remote?

**Yes.** Standard USB/Bluetooth presentation clickers map to `Space`, `Enter`, or Arrow keys, which Teleprompter supports out of the box.

---

## Next Steps

- Reach out to community support: [**09. Feedback & Support**](09-feedback-and-support.md)
