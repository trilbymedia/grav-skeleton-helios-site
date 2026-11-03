---
title: 'Create Users With List'
api:
    method: POST
    path: /user/createWithList
    description: 'Create multiple user accounts in a single request by posting an array of user objects.'
    request_example: "[\n    {\n        \"username\": \"theUser\",\n        \"firstName\": \"John\",\n        \"lastName\": \"James\",\n        \"email\": \"john@email.com\",\n        \"password\": \"12345\",\n        \"phone\": \"12345\",\n        \"userStatus\": 1\n    },\n    {\n        \"username\": \"anotherUser\",\n        \"firstName\": \"Jane\",\n        \"lastName\": \"Doe\",\n        \"email\": \"jane@email.com\",\n        \"password\": \"67890\",\n        \"userStatus\": 1\n    }\n]"
    response_example: "[\n    {\n        \"id\": 10,\n        \"username\": \"theUser\",\n        \"firstName\": \"John\",\n        \"lastName\": \"James\",\n        \"email\": \"john@email.com\",\n        \"userStatus\": 1\n    },\n    {\n        \"id\": 11,\n        \"username\": \"anotherUser\",\n        \"firstName\": \"Jane\",\n        \"lastName\": \"Doe\",\n        \"email\": \"jane@email.com\",\n        \"userStatus\": 1\n    }\n]"
    response_codes:
        -
            code: '200'
            description: 'Successful operation'
        -
            code: 'default'
            description: 'Unexpected error'
---
