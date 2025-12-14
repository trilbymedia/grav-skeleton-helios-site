---
title: 'Add Pet'
template: api-endpoint
taxonomy:
  category: docs
api:
  method: POST
  path: /pet
  description: 'Creates a new pet in the store inventory. The pet will be assigned a unique ID automatically.'
  parameters:
    -
      name: id
      type: integer
      required: false
      description: ''
    -
      name: name
      type: string
      required: true
      description: ''
    -
      name: category
      type: object
      required: false
      description: ''
    -
      name: photoUrls
      type: array
      required: true
      description: ''
    -
      name: tags
      type: array
      required: false
      description: ''
    -
      name: status
      type: string
      required: false
      description: 'pet status in the store'
  request_example: "{\n    \"name\": \"doggie\",\n    \"category\": {\n        \"name\": \"Dogs\"\n    },\n    \"photoUrls\": [\n        \"string\"\n    ],\n    \"tags\": [\n        {\n            \"name\": \"string\"\n        }\n    ],\n    \"status\": \"available\"\n}"
  response_example: "{\n    \"id\": 10,\n    \"name\": \"doggie\",\n    \"category\": {\n        \"id\": 1,\n        \"name\": \"Dogs\"\n    },\n    \"photoUrls\": [\n        \"string\"\n    ],\n    \"tags\": [\n        {\n            \"id\": 1,\n            \"name\": \"string\"\n        }\n    ],\n    \"status\": \"available\"\n}"
  response_codes:
    -
      code: '200'
      description: 'Successful operation'
    -
      code: '400'
      description: 'Invalid input'
    -
      code: '422'
      description: 'Validation exception'
---

## Usage Notes

When creating a new pet, the `id` field is optional. If omitted, the system will automatically generate a unique identifier.

### Status Values

The `status` field accepts one of the following values:

| Status      | Description |
|-------------|-------------|
| `available` | Pet is available for purchase |
| `pending`   | Pet has a pending order |
| `sold`      | Pet has been sold |

### Image Upload

After creating a pet, you can upload images using the [Upload Image](/v3/api-reference/pet/uploadfile) endpoint.

### Example with cURL

```bash
curl -X POST "https://petstore3.swagger.io/api/v3/pet" \
  -H "Content-Type: application/json" \
  -H "api_key: YOUR_API_KEY" \
  -d '{
    "name": "Buddy",
    "category": {"name": "Dogs"},
    "photoUrls": ["https://example.com/buddy.jpg"],
    "status": "available"
  }'
```

### Webhooks

When a pet is created, the following webhook event is triggered:

```json
{
  "event": "pet.created",
  "data": {
    "id": 12345,
    "name": "Buddy",
    "status": "available"
  },
  "timestamp": "2024-01-15T10:30:00Z"
}
```
