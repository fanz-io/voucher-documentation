<!--start-->
# Voucher

## Properties
Our voucher entity has multiple properties you can control.

### amount (`numeric`) ~**required**~

The numeric is the value, which defines the reduction of the amount to pay.

!!! example "Example"
    `44`

!!! danger "If not provided..."
    ```javascript
    {
        "message": "AMOUNT_REQUIRED",
        "error": "Bad Request",
        "statusCode": 400
    }
    ```

### type (`VoucherType`) ~**required**~

The type of the voucher defines if the amount is just an amount of money, that will be substracted or if it's a percentage value.

| Value        | Description                                 | 
| ------------ | ------------------------------------------- | 
| `AMOUNT`     | The [amount](#amount) is (money) value.|    | 
| `PERCENTAGE` | The [amount](#amount) is a percentage value.| 

!!! example "Example"
    `PERCENTAGE`

!!! danger "If not provided..."
    ```javascript
    {
        "message": "TYPE_REQUIRED",
        "error": "Bad Request",
        "statusCode": 400
    }
    ```

### name (`string`)

A voucher can have a name. The value will not be displayed when redeeming a voucher.
You will retrieve this information via webhook payload.

!!! example Example
    `Et tu, Brute?`

### description (`string`)

A voucher can have a description. The value will not be displayed when redeeming a voucher.
You will retrieve this information via webhook payload.

!!! example "Example"
    `Alea iacta est - A Latin proverb, but stolen from the Greek.`

### reference (`string`)

For analysis you can add a reference to a voucher to keep track of the status. 

!!! example "Example"
    `Folio: 0815`

### code (`string`)

You can provide a code on your own. But you can also use the [CodeGenerator](#codegeneratorsettings-vouchercodegeneratorsettings)

!!! example Example
    `MY-CODE-2024`

### validFrom (`date`)
You can create a voucher that will only become valid in the future.

!!! abstract "Format"
    As defined in `ISO 8601` use a date time format like `YYYY-MM-DDThh:mm:ss`.

!!! tip "Default"
    DateTime of creation.

!!! example Example
    `1987-12-23T11:54:00`

### validUntil (`date`)

You can create a voucher that will only become valid in the future.

!!! abstract "Format"
    As defined in `ISO 8601` use a date time format like `YYYY-MM-DDThh:mm:ss`.

!!! tip "Default"
    validFrom + 1 year

!!! example Example
    `1988-12-23T11:54:00`

### usage (`VoucherUsage`)

A voucher is assigned to a specific group of people, e.g. to carry out targeted marketing campaigns with a voucher.

| Value      | Description                                | Default|
| ---------- | ------------------------------------------ | :-----: |
| `PUBLIC`   | The voucher code is available for everyone.|  |
| `CUSTOMER` | The voucher is for **one** specific customer.    |  :material-check:      |

!!! example "Example"
    `PUBLIC`

### quota (`number`)

A quota limits the generation of a voucher.
If you created a voucher for a campaign you can limit how often the voucher could redeemed.

!!! tip "Explanation"

    - Let's asume, you're having a campaign for example "The first 100 will have a 5 %".
    - The voucher code is **FIRST100**
    - So if guest performs the checkout and enters **FIRST100** as voucher code, the system
    will do the following:
        1. If there's a quota left, the amount will be reduced by 5 %.
        2. If there's no quota left, the guest will not have a reduction.

!!! example "Example"
    `100`

### default (`boolean`)

This voucher will be the blueprint for creating vouchers for [`usage.CUSTOMER`](#usage) if
you want to invite guest to join your voucher program.

!!! tip "Default"
    `false`

### deactivated (`boolean`)

Easily mark a voucher as not valid anymore.

!!! tip "Default"
    `false`

### customerReference (`json`)

You can provide more details about the owner of the voucher - if you have.

!!! tip "Object definition"
    We recommend to use this structure, to serialize the data.
    Provide only fields you have.

    ```javascript
    {
        "email": "",
        "firstname": "",
        "lastname": "",
        "phone": ""
        "salutation": "Choose from `Mr`, `Mrs`"
    }

    ```

### thirdPartyPayload (`json`)

You can add own information to a generated voucher. 

!!! warning "We will not process any of the information in this property"

!!! tip "Object definition"
    It's up to you, what you want to add.

    ```javascript
    {
        "appRef": "",
        "customerId": "",
        "arragementId": "",
    }

    ```

### codeGeneratorSettings (`VoucherCodeGeneratorSettings`)

You can use a built in generator to let you create codes.

!!! explanation "Definition"
    {%
        include "../scenarios/snippets/codeGeneratorSettings.md"
    %}
<!--end-->