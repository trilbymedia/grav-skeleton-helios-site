---
title: 'Deletes a pet.'
template: api-endpoint
taxonomy:
  category: docs
api:
  method: DELETE
  path: '/pet/{petId}'
  description: 'Delete a pet.'
  parameters:
    -
      name: api_key
      type: string
      required: false
      description: ''
    -
      name: petId
      type: integer
      required: true
      description: 'Pet id to delete'
  response_codes:
    -
      code: '200'
      description: 'Pet deleted'
    -
      code: '400'
      description: 'Invalid pet value'
---
