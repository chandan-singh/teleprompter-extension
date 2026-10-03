# 07. AI Re-Anchoring Setup Guide

When speaking live, it is natural to occasionally deviate from your prepared script—whether to answer an unexpected audience question, tell a spontaneous anecdote, or skip ahead when running low on time.

While Teleprompter's built-in fuzzy matcher easily handles minor phrasing differences, major digressions can cause standard speech trackers to lose their place. **AI Re-Anchoring** solves this by consulting a Large Language Model (LLM) to determine where you jumped to and smoothly restore your scroll position.

---

## 1. How AI Re-Anchoring Works

1. **Detection**: If Voice-Sync detects low matching confidence for several consecutive seconds, it flags the cursor status as "Searching".
2. **Context Window**: Teleprompter packages the last few phrases transcribed from your microphone alongside a window of your script.
3. **LLM Consultation**: The AI analyzes the spoken words and locates the exact matching sentence in the script.
4. **Local Verification Guardrail**: Teleprompter **never** blindly jumps to an LLM's guess. It takes the AI's estimated quote and runs it through the local fuzzy matcher to verify that the text genuinely exists in your script.
5. **Throttled**: AI queries are rate-limited to at most once every 5 seconds to prevent network spam and keep token consumption minimal.

---

## 2. Choosing an AI Provider

You can power AI Re-Anchoring using either **100% local, offline AI** on your own computer or **cloud AI APIs**.

Configure your provider in **Settings** → **AI Alignment & Re-Anchoring**:

### Option A: 100% Local Offline AI (Free & Private)

Run open-source models (like Llama 3, Mistral, or Qwen) locally on your computer with zero data sent over the internet:

#### 1. Ollama

- **Base URL**: `http://localhost:11434/v1`
- **API Key**: Leave blank (not required)
- **Model**: e.g., `llama3.2`, `mistral`, or `qwen2.5`
- **Important (CORS Configuration)**: Because Chrome extensions make browser cross-origin requests, you must start Ollama with origins enabled:
  ```bash
  OLLAMA_ORIGINS="*" ollama serve
  ```

#### 2. LM Studio

- **Base URL**: `http://localhost:1234/v1`
- **API Key**: Leave blank
- **Model**: Any loaded chat model
- **Important**: In LM Studio's Local Server settings tab, toggle **CORS** to **ON** and allow `chrome-extension://*` origins.

---

### Option B: Cloud AI Providers

If you prefer cloud models with zero local hardware setup:

| Provider              | Preset Base URL                                    | Recommended Model            |
| :-------------------- | :------------------------------------------------- | :--------------------------- |
| **OpenAI**            | `https://api.openai.com/v1`                        | `gpt-4o-mini`                |
| **Anthropic**         | `https://api.anthropic.com/v1`                     | `claude-3-5-haiku-latest`    |
| **Google Gemini**     | `https://generativelanguage.googleapis.com/v1beta` | `gemini-1.5-flash`           |
| **OpenAI-Compatible** | Custom URL (e.g., Groq, Together, DeepSeek)        | `llama-3.1-8b-instant`, etc. |

---

## 3. Step-by-Step Setup

1. Open **Settings** (gear icon in the top right).
2. Scroll to **AI Alignment & Re-Anchoring**.
3. Toggle **Enable AI Re-Anchoring** to **ON**.
4. Select your **Provider** from the dropdown.
5. Enter your **Base URL**, **API Key**, and **Model Name** (preset buttons will auto-fill the standard values).
6. Click the **Test connection** button:
   - 🟢 **Success**: Shows round-trip latency (e.g., `Connected (142 ms)`).
   - 🔴 **Error**: Displays the exact HTTP error code (e.g., `401 Unauthorized` for bad key, or `CORS blocked` for local server).

---

## 4. Privacy & API Key Security

- **Strictly Local Storage**: Your API keys are stored solely inside your browser's encrypted local storage (`chrome.storage.local`).
- **Direct Requests**: API calls are made directly from your browser to the designated provider URL. No intermediate proxy or telemetry server is ever involved.
- **Wipe Anytime**: Clicking "Restore defaults" in Settings or removing the extension permanently erases all stored keys.

---

## Next Steps

- Troubleshoot common errors: [**08. Troubleshooting & FAQ**](08-troubleshooting-and-faq.md)
- Submit feedback or ask questions: [**09. Feedback & Support**](09-feedback-and-support.md)
