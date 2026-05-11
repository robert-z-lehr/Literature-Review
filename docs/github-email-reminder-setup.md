# GitHub Email Reminder Setup

This repository includes a GitHub Actions workflow that can send scheduled reminder emails.

Workflow file:

```text
.github/workflows/scheduled-email-reminder.yml
```

---

## Required Repository Secrets

Open:

```text
Repository → Settings → Secrets and variables → Actions
```

Add the following repository secrets.

| Secret | Example |
|---|---|
| SMTP_HOST | smtp.gmail.com |
| SMTP_PORT | 587 |
| SMTP_USERNAME | your-email@gmail.com |
| SMTP_PASSWORD | app-password |
| REMINDER_EMAIL_FROM | your-email@gmail.com |
| REMINDER_EMAIL_TO | your-email@gmail.com |

---

## Gmail Setup Recommendation

For Gmail:

1. Enable 2-factor authentication.
2. Create a Google App Password.
3. Use the App Password as SMTP_PASSWORD.

Google Account:

```text
Security → 2-Step Verification → App passwords
```

---

## Changing Reminder Frequency

Current schedule:

```yaml
- cron: "0 13 * * 1"
```

Meaning:

```text
Every Monday at 13:00 UTC
```

Examples:

| Schedule | Cron |
|---|---|
| Every day at 8 AM | 0 13 * * * |
| Every weekday at 7 AM | 0 12 * * 1-5 |
| Every Sunday evening | 0 0 * * 0 |

Cron uses UTC.

---

## Manual Trigger

You can manually run the workflow:

```text
Actions → Scheduled Research Email Reminder → Run workflow
```

You may optionally customize:

- email subject
- message body

---

## Future Extensions

Potential upgrades:

- summarize open GitHub Project tasks
- summarize overdue issues
- include advisor meeting deadlines
- integrate SMS reminders using Twilio
- daily digest emails
- AI-generated weekly summaries
