<!--start-->
## Create a volume of vouchers (`POST`)
{%
    include "../requestAuth.md"
%}
**URL** /merchants/`${merchantId}`/vouchers/quantity/`${quantity}`

We use the same base request as in [Create default voucher](#create-a-default-voucher-post).

!!! danger "BUT"
    ..we have to add a reference to identity all vouchers related to this volume-generation.

    If you don't provide a reference, you will end in an exception.

    ```javascript 
    {
        "message": "REFERENCE_REQUIRED",
        "error": "Bad Request",
        "statusCode": 400
    }
    ```

!!! danger "Limitations"
    Currently the maximum amount of vouchers you can create with one request is 
    limited to `1000`.

    If you exceed the limit per request, you will end in an exception.

    ```javascript
    {
       "message": "QUANTITY_EXCEEDED",
        "error": "Bad Request",
        "statusCode": 400 
    }
    ```
<!--end-->