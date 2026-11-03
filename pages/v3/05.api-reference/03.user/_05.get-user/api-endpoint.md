---
title: 'Get User by Username'
api:
    method: GET
    path: '/user/{username}'
    description: 'Retrieve a single user account by its username.'
    parameters:
        -
            name: username
            type: string
            required: true
            description: 'The username of the account to fetch'
    request_example: ''
    response_example: "{\n    \"id\": 10,\n    \"username\": \"theUser\",\n    \"firstName\": \"John\",\n    \"lastName\": \"James\",\n    \"email\": \"john@email.com\",\n    \"phone\": \"12345\",\n    \"userStatus\": 1\n}"
    response_codes:
        -
            code: '200'
            description: 'Successful operation'
        -
            code: '400'
            description: 'Invalid username supplied'
        -
            code: '404'
            description: 'User not found'
---
