---
title: 'Update an existing pet.'
template: api-endpoint
taxonomy:
  category: docs
api:
  method: PUT
  path: /pet
  description: 'Update an existing pet by Id.'
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
      description: 'Invalid ID supplied'
    -
      code: '404'
      description: 'Pet not found'
    -
      code: '422'
      description: 'Validation exception'
---
