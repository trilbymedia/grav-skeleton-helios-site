---
title: 'Delete User'
api:
    method: DELETE
    path: '/user/{username}'
    description: 'Delete a user account. This operation is permanent and cannot be undone.'
    parameters:
        -
            name: username
            type: string
            required: true
            description: 'The username of the account to delete'
    request_example: ''
    response_example: ''
    response_codes:
        -
            code: '200'
            description: 'User deleted'
        -
            code: '400'
            description: 'Invalid username supplied'
        -
            code: '404'
            description: 'User not found'
---
