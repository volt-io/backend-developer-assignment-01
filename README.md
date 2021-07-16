# Backend developer assignment 0x01

This document contains a description and requirements for assignment for the backend developer position.

## Goals

1. Verify your ability to work with 3rd party libraries.
2. Verify that you are able to write clean and testable code.
3. Check for best practices inside the chosen backend stack/framework.

## Requirements

1. For implementation use whatever fits you at the moment, the preferred order PHP, NodeJS, Java, GoLang, ... (ehm Whitespace?)
2. Create a payment gateway app, that can handle payments with:
    - Braintree [https://developer.paypal.com/braintree/docs](https://developer.paypal.com/braintree/docs)
    - Adyen [https://docs.adyen.com/online-payments](https://docs.adyen.com/online-payments)
3. The app should be designed to easily add another payment gateway.
4. The app should present a simple web page with a form for making a payment. 
5. From should contain the following fields with validation:
    1. In order section
        - Price (amount)
        - Currency (USD, EUR, GBP)
        - Customer full name
    2. In payment section:
        - Credit card holder name
        - Credit card number
        - Credit card expiration date
        - Credit card CCV
    3. Submit button
6. The app should present success or error message after the payment completes.
7. The app should save order data + response from payment gateway in database table (SQLite is OK).
8. Create a repository on Github with your solution and send us the link or invite @dannyow to the repository if it is private.

## Specification

- Create your own sandbox accounts on payments processors mentioned above.
- Implement the following rules on how to use a different gateway:
    - if credit card type is VISA use Braintree
    - if the currency is EUR use Braintree
    - if the card is VISA but the currency is not EUR show error message stating that EUR transactions are only possible with VISA card
    - otherwise use Adyen
- Use any framework or no framework at all - whichever suits you.
- Don't bother with any graphics or styling, plain old HTML is sufficient (however you can use something like Bootstrap or anything else)
- Prefer using raw API access instead of SDKs
- Cover your code with unit and integration tests. Use mocks in all places where there is a 3rd party request.
- Create readme file explaining how to run your app.
- Bonus points for using docker.

## Quality requirements

We will look specifically into:

- overall code quality,
- usage of configuration files,
- code best practices (naming convention, code formatting, linting etc),
- usage of tests,
- how easy was to run the app (readme!).