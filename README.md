# Resolve — AI Ticket Assistant

A small AI-assisted customer-support triage MVP built with ASP.NET Core 10, vanilla JavaScript, and the Google Gemini API.

## Features
- Classifies tickets into Billing, Technical, Account, Delivery, or Other.
- Assigns Low, Medium, High, or Critical priority.
- Produces a concise summary, a suggested response draft, and missing-information questions.
- Requests JSON output from Gemini and validates returned values on the server.
- Handles missing configuration, API errors, quota limits, and timeouts.
- Keeps the API key on the server; it is never sent to the browser.

## Requirements
- .NET 10 SDK
- A Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey)

## Run locally

Open PowerShell in the project folder:

```powershell
$env:GEMINI_API_KEY="your-gemini-api-key"
$env:GEMINI_MODEL="gemini-2.5-flash"
dotnet run --urls http://localhost:5000
```

Open http://localhost:5000.

The default model is `gemini-2.5-flash`. You can override it with `GEMINI_MODEL`.

## API

`POST /api/analyze`

```json
{ "message": "I was charged twice for my subscription." }
```

`GET /api/health` returns service status and provider name.

## Privacy and limitations

This is a demo, not a production support system. AI output can be inaccurate; a human must review suggested replies. No customer data is persisted. Use synthetic/example ticket text only in the free Gemini tier, and do not submit real customer personal or payment information. Google's free-tier data-use terms may differ from paid-tier terms; review the current [Gemini API pricing and terms](https://ai.google.dev/gemini-api/docs/pricing) before using real data.

Before production use, add authentication, rate limiting, privacy controls, structured logging, retries, and automated tests.
