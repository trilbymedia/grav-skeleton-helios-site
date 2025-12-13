---
title: Update User
template: api-endpoint
taxonomy:
    category: docs
api:
    method: PUT
    path: /users/{id}
    description: Updates an existing user's information
    parameters:
        - name: id
          type: string
          required: true
          in: path
          description: The user's unique identifier
        - name: email
          type: string
          required: false
          description: New email address (must be unique)
        - name: name
          type: string
          required: false
          description: New display name
        - name: role
          type: string
          required: false
          description: New user role
    request_example: |
        {
          "name": "John Smith",
          "role": "admin"
        }
    response_example: |
        {
          "id": "usr_abc123xyz",
          "email": "john@example.com",
          "name": "John Smith",
          "role": "admin",
          "created_at": "2024-01-15T10:30:00Z",
          "updated_at": "2024-01-22T09:15:00Z"
        }
    response_codes:
        - code: 200
          description: User updated successfully
        - code: 400
          description: Invalid request body
        - code: 404
          description: User not found
        - code: 409
          description: Email already in use
        - code: 401
          description: Unauthorized
---

## Example Request

```bash
curl -X PUT https://api.example.com/users/usr_abc123xyz \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Smith",
    "role": "admin"
  }'
```

## Partial Updates

Only include fields you want to update. Omitted fields remain unchanged.

## Updating Password

To update a user's password, use the dedicated password endpoint:

```bash
curl -X POST https://api.example.com/users/usr_abc123xyz/password \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{"current_password": "old_pass", "new_password": "new_pass"}'
```
