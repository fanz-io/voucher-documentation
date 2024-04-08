## Create a default voucher (`POST`)

**URL** /merchants/`${merchantId}`/vouchers

=== "cURL"

    ``` javascript linenums="1"
    curl --location 'localhost:3000/merchants/6543f1a747d45f218ed0071e/vouchers' \
    --header 'Content-Type: application/json' \
    --data '{
        "amount": 23.12,
        "reference": "POSTMAN",
        "type": "AMOUNt",
        "name": "Stefans Vouchers",
        "description": "Wir testen nur mal"
        }'
    ```