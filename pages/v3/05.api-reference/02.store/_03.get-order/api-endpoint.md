---
title: 'Get Order by ID'
api:
    method: GET
    path: '/store/order/{orderId}'
    description: 'Retrieve a purchase order by its ID. IDs between 1 and 10 are valid in the demo data set; IDs greater than 10 or non-integers generate API errors.'
    parameters:
        -
            name: orderId
            type: integer
            required: true
            description: 'The ID of the order to fetch'
    request_example: ''
    response_example: "{\n    \"id\": 10,\n    \"petId\": 198772,\n    \"quantity\": 1,\n    \"shipDate\": \"2026-05-01T09:00:00.000Z\",\n    \"status\": \"approved\",\n    \"complete\": true\n}"
    response_codes:
        -
            code: '200'
            description: 'Successful operation'
        -
            code: '400'
            description: 'Invalid ID supplied'
        -
            code: '404'
            description: 'Order not found'
---
