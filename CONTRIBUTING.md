# Contributing to AI-Box

## Adding a New Model
1. Add a new panel section in `index.html`
2. Add the API call function following the existing pattern
3. Wire up the API key input to localStorage
4. Handle streaming if the model supports it

## Supported Model Endpoints
- Claude: `https://api.anthropic.com/v1/messages`
- Gemini: `https://generativelanguage.googleapis.com/v1beta/models/`
- DeepSeek: `https://api.deepseek.com/chat/completions`
