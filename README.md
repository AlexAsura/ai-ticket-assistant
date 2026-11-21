# Resolve — AI Ticket Assistant

An AI-powered customer support ticket triage MVP built with ASP.NET Core 10, vanilla JavaScript, and the Google Gemini API.

Resolve analyzes incoming customer support messages and helps support teams understand, prioritize, and respond to customer requests.

## Features

- **Ticket classification** — categorizes requests as Billing, Technical, Account, Delivery, or Other.
- **Priority assessment** — assigns Low, Medium, High, or Critical priority.
- **Ticket summary** — generates a concise summary of the customer's issue.
- **Suggested response** — drafts a response that a support agent can review and edit.
- **Missing information detection** — identifies additional information that may be needed.
- **Structured AI output** — requests JSON responses from Gemini and validates the returned values on the server.
- **Error handling** — handles missing configuration, API errors, quota limits, and timeouts.

The Gemini API key is stored on the server and is never exposed to the browser.

## Tech Stack

- C# / ASP.NET Core 10
- Vanilla JavaScript
- HTML / CSS
- Google Gemini API

## Requirements

- .NET 10 SDK
- A Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/AlexAsura/ai-ticket-assistant.git
cd ai-ticket-assistant
```

### 2. Configure the API key

Set your Gemini API key as an environment variable.

**PowerShell:**

```powershell
$env:GEMINI_API_KEY="your-gemini-api-key"
```

Do not commit your API key or share it publicly.

### 3. Run the application

```powershell
dotnet run --urls "http://localhost:5000"
```

Open [http://localhost:5000](http://localhost:5000) in your browser.

The application uses the `gemini-flash-lite-latest` model.

## API

### `POST /api/analyze`

Analyzes a customer support message.

Example request:

```json
{
  "message": "I was charged twice for my subscription."
}
```

### `GET /api/health`

Returns the service status and AI provider information.

## Privacy and Limitations

Resolve is a demonstration MVP, not a production-ready customer support system.

- AI-generated classifications and responses may be inaccurate and should always be reviewed by a human.
- Customer data is not persisted.
- Use synthetic or example ticket text when testing with the free Gemini tier.
- Do not submit real customer personal information or payment details.

Google's free-tier data-use terms may differ from paid-tier terms. Review the current [Gemini API pricing and terms](https://ai.google.dev/gemini-api/docs/pricing) before using real data.

Before production use, the application would need additional features such as authentication, rate limiting, privacy controls, structured logging, and automated tests.

## Project Status

This project is an MVP developed as a practical demonstration of integrating an LLM API into a backend application.