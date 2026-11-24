# scam_shield
Real-time AI scam call detector for elders. Listens to Telugu/Hindi calls, flags "digital arrest", OTP and UPI fraud patterns, and warns in spoken Telugu, with family SMS alerts. Built for AI for Bharat.
# Scam Shield

A prototype scam-call awareness tool focused on helping older adults recognize suspicious call content in Telugu, Hindi, and English.

The current prototype uses transcript-based red-flag detection. It can identify warning signs such as requests for OTPs, UPI payments, remote access, threats of digital arrest, and urgent money transfers.

> **Important:** This is an educational prototype, not a guaranteed fraud detector. A low score does not prove that a call is safe. Never share an OTP, PIN, password, or UPI PIN with anyone.

## Current project files

- `app.py` — FastAPI application and API entry point.
- `scam_rules.py` — language-specific scam indicators and scoring logic.
- `requirements.txt` — Python dependencies.
- `sample_transcripts.txt` — sample text used for manual testing.

## Setup

Use Python 3.10 or newer.

```bash
python -m venv .venv
```

Activate the environment:

**Windows PowerShell**
```powershell
.venv\Scripts\Activate.ps1
```

**macOS / Linux**
```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Run the API

If `app.py` defines a FastAPI instance named `app`, run:

```bash
uvicorn app:app --reload
```

Open the API documentation at:

```text
http://127.0.0.1:8000/docs
```

If your FastAPI variable has a different name, or your app uses a different startup command, adjust the command to match `app.py`.

Test the scorer

Run the sample transcripts through the API or the scorer function defined in `scam_rules.py`. Confirm that the output includes a risk score or risk category, the matched warning indicators, and a clear safety recommendation.

Do not assume the sample output is accurate until you have run the tests yourself.
 Suggested demo flow

1. Start the API.
2. Open `/docs`.
3. Submit a clearly suspicious transcript mentioning an OTP, UPI PIN, or digital arrest.
4. Show the detected indicators and risk result.
5. Submit an ordinary conversation as a comparison.
6. Explain why the tool gives warnings and why users should verify suspicious calls independently.
7.
    Planned improvements
9.    Speech-to-text for Telugu and Hindi audio.
- Spoken warning messages in the user's preferred language.
- Optional family notifications, with explicit user consent.
- More realistic and diverse test transcripts.
- Evaluation using precision, recall, and a confusion matrix.
Privacy and safety

- Use synthetic or consented test transcripts only.
- Do not upload real call recordings or personal information to a public repository.
- Do not automatically record, monitor, or notify family members without clear consent.
- Treat every detection as a warning for further verification, not a final judgement.

 Limitations

- Keyword/rule-based scoring can miss new scam patterns.
- Ordinary conversations can contain words that resemble scam indicators.
- Speech recognition may mishear regional accents, names, and numbers.
- The prototype does not independently verify phone numbers, bank accounts, or callers.
