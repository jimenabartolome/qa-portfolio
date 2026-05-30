BUG-001 – Incorrect Error Type Returned When Adding a Product to a Kit

## Summary

The API returns an incorrect error type when attempting to add a product to a kit using an invalid Kit ID. Instead of returning a 400 Bad Request, the endpoint returns a 500 Internal Server Error.

## Environment
Tool: Postman
Method: POST
Endpoint: /api/v1/kits/{id}/products
Browser: Google Chrome

## Preconditions

An existing kit is available in the system.
Example:

Kit ID: 3

## Steps to Reproduce
1. Open Postman.
2. Select the POST method.
3. Enter the following endpoint:
{{BASE_URL}}/api/v1/kits/3/products
4. Navigate to Body → Raw → JSON.
5. Send the following request body:
{
  "productsList": [
    {
      "id": 3,
      "quantity": 1
    }
  ]
}
6. Click Send.
7. Observe the response.

## Expected Result
The API should reject the request.
The API should return 400 Bad Request.
The response message should indicate that the Kit ID is invalid or does not exist.

## Actual Result
The API rejects the request.
The API returns 500 Internal Server Error.
The system fails to properly validate the invalid Kit ID.

## Severity
Medium

## Priority
Medium



Open
