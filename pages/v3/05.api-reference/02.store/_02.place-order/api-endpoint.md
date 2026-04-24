---
title: 'Place Order'
api:
    method: POST
    path: /store/order
    description: 'Place a new order for a pet.'
    parameters:
        -
            name: petId
            type: integer
            required: true
            description: 'ID of the pet being ordered'
        -
            name: quantity
            type: integer
            required: true
            description: 'Number of units to order'
        -
            name: shipDate
            type: string
            required: false
            description: 'ISO 8601 date-time for requested shipment'
        -
            name: status
            type: string
            required: false
            description: 'Order status: placed, approved, or delivered'
        -
            name: complete
            type: boolean
            required: false
            description: 'Whether the order has been fulfilled'
    request_example: "{\n    \"petId\": 198772,\n    \"quantity\": 1,\n    \"shipDate\": \"2026-05-01T09:00:00.000Z\",\n    \"status\": \"placed\",\n    \"complete\": false\n}"
    response_example: "{\n    \"id\": 10,\n    \"petId\": 198772,\n    \"quantity\": 1,\n    \"shipDate\": \"2026-05-01T09:00:00.000Z\",\n    \"status\": \"placed\",\n    \"complete\": false\n}"
    response_codes:
        -
            code: '200'
            description: 'Order placed'
        -
            code: '400'
            description: 'Invalid input'
        -
            code: '422'
            description: 'Validation exception'
---
