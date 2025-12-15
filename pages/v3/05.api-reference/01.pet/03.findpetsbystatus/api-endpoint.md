---
title: 'Finds Pets by status.'
template: api-endpoint
taxonomy:
  category: docs
api:
  method: GET
  path: /pet/findByStatus
  description: 'Multiple status values can be provided with comma separated strings.'
  parameters:
    -
      name: status
      type: string
      required: true
      description: 'Status values that need to be considered for filter'
  response_example: "[\n    {\n        \"id\": 10,\n        \"name\": \"doggie\",\n        \"category\": {\n            \"id\": 1,\n            \"name\": \"Dogs\"\n        },\n        \"photoUrls\": [\n            \"string\"\n        ],\n        \"tags\": [\n            {\n                \"id\": 1,\n                \"name\": \"string\"\n            }\n        ],\n        \"status\": \"available\"\n    }\n]"
  response_codes:
    -
      code: '200'
      description: 'successful operation'
    -
      code: '400'
      description: 'Invalid status value'
---
