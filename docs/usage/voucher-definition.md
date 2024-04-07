# Voucher

Our voucher has multiple options you can control.

## Amount (`numeric`)

The numeric is the value, which defines the reduction of the amount to pay.

!!! example "Example"

    `44`

## Name (`string`)

A voucher can have a name. The value will not be displayed when redeeming a voucher.
You will retrieve this information via webhook payload.

!!! example Example
    `Et tu, Brute?`

## Description (`string`)

A voucher can have a description. The value will not be displayed when redeeming a voucher.
You will retrieve this information via webhook payload.

!!! example "Example"
    `Alea iacta est - A Latin proverb, but stolen from the Greek.`

## validFrom (`date`)

You can create a voucher that will only become valid in the future.

!!! abstract "Format"
    As defined in `ISO 8601` use a date time format like `YYYY-MM-DDThh:mm:ss`.

!!! note "Default"
    DateTime of creation.

!!! example Example
    `1987-12-23T11:54:00`


## validUntil (`date`)

You can create a voucher that will only become valid in the future.

!!! abstract "Format"
    As defined in `ISO 8601` use a date time format like `YYYY-MM-DDThh:mm:ss`.

!!! note "Default"
    validFrom + 1 year

!!! example Example
    `1987-12-23T11:54:00`


