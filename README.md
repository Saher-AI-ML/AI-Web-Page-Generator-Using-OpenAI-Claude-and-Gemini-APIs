# 🚀 AI Web Page Generator — OpenAI vs. Claude vs. Gemini

[![View on nbviewer](https://img.shields.io/badge/render-nbviewer-orange?logo=jupyter)](https://nbviewer.org/github/Saher-AI-ML/AI-Web-Page-Generator-Using-OpenAI-Claude-and-Gemini-APIs/blob/main/AI%20Web%20Page%20Generator%20Using%20OpenAI%2C%20Claude%2C%20and%20Gemini%20APIs.ipynb)

> **Note:** GitHub's built-in notebook preview occasionally fails to render fully (a known limitation of its third-party rendering pipeline, unrelated to the notebook itself). If some cells appear missing below, click the badge above to view the complete notebook on nbviewer.

Give it a startup name and a one-paragraph pitch — get back a fully designed,
production-style landing page in seconds. This notebook pits three of the world's
leading LLMs head-to-head, sending the exact same conversion-focused prompt to
**GPT**, **Claude**, and **Gemini** simultaneously and generating three complete,
styled, responsive HTML landing pages you can open and compare side by side.

No templates. No design tools. No manual coding. Just a startup concept in, three
launch-ready web pages out.

## How it works

1. **Define** — describe your startup: a name and a short concept paragraph.
2. **Prompt engineer** — a single, richly detailed prompt asks each model to act as a
   front-end developer and produce a complete, self-contained `index.html` file
   (header, hero, features, "How it Works," testimonials, pricing, and footer — all
   with inline CSS, responsive layout, hover effects, and animations).
3. **Generate in parallel** — the same prompt is sent to three different providers:
   - **OpenAI** (`gpt-4o-mini`, via OpenRouter)
   - **Google Gemini** (`gemini` generative model)
   - **Anthropic Claude** (`claude-sonnet` model)
4. **Compare** — each model's raw HTML response is cleaned up (code fences stripped),
   rendered inline in the notebook, and saved to its own file so you can benchmark
   design quality, copywriting, and code cleanliness across providers.

## Tools & Libraries used

| Tool / Library | Purpose |
|---|---|
| [OpenAI Python SDK](https://github.com/openai/openai-python) | Calls the OpenAI-compatible chat completions endpoint |
| [OpenRouter](https://openrouter.ai/) | Gateway used as the `base_url` for the OpenAI client |
| [Anthropic Python SDK](https://github.com/anthropics/anthropic-sdk-python) | Calls the Claude Messages API |
| [Google Generative AI SDK](https://ai.google.dev/) (`google-generativeai`) | Calls the Gemini API |
| [IPython](https://ipython.org/) | Renders generated HTML/Markdown output inline in the notebook |

## Output

Running the notebook produces three ready-to-open HTML files, one per provider:

```
gpt_gymsite.html
gemini_gymsite.html
claude_gymsite.html
```

Each is a complete, self-contained landing page — just open it in a browser.

## Setup

1. **Install dependencies:**
   ```bash
   pip install --upgrade openai anthropic google-generativeai
   ```

2. **Set your API keys** as environment variables (this notebook was built for Colab,
   which pulls secrets via `google.colab.userdata` — replace that with `os.environ`
   for local use):
   ```bash
   export OPENAI_API_KEY="your-key"
   export ANTHROPIC_API_KEY="your-key"
   export GOOGLE_API_KEY="your-key"
   ```

3. **Swap in your own client base URLs** if you're not routing through OpenRouter /
   a relay service — point them at the providers' native endpoints if preferred.

4. **Customize the pitch** — edit `startup_name` and `startup_concept` to generate a
   landing page for any product or business idea.

5. **Run all cells** and open the three generated HTML files to compare results.

## Why this is powerful

This isn't just "ask an AI for some HTML" — it's a structured, repeatable benchmark
that turns a single well-engineered prompt into a multi-model design bake-off,
giving you an instant, apples-to-apples view of which model produces the most
polished, conversion-ready front-end for your product.
