---
title: 'Find pet by ID.'
template: api-endpoint
taxonomy:
  category: docs
api:
  method: GET
  path: '/pet/{petId}'
  description: 'Returns a single pet.'
  parameters:
    -
      name: petId
      type: integer
      required: true
      description: 'ID of pet to return'
  response_example: "{\n    \"id\": 10,\n    \"name\": \"doggie\",\n    \"category\": {\n        \"id\": 1,\n        \"name\": \"Dogs\"\n    },\n    \"photoUrls\": [\n        \"string\"\n    ],\n    \"tags\": [\n        {\n            \"id\": 1,\n            \"name\": \"string\"\n        }\n    ],\n    \"status\": \"available\"\n}"
  response_codes:
    -
      code: '200'
      description: 'successful operation'
    -
      code: '400'
      description: 'Invalid ID supplied'
    -
      code: '404'
      description: 'Pet not found'
---
