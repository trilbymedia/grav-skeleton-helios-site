---
title: Create User
template: api-endpoint
taxonomy:
    category: docs
api:
    method: POST
    path: /users
    description: Creates a new user account
    parameters:
        - name: email
          type: string
          required: true
          description: User's email address. Must be unique.
        - name: name
          type: string
          required: true
          description: User's display name
        - name: password
          type: string
          required: true
          description: Password (min 8 characters)
        - name: role
          type: string
          required: false
          description: User role (admin, user, viewer). Defaults to user.
    request_example: |
        {
          "email": "john@example.com",
          "name": "John Doe",
          "password": "secure_password_123",
          "role": "user"
        }
    response_example: |
        {
          "id": "usr_abc123xyz",
          "email": "john@example.com",
          "name": "John Doe",
          "role": "user",
          "created_at": "2024-01-15T10:30:00Z",
          "updated_at": "2024-01-15T10:30:00Z"
        }
    response_codes:
        - code: 201
          description: User created successfully
        - code: 400
          description: Invalid request body or validation error
        - code: 409
          description: Email already exists
        - code: 401
          description: Unauthorized - invalid API key
---

## Additional Notes

The user's password is hashed using bcrypt before storage. The password field is never returned in API responses.

### Example Request

```bash
curl -X POST https://api.example.com/users \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "email": "john@example.com",
    "name": "John Doe",
    "password": "secure_password_123"
  }'
```

### Validation Rules

| Field | Rules |
|-------|-------|
| email | Valid email format, unique |
| name | 1-100 characters |
| password | Minimum 8 characters |
| role | One of: admin, user, viewer |

### Webhooks

When a user is created, the `user.created` webhook event is fired:

```json
{
  "event": "user.created",
  "data": {
    "id": "usr_abc123xyz",
    "email": "john@example.com"
  }
}
```
