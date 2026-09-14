# Laxman AI — Khoj Workspace

This folder is the static frontend for the Laxman AI workspace.

## Architecture

```text
apps.laxmannepal.com.np/ai
        │
        ▼
   Laxman AI UI
        │ HTTPS
        ▼
ai.laxmannepal.com.np  ← self-hosted Khoj (Google Colab for now)
        │
        ├── GitHub knowledge
        ├── Google Drive / personal documents
        └── configured AI model
```

## Current status

- Frontend: ready in `index.html`, `style.css`, `app.js`
- Khoj chat endpoint: `/api/chat`
- The frontend does **not** contain API keys.
- The backend URL is stored locally in the browser and can be changed with **Connect Khoj**.

Khoj's current self-hosted API uses `POST /api/chat`; its official code/examples also show optional Bearer authentication and parameters such as `q`, `n`, `conversation_id`, and `create_new`.

## $0 Colab plan

1. Start Khoj in Google Colab.
2. Keep its data/configuration on Google Drive where practical.
3. Expose port `42110` through Cloudflare Tunnel.
4. Use the generated HTTPS hostname as the backend URL in **Connect Khoj**.
5. Later move the same setup to a stable `ai.laxmannepal.com.np` Cloudflare Tunnel.

### Important

Google Colab is suitable for testing/personal use, but it is not guaranteed 24/7 hosting. Runtime restarts will require the backend to be started again.

Do not put OpenAI, Gemini, Groq, Hugging Face, or other provider secrets in this GitHub frontend.
