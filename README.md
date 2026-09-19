# Ain (عين) – AI-Powered Municipal Infrastructure Assistant

Ain automates the processing of citizen infrastructure reports (e.g. potholes, water leaks). Instead of manually reviewing unstructured text, a two-agent **CrewAI** pipeline analyzes each report, extracts the key details, validates them, and stores the result in a structured format.

## How it works

1. A citizen submits a report through a **Gradio** interface.
2. **Report Analyzer** agent extracts the issue type, location, and description.
3. **Quality Reviewer** agent validates the extraction, assigns a priority level (High/Medium/Low), and produces the final structured JSON.
4. The validated report is saved automatically to **Google Sheets**.

## Tech stack

- Python
- [CrewAI](https://github.com/joaomdmoura/crewAI) (multi-agent orchestration)
- [OpenRouter](https://openrouter.ai) (LLM access)
- [Gradio](https://gradio.app) (UI)
- Google Sheets API (storage)

## Setup

1. Install dependencies: `pip install crewai gspread google-auth gradio`
2. Get an API key from [openrouter.ai/keys](https://openrouter.ai/keys) and set it as an environment variable (`OPENROUTER_API_KEY`) — **never commit a real key to the repo**.
3. Set up Google Sheets access (a service account, or Colab's built-in `google.colab.auth` if running there) and create a sheet named `Ain Infrastructure Reports`.
4. Run the notebook top to bottom; the last cell launches the Gradio demo.

## Notes

This is a learning/demo project built as part of a CS coursework/project exercise, not a production system — there's no authentication on the submission form, and error handling is minimal.
