<div align="center">

# 🧠 BrainAI

**A Flask-based conversational web interface**

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-Web%20App-000000?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)

</div>

---

## Overview

BrainAI is a small Python web application built with Flask. It serves a chat page and accepts user messages through a POST endpoint, then passes the prompt to the project's Gemini integration and returns the generated response.

## Features

- Flask-powered web interface
- Chat page rendered from a Jinja template
- POST endpoint for sending prompts
- Vietnamese language preference configured for the Gemini client

## Technology

| Component | Purpose |
|---|---|
| Python | Application runtime |
| Flask | Web server and routing |
| Flask-Bootstrap | Bootstrap integration |
| Jinja | HTML template rendering |
| Gemini integration | Prompt response generation |

## Project layout

```text
.
├── app.py              # Flask application and /get endpoint
├── config.py           # Local integration configuration
├── templates/
│   └── index.html      # Chat interface
└── static/             # Frontend assets, if present
```

## Setup

### Requirements

- Python 3
- The Python packages imported by `app.py`
- A working configuration for the Gemini integration used by this project

Install the web framework dependencies:

```bash
python -m pip install Flask Flask-Bootstrap
```

The repository also imports a `Gemini` client module. Install or provide that dependency according to the version used by this project; the repository does not currently include a standard `requirements.txt` manifest.

### Run

From the repository root:

```bash
python app.py
```

The Flask development server is configured to listen on port **5000**. Open:

```text
http://127.0.0.1:5000
```

## Routes

| Method | Route | Purpose |
|---|---|---|
| GET | `/` | Render the chat interface |
| POST | `/get` | Submit a prompt and return the generated response |

## Security and maintenance

The current integration uses account-session cookie values through local configuration. Treat those values as secrets:

- Never commit real session cookies or account credentials.
- Keep private configuration out of public repositories.
- Do not expose this development server directly to the public internet.
- The app currently starts Flask with `debug=True`; disable debug mode and add appropriate authentication, validation, and production hosting controls before deployment.
- Review the upstream Gemini integration for compatibility and service-policy changes.

This repository is an experimental chat interface, not a production-ready AI service.

---

<div align="center">

**BrainAI · Python × Flask**

</div>
