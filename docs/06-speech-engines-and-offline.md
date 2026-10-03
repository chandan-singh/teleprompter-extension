# 06. Speech Engines & Offline Setup Guide

Teleprompter supports multiple Speech-to-Text (STT) engines for Voice-Sync mode. Whether you have reliable internet, require strict air-gapped privacy, or want maximum cloud accuracy, you can choose the engine that best fits your environment.

Navigate to **Settings** → **Voice & Speech Recognition** to select and configure your engine.

---

## Engine Comparison Matrix

| Feature               | 🌐 Web Speech API                | 💻 Whisper (Local In-Browser)  | ☁️ Remote OpenAI-Compatible   |
| :-------------------- | :------------------------------- | :----------------------------- | :---------------------------- |
| **Setup Required**    | None (Built-in)                  | 1-click model download         | Base URL + API Key            |
| **Offline Support**   | ❌ Requires Internet             | ✅ **100% Offline**            | ❌ Requires Network           |
| **Data Privacy**      | Audio processed by Google Speech | **Audio never leaves browser** | Sent to your chosen endpoint  |
| **Hardware Overhead** | Ultra-lightweight                | Moderate (uses WebGPU / WASM)  | Ultra-lightweight (remote)    |
| **Accuracy**          | High (English & Multilingual)    | High (English optimized)       | Highest (Whisper Large/Turbo) |
| **Cost**              | 100% Free                        | 100% Free                      | Free or Provider API fees     |

---

## 1. 🌐 Web Speech API (Built-in Default)

### Overview

The Web Speech API is Google Chrome’s built-in speech recognition system.

### Pros & Cons

- **Pros**: Zero initial setup or downloads. Works instantly out of the box. Supports 52+ spoken languages and dialects.
- **Cons**: Requires active internet connectivity. Some corporate firewall networks or secure offline environments block Chrome speech services.

### How to Use

1. Open **Settings** → **Voice & Speech Recognition**.
2. Select **Web Speech API (Built-in Chrome)**.
3. Choose your spoken language dialect (e.g., `English (US)`, `English (UK)`, `Spanish`, `French`, `German`, etc.).

---

## 2. 💻 Whisper Local (In-Browser Offline Engine)

### Overview

Teleprompter can run OpenAI's Whisper model directly inside your Chrome tab using client-side WebAssembly (WASM) and WebGPU acceleration.

### Why Choose Local Whisper?

- **100% Air-Gapped Offline**: Transcribes speech with no internet connection whatsoever. Perfect for flights, remote field locations, or backstage conference venues with spotty Wi-Fi.
- **Maximum Privacy**: Audio is processed purely in your computer's local memory (RAM) and never transmitted across the network.

### Model Options

- **Tiny (~40 MB download)**: Recommended for most laptops and desktops. Highly responsive with minimal CPU/GPU usage.
- **Base (~75 MB download)**: Slightly higher transcription fidelity for accents and technical terminology.

### First-Time Initialization

1. In **Settings** → **Voice & Speech Recognition**, select **Whisper (Local In-Browser)**.
2. Choose **Model Size** (`Tiny` or `Base`).
3. Click **Start** in the prompter. The browser will download the model files on the first run and cache them permanently in your local browser storage. Subsequent sessions start immediately with zero downloads.

---

## 3. ☁️ Remote OpenAI-Compatible Speech Endpoint

### Overview

If you have access to a remote Whisper API server (such as OpenAI's official audio transcription API, Groq Cloud, or a self-hosted Whisper ASR container), Teleprompter can stream audio chunks to it.

### Configuration

1. Open **Settings** → **Voice & Speech Recognition**.
2. Select **Remote OpenAI-Compatible Endpoint**.
3. Fill in your endpoint details:
   - **Base URL**: e.g., `https://api.openai.com/v1` or `https://api.groq.com/openai/v1`
   - **API Key**: Your provider secret key
   - **Model Name**: e.g., `whisper-1` or `whisper-large-v3-turbo`
4. Click **Test connection** to verify connectivity before presenting.

---

## 🎙️ Best Practices for Audio Clarity

Regardless of which engine you select, speech recognition accuracy depends on clear audio:

1. **Use an External Microphone**: A directional USB microphone, headset, or lavalier mic produces far better results than built-in laptop microphones picking up fan noise and room echo.
2. **Minimize Background Noise**: Close windows and avoid sitting directly in front of air conditioning units or loud cooling fans.
3. **Check Chrome Site Permissions**: Ensure Chrome has granted microphone permissions to the Teleprompter tab (`chrome://settings/content/microphone`).

---

## Next Steps

- Configure smart position recovery: [**07. AI Re-Anchoring Setup**](07-ai-reanchoring-setup.md)
- Troubleshoot microphone issues: [**08. Troubleshooting & FAQ**](08-troubleshooting-and-faq.md)
