# MedQuiz AI — deploy to Safari

## What this version does
- Accepts PPTX and PDF uploads.
- Extracts slide/page text.
- Sends the material to the OpenAI Responses API from the server.
- Generates UKMPPD-style practice questions, option-by-option explanations, high-yield notes, and flashcards.
- Serves the same responsive UI to iPhone Safari.

## Required
1. An OpenAI API key.
2. A Python hosting service that can run Flask/Gunicorn (Render, Railway, Fly.io, etc.).
3. Set environment variable OPENAI_API_KEY on the hosting service.
4. Optional: OPENAI_MODEL (default: gpt-6-luna).

## Local test
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
export OPENAI_API_KEY="..."
python app.py

Then open http://127.0.0.1:8000

## Important security
Never put OPENAI_API_KEY in index.html or client-side JavaScript. Keep it as a server environment variable.
