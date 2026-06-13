# Mailbox Voice To Text

این workflow برای n8n است.

جریان کار:

```text
Simotel Mailbox Webhook
  -> Create voicemail audio link
  -> Download audio binary
  -> Upload audio to Eboo
  -> Convert audio to Persian text
  -> Poll Eboo until output is ready
  -> Build Telegram message
  -> Send message to Telegram
```

## فایل‌ها

```text
n8n-workflow.json
.env.example
README.md
```

## مقدارهای لازم برای جایگزینی

داخل `n8n-workflow.json` این مقدارها را replace کن:

```text
__PANEL_API_KEY__
__EBOO_TOKEN__
__TELEGRAM_BOT_TOKEN__
__TELEGRAM_CHAT_ID__
```

## Webhook

بعد از import و فعال‌سازی workflow در n8n:

```text
https://YOUR-N8N-DOMAIN/webhook/mailbox-voice-to-text
```

## Payload مورد انتظار

workflow از query string این فیلدها را می‌خواند:

```text
event_name=VoiceMail
state=SUCCESS
filename=...
caller=...
number=...
duration=...
date=...
cuid=...
id=...
```

## نکته n8n

در node `Link to Binary` باید خروجی فایل با binary property زیر باشد:

```text
Response Format = File
Binary Property = data
```

در node `Get FileToken` نیز همین binary field خوانده می‌شود:

```text
inputDataFieldName = data
```
