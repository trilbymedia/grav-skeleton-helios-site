---
title: 'Updates a pet in the store with form data.'
template: api-endpoint
taxonomy:
  category: docs
api:
  method: POST
  path: '/pet/{petId}'
  description: 'Updates a pet resource based on the form data.'
  parameters:
    -
      name: petId
      type: integer
      required: true
      description: 'ID of pet that needs to be updated'
    -
      name: name
      type: string
      required: false
      description: 'Name of pet that needs to be updated'
    -
      name: status
      type: string
      required: false
      description: 'Status of pet that needs to be updated'
  response_example: "{\n    \"id\": 10,\n    \"name\": \"doggie\",\n    \"category\": {\n        \"id\": 1,\n        \"name\": \"Dogs\"\n    },\n    \"photoUrls\": [\n        \"string\"\n    ],\n    \"tags\": [\n        {\n            \"id\": 1,\n            \"name\": \"string\"\n        }\n    ],\n    \"status\": \"available\"\n}"
  response_codes:
    -
      code: '200'
      description: 'successful operation'
    -
      code: '400'
      description: 'Invalid input'
---
