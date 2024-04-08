<!--start-->
## Deactivate vouchers (`POST`)
### by id
{%
    include "../requestAuth.md"
%}
**URL** /merchants/`${merchantId}`/vouchers/deactivate

Deactivate a single voucher

```javascript linenums="1"
{
    "id": "f85f3d36-0893-41e1-bbc3-8ee419e98107"
}
```

### by reference
{%
    include "../requestAuth.md"
%}
**URL** /merchants/`${merchantId}`/vouchers/deactivate

Deactivate a single voucher

```javascript linenums="1"
{
    "reference": "Marketing Spring 2024"
}
```


<!--end-->
