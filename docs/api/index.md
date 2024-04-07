# API

## Authentication

The voucher system is an independent service in the Fanz cosmos. However, we have decided to integrate it seamlessly into existing implementations.
So if there is an integration with the payment platform, the same API keys are used.

=== "Authenticate with API Key"

    Add an `Authorization`-Header (Line 4) to each request to perform the API-Key authentication.

    ```javascript hl_lines="4" linenums="1"
    curl -X POST "https://voucher-api-dev.fanz.io/merchant/vouchers" \
    -H "accept: application/json" 
    -H "Content-Type: application/json" \
    -H "Authorization: YOUR_API_KEY"
    ```



=== "Authenticate with Username & Password"

    !!! danger "Keep in mind, to use the payment platform API"
        By April 2024 the payment platform is a mandatory building block. We're working on a separation.

    ```javascript linenums="1"
    curl -X POST "https://api-manage.fanz.io/merchants/login" \
    -H "accept: application/json" -H "Content-Type: application/json" \
    -d '{
            "email":"{EMAIL}",
            "password":"{PASSWORD}",
        }'
    ```
    






## API reference

!!! warning "Work in progress"

    As you read this, the API is currently a moving target - but a very small one.

You will find the OpenAPI specification [here](https://voucher-api-dev.fanz.io/documentation).
