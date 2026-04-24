---
title: 'Create User'
api:
    method: POST
    path: /user
    description: 'Create a new user account. This endpoint can only be invoked by a logged-in administrator.'
    parameters:
        -
            name: username
            type: string
            required: true
            description: 'Unique username for the account'
        -
            name: email
            type: string
            required: true
            description: 'Primary email address'
        -
            name: firstName
            type: string
            required: false
            description: 'Account holder''s first name'
        -
            name: lastName
            type: string
            required: false
            description: 'Account holder''s last name'
        -
            name: password
            type: string
            required: true
            description: 'Initial account password'
        -
            name: phone
            type: string
            required: false
            description: 'Contact phone number'
        -
            name: userStatus
            type: integer
            required: false
            description: 'User status flag'
    request_example: "{\n    \"username\": \"theUser\",\n    \"firstName\": \"John\",\n    \"lastName\": \"James\",\n    \"email\": \"john@email.com\",\n    \"password\": \"12345\",\n    \"phone\": \"12345\",\n    \"userStatus\": 1\n}"
    response_example: "{\n    \"id\": 10,\n    \"username\": \"theUser\",\n    \"firstName\": \"John\",\n    \"lastName\": \"James\",\n    \"email\": \"john@email.com\",\n    \"phone\": \"12345\",\n    \"userStatus\": 1\n}"
    response_codes:
        -
            code: '200'
            description: 'Successful operation'
        -
            code: '400'
            description: 'Invalid input'
---
