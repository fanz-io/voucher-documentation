<!--start-->
## Create a default voucher (`POST`)
{%
    include "../requestAuth.md"
%}
**URL** /merchants/`${merchantId}`/vouchers

!!! note
    In this scenario we're create a simple money value based voucher.

=== "Request with cURL"

    ``` javascript linenums="1"
    curl --location 'http://localhost:3000/merchants/6543f1a747d45f218ed0071e/vouchers' \
    --header 'Authorization: YOUR_API_KEY' \
    --header 'Content-Type: application/json' \
    --data '{
    "amount": 23.12,
    "type": "AMOUNT",
    "name": "Stefans Vouchers",
    "description": "Wir testen nur mal",
    "codeGeneratorSettings": {
                "charset": "numerical",
                "length": 12,
                "pattern": "####-####-##",
                "prefix": "CODE-",
                "suffix": "",
                "uppercase": true
            }
    }'
    ```

=== "Request with PHP Guzzle"

    ```php linenums="1"
    <?php
        $client = new Client();
        $headers = [
            'Content-Type' => 'application/json',
            'Authorization' => 'YOUR_API_KEY',
        ];
        $body = '{
            "amount": 23.12,
            "type": "AMOUNT",
            "name": "Stefans Vouchers",
            "description": "Wir testen nur mal",
                "codeGeneratorSettings": {
                    "charset": "numerical",
                    "length": 12,
                    "pattern": "####-####-##",
                    "prefix": "CODE-",
                    "suffix": "",
                    "uppercase": true
                }
        }';
        $request = new Request('POST', 'http://localhost:3000/merchants/6543f1a747d45f218ed0071e/vouchers', $headers, $body);
        $res = $client->sendAsync($request)->wait();
        echo $res->getBody();
    ?>
    ```


=== "Response"

    ```json linenums="1"
    {
        "amount": 23.12,
        "type": "AMOUNT",
        "name": "Stefans Vouchers",
        "description": "Wir testen nur mal",
        "codeGeneratorSettings": {
            "charset": "numerical",
            "length": 12,
            "pattern": "####-####-###",
            "prefix": "CODE-",
            "suffix": "",
            "uppercase": true
        },
        "merchantId": "6543f1a747d45f218ed0071e",
        "validFrom": "2024-04-08T07:45:27.123Z",
        "validUntil": "2025-04-08T07:45:27.123Z",
        "code": "CODE-5270-3530-42",
        "id": "bd7b6bdc-f335-444a-8bbd-4d20a03ea846",
        "initialAmount": 0,
        "purpose": "MULTIPLE",
        "createdAt": "2024-04-08T05:45:27.227Z",
        "sessionCode": "",
        "paid": false,
        "usage": "CUSTOMER",
        "default": false,
        "deactivated": false,
        "quota": 0
    }
    ```

??? "Usage of Code Generator"

    {%
        include "../codeGeneratorSettings.md"
    %}

<!--end-->