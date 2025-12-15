---
title: API Reference
template: chapter
icon: tabler/code.svg
description: Complete REST API documentation with endpoints, parameters, and examples
taxonomy:
    category:
        - docs
---

Welcome to the Petstore API reference documentation. This API allows you to manage pets, store orders, and user accounts.

## Base URL

All API requests should be made to:

```
https://petstore3.swagger.io/api/v3
```

## Authentication

Most endpoints require authentication. The API supports two authentication methods:

### API Key
Include your API key in the request header:

```bash
curl -H "api_key: YOUR_API_KEY" \
  https://petstore3.swagger.io/api/v3/pet/1
```

### OAuth 2.0
For OAuth authentication, include the Bearer token:

```bash
curl -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
  https://petstore3.swagger.io/api/v3/pet/1
```

## Rate Limiting

| Plan       | Requests/min | Requests/day |
|------------|--------------|--------------|
| Free       | 60           | 1,000        |
| Pro        | 600          | 50,000       |
| Enterprise | Unlimited    | Unlimited    |

When rate limited, you'll receive a `429 Too Many Requests` response with a `Retry-After` header.

## Response Codes

All endpoints return standard HTTP status codes:

| Code | Description |
|------|-------------|
| 200  | Success |
| 201  | Created |
| 400  | Bad Request - Invalid parameters |
| 401  | Unauthorized - Invalid or missing API key |
| 404  | Not Found - Resource doesn't exist |
| 429  | Too Many Requests - Rate limit exceeded |
| 500  | Server Error |
