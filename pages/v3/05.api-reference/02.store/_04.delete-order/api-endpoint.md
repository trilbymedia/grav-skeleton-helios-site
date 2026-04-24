---
title: 'Delete Order'
api:
    method: DELETE
    path: '/store/order/{orderId}'
    description: 'Delete a purchase order by its ID. For valid response try integer IDs with positive values; negative or non-integer IDs will generate API errors.'
    parameters:
        -
            name: orderId
            type: integer
            required: true
            description: 'The ID of the order to delete'
    request_example: ''
    response_example: ''
    response_codes:
        -
            code: '200'
            description: 'Order deleted'
        -
            code: '400'
            description: 'Invalid ID supplied'
        -
            code: '404'
            description: 'Order not found'
---
