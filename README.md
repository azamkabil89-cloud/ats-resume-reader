# 📄 AI Resume ATS Checker

Upload a resume (PDF, DOCX or TXT) and get an **ATS score**, category breakdown,
strengths, weaknesses, missing keywords and prioritized improvements, powered by
**Google Gemini Flash** and a **Streamlit** UI. Paste a job description for
targeted keyword matching.

## Features
- PDF / DOCX / TXT parsing
- ATS score (0-100) with formatting, keywords, content and readability sub-scores
- Prioritized, actionable improvement suggestions
- Optional job-description matching
- Downloadable JSON report

## Run locally
```bash
pip install -r requirements.txt
export GEMINI_API_KEY="your_key"      # Windows PowerShell: $env:GEMINI_API_KEY="your_key"
streamlit run app.py
```
Get a free key at https://aistudio.google.com/apikey. If no key is set, the app
asks for one in the sidebar.

## Deploy on Streamlit Community Cloud
1. Push `app.py`, `requirements.txt`, `README.md` to a GitHub repo.
2. Go to https://share.streamlit.io, click **Create app**, pick the repo, branch `main`, main file `app.py`.
3. Under **Advanced settings → Secrets**, add:
   ```toml
   GEMINI_API_KEY = "your_key"
   ```
4. Click **Deploy**.

## Configuration
Set `GEMINI_MODEL` (env var) to force a specific model. By default the app tries
`gemini-3.6-flash`, then falls back to `gemini-2.5-flash`.

## Notes
- Never commit your API key to GitHub.
- Scanned/image-only PDFs can't be read; use a text-based file.
- The score is an AI estimate, not the output of a real ATS.
