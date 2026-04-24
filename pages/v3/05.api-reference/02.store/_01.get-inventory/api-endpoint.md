---
title: 'Get Inventory'
api:
    method: GET
    path: /store/inventory
    description: 'Returns a map of status codes to quantities of pets currently in the store.'
    request_example: ''
    response_example: "{\n    \"available\": 42,\n    \"pending\": 7,\n    \"sold\": 15\n}"
    response_codes:
        -
            code: '200'
            description: 'Successful operation'
---
