<!--start-->
    Defines how the code should look like, when automatically generated.

    | Property | Type     | Description | Default |
    | -------- | -------- | ----------- | ------- | 
    | charset  | `enum`   | Defines, which chars sould be used. Can be `numerical`, `alphanumerical`, `alphabetical`.| `numerical`|
    | length   | `number` | Length of code | 8 | 
    | pattern  | `string` | You can define a patter by using `#`. Each `#` will be replaced by a char of the genrator code. All other than `#` will count as one character as well. | `####-###`|
    | prefix   | `string` | Use this to add something before the code. | `empty` |
    | suffix   | `string` | Use this to add someting to the end. | `empty` |
    | uppercase| `boolean`| If using `alphabetical` or `alphanumerical` all chars will be uppercase if `true` - otherwise it could be a mix of upper- and lowercase characters. | abc |
    
<!--end-->