<!--start-->
## Get vouchers - with filter (`GET`)
{%
    include "../requestAuth.md"
%}
**URL** /merchants/`${merchantId}`/vouchers

### by VoucherStatus (`Query-Parameter` voucherStatus)

| Status | Description |
| ------ | ----------- |
| COLLECT  | If you have a default voucher, you will get all generated vouchers based on your default voucher. | 
| REDEEM | You will receive all vouchers, that are redeemed while checkout. |
| CHECK | You will receive all vouchers, that were entered in the checkout process. | 
<!--end-->