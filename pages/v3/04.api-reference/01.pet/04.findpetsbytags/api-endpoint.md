---
title: 'Finds Pets by tags.'
template: api-endpoint
taxonomy:
  category: docs
api:
  method: GET
  path: /pet/findByTags
  description: 'Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.'
  parameters:
    -
      name: tags
      type: array
      required: true
      description: 'Tags to filter by'
  response_example: "[\n    {\n        \"id\": 10,\n        \"name\": \"doggie\",\n        \"category\": {\n            \"id\": 1,\n            \"name\": \"Dogs\"\n        },\n        \"photoUrls\": [\n            \"string\"\n        ],\n        \"tags\": [\n            {\n                \"id\": 1,\n                \"name\": \"string\"\n            }\n        ],\n        \"status\": \"available\"\n    }\n]"
  response_codes:
    -
      code: '200'
      description: 'successful operation'
    -
      code: '400'
      description: 'Invalid tag value'
---
