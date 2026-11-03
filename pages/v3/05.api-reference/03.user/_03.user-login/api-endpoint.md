---
title: 'User Login'
api:
    method: GET
    path: /user/login
    description: 'Authenticate a user with username and password, returning a session token in the response header.'
    parameters:
        -
            name: username
            type: string
            required: false
            description: 'Username for the account'
        -
            name: password
            type: string
            required: false
            description: 'Password for the account (sent in clear-text in this demo API)'
    request_example: ''
    response_example: "Logged in user session:2026-04-24T12:00:01.123+00:00"
    response_codes:
        -
            code: '200'
            description: 'Successful operation'
        -
            code: '400'
            description: 'Invalid username/password supplied'
---

The session token is returned in the `X-Expires-After` and `X-Rate-Limit` response headers alongside the response body.
