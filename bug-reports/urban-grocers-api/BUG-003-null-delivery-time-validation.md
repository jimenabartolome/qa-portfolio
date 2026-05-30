## BUG-003 – POST /order-and-go/v1/delivery Returns 200 OK When "deliveryTime" Is Null
## Summary
The API returns an incorrect response when executing an Order and Go delivery request with the required "deliveryTime" field set to null. Instead of returning a 400 Bad Request response, the endpoint returns 200 OK and processes the request successfully.

## Environment
Tool: Postman
Method: POST
Endpoint: /order-and-go/v1/delivery
Browser: Google Chrome

## Steps to Reproduce
1. Open Postman.
2. Select the POST method.
3. Enter the following endpoint:

{{BASE_URL}}/order-and-go/v1/delivery

4. Navigate to Body → Raw → JSON.
5. Send the following request body:

{
"deliveryTime": null,
"productsCount": 2,
"productsWeight": 2
}

6. Click Send.
7. Observe the response.

## Expected Result
The API should reject the request.
The API should return 400 Bad Request.
The response message should indicate that the "deliveryTime" value is invalid or cannot be null.

## Actual Result
The API returns 200 OK.
isItPossibleToDeliver: TRUE.
hostDeliveryCost: 3.
clientDeliveryCost: 5.
The request is processed successfully despite the invalid null value.

## Severity
Medium

## Priority
Medium

## Status
Open
