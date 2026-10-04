# AI Daily News Automation

An n8n workflow that automatically collects recent AI news, uses Google Gemini to select and summarize the most important stories, and sends a daily email digest.

## What it does

1. Gets AI news from TechCrunch, Ars Technica, and Wired.
2. Keeps articles from the last 72 hours.
3. Removes duplicate articles.
4. Selects the latest 15 articles.
5. Sends the articles to Google Gemini.
6. Gemini selects and summarizes the 8 most important stories.
7. Creates an email digest.
8. Sends the digest automatically.

## Workflow

```text
RSS News Sources
       ↓
Merge Articles
       ↓
Filter Recent News
       ↓
Remove Duplicates
       ↓
Sort by Date
       ↓
Top 15 Articles
       ↓
Google Gemini
       ↓
Select & Summarize Top 8
       ↓
Build Email Digest
       ↓
Send Email
```

## Technologies

- n8n
- Docker
- Google Gemini
- RSS Feeds
- SMTP / Email

## Setup

1. Run n8n locally with Docker.
2. Open `http://localhost:5678`.
3. Import `workflows/workflows.json`.
4. Create/configure a Google Gemini credential in n8n.
5. Create/configure an SMTP credential in n8n.
6. Set the email address you want to receive the digest.
7. Test the workflow manually.
8. Enable the workflow when it is working correctly.

The workflow is scheduled to run daily at 7:00 AM.

## Security

Do not upload API keys, passwords, `.env` files, or the n8n data directory to GitHub.

Credentials should be stored in n8n's credential system, not directly inside the workflow code.

## Project Structure

```text
ai-daily-news/
├── workflows/
│   └── workflows.json
├── README.md
├── .gitignore
└── .env.example
```

## Example Output

The email digest contains:

- News headline
- Short summary
- Why the story matters
- Category
- Source
- Link to the original article

## Author

Ayush Shrestha
