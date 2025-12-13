---
title: Get User
template: api-endpoint
taxonomy:
    category: docs
api:
    method: GET
    path: /users/{id}
    description: Retrieves a user by their unique identifier
    parameters:
        - name: id
          type: string
          required: true
          in: path
          description: The user's unique identifier
    response_example: |
        {
          "id": "usr_abc123xyz",
          "email": "john@example.com",
          "name": "John Doe",
          "role": "user",
          "avatar_url": "https://example.com/avatars/usr_abc123xyz.jpg",
          "created_at": "2024-01-15T10:30:00Z",
          "updated_at": "2024-01-20T14:45:00Z"
        }
    response_codes:
        - code: 200
          description: User retrieved successfully
        - code: 404
          description: User not found
        - code: 401
          description: Unauthorized - invalid API key
---

## Example Request

```bash
curl https://api.example.com/users/usr_abc123xyz \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## Related Endpoints

- [Create User](/api-reference/users/create-user) - Create a new user
- [Update User](/api-reference/users/update-user) - Modify user details
- [List Users](/api-reference/users/list-users) - Get all users
