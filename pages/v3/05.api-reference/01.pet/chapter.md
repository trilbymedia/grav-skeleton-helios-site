---
title: Pets
template: chapter
description: Manage pets in the store inventory
taxonomy:
    category:
        - docs
---

The Pets API allows you to create, read, update, and delete pets in the store inventory.

## Available Operations

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/pet/{petId}` | Get a pet by ID |
| POST | `/pet` | Add a new pet |
| PUT | `/pet` | Update an existing pet |
| DELETE | `/pet/{petId}` | Delete a pet |
| GET | `/pet/findByStatus` | Find pets by status |
| GET | `/pet/findByTags` | Find pets by tags |
| POST | `/pet/{petId}/uploadImage` | Upload a pet image |

## Pet Object

```json
{
  "id": 10,
  "name": "Buddy",
  "category": {
    "id": 1,
    "name": "Dogs"
  },
  "photoUrls": [
    "https://example.com/buddy.jpg"
  ],
  "tags": [
    {"id": 1, "name": "friendly"}
  ],
  "status": "available"
}
```
