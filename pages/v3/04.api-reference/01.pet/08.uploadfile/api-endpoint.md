---
title: 'Uploads an image.'
template: api-endpoint
taxonomy:
  category: docs
api:
  method: POST
  path: '/pet/{petId}/uploadImage'
  description: 'Upload image of the pet.'
  parameters:
    -
      name: petId
      type: integer
      required: true
      description: 'ID of pet to update'
    -
      name: additionalMetadata
      type: string
      required: false
      description: 'Additional Metadata'
  response_example: "{\n    \"code\": 1,\n    \"type\": \"string\",\n    \"message\": \"string\"\n}"
  response_codes:
    -
      code: '200'
      description: 'successful operation'
    -
      code: '400'
      description: 'No file uploaded'
    -
      code: '404'
      description: 'Pet not found'
---
