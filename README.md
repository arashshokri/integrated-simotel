# Integrated Simotel

مخزن integrationهای کوچک مرتبط با Simotel / HostedPBX / n8n.

## ساختار

```text
integrated-simotel/
  mailbox-voice-to-text/
    n8n-workflow.json
    README.md
    .env.example
```

## قانون امنیتی

توکن‌ها، API keyها، bot tokenها و chat id واقعی نباید داخل Git commit شوند.
در workflow از placeholder استفاده شده است.
