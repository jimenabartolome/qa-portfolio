# BUG-001: "Add card" button becomes active with incomplete card number

## Description
The "Add card" button becomes enabled when only 11 digits are entered in the "Card Number" field.

## Steps to reproduce
1. Go to the test environment.
2. Enter "1917 Bay St" in the "From" field.
3. Enter "615 S Broadway" in the "To" field.
4. Select "Personal" mode.
5. Choose "Car sharing" as the transportation type.
6. Add a driver’s license.
7. Add a payment card:
   - Card number: 1234 1234 123
   - Security code: 12
8. Click "Add"

## Expected result
When entering only 11 digits in the "Card Number" field, the "Add card" button should remain inactive.

## Actual result
When entering 11 digits in the "Card Number" field, the "Add card" button becomes active.

## Severity
High

## Environment
- Browser: Google Chrome 800x600

