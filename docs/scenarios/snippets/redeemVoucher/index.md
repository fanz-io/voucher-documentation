<!--start-->
## Redeem voucher (`POST`)
{%
    include "../requestAuth.md"
%}
**URL** /vouchers/`${voucherCode}`/redeem


```javascript linenums="1"
{
    "amountToPay": 49.99,
    "merchantId": "the-id-of-the-merchant",
    "order": {
        "cart": [
            {
                "productId": "ABC-1",
                "productName": "Sandalen Gr. 42",
                "unitPrice": 12.99,
                "pieces": 2
            },
            {
                "productId": "SONC-1",
                "productName": "Sonnencreme LSF 'Nutella'",
                "unitPrice": 24.01,
                "pieces: 1
            }
        ]
    },
    "callback": {
        "url": "https://i-called-you.com/voucher/hook",
        "headerName": "X-API-KEY",
        "headerAuth": "mySecretApiKey"
    }
}
```

| Property | Type | Description | Mandatory | 
| ------ | ----------- | ----------- | ----- |
| amountToPay | number  | The amount the cart has.  | yes |
| merchantId | objectId  | The Fanz Merchant-Id  | yes |
| order | object | Your payload you want to proxy. It will be the body of `callback` | no | 
| callback | object | Get notified, when a voucher is redeemed. | should |

### PERCENTAGE voucher

If it's a percentage voucher, the redeemation is straight forward: **The whole voucher code will marked as `REDEEMED` and is not available anymore**.

### AMOUNT voucher

If you reedem a voucher with an amount it's quiet different.
Let's explain three possible scenarios:

#### Amount to pay is higher than amount of voucher

Straight forward: **Voucher is completely `REDEEMED`**.

#### Amount to pay is equal to amount of voucher

Straight forward: **Voucher is completely `REDEEMED`**.

#### Amount to pay is lower than amount of voucher

The only exception, **BUT** our system is designed to handle that.

Let's create an example.

>   You have a voucher with an amount of EUR 100. <br>
    Your cart have items for EUR 49.99.<br>
    If you redeem your voucher you have EUR 50.01 left.

You can use the voucher code until the amount is EUR 0 (Zero).



### QUOTA voucher


<!--end-->