---
title: Authentication
taxonomy:
    category: docs
---

# Authentication

All API requests require authentication using API keys or OAuth tokens.

## API Keys

Include your API key in the `Authorization` header:

```bash
curl https://api.example.com/users \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## Obtaining API Keys

1. Log in to your dashboard
2. Navigate to Settings > API Keys
3. Click "Create New Key"
4. Copy and store your key securely

> [!WARNING]
> API keys grant full access to your account. Never share them or commit them to version control.

## OAuth 2.0

For user-authenticated requests, use OAuth 2.0:

```bash
curl https://api.example.com/oauth/token \
  -X POST \
  -d "grant_type=authorization_code" \
  -d "code=AUTH_CODE" \
  -d "client_id=YOUR_CLIENT_ID" \
  -d "client_secret=YOUR_CLIENT_SECRET"
```

## Rate Limiting

API requests are limited to:

| Plan | Requests/minute | Requests/day |
|------|-----------------|--------------|
| Free | 60 | 1,000 |
| Pro | 600 | 50,000 |
| Enterprise | Unlimited | Unlimited |

Rate limit headers are included in responses:

```
X-RateLimit-Limit: 60
X-RateLimit-Remaining: 45
X-RateLimit-Reset: 1699574400
```

## Error Responses

Authentication errors return a `401 Unauthorized` status:

```json
{
  "error": "unauthorized",
  "message": "Invalid or expired API key"
}
```
