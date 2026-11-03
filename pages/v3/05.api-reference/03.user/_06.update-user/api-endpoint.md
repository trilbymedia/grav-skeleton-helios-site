---
title: 'Update User'
api:
    method: PUT
    path: '/user/{username}'
    description: 'Update an existing user account. Only the fields provided in the request body are modified.'
    parameters:
        -
            name: username
            type: string
            required: true
            description: 'The username of the account to update'
        -
            name: email
            type: string
            required: false
            description: 'Updated email address'
        -
            name: firstName
            type: string
            required: false
            description: 'Updated first name'
        -
            name: lastName
            type: string
            required: false
            description: 'Updated last name'
        -
            name: password
            type: string
            required: false
            description: 'Updated password'
        -
            name: phone
            type: string
            required: false
            description: 'Updated contact phone number'
        -
            name: userStatus
            type: integer
            required: false
            description: 'Updated user status flag'
    request_example: "{\n    \"firstName\": \"Johnny\",\n    \"email\": \"johnny@email.com\",\n    \"phone\": \"555-0199\"\n}"
    response_example: "{\n    \"id\": 10,\n    \"username\": \"theUser\",\n    \"firstName\": \"Johnny\",\n    \"lastName\": \"James\",\n    \"email\": \"johnny@email.com\",\n    \"phone\": \"555-0199\",\n    \"userStatus\": 1\n}"
    response_codes:
        -
            code: '200'
            description: 'User updated'
        -
            code: '400'
            description: 'Bad request'
        -
            code: '404'
            description: 'User not found'
        -
            code: '422'
            description: 'Validation exception'
---
