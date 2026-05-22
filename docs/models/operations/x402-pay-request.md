# X402PayRequest

## Example Usage

```typescript
import { X402PayRequest } from "@mag3nt/sdk/models/operations";

let value: X402PayRequest = {
  cardId: "sx_a66a6666-1234-5678-9abc-def012345678",
  cardToken: "tok_3b9fe670-abcd-efgh-ijkl-mnopqrstuvwx",
  amount: 0.5,
  merchant: "weather-api.com",
  merchantAddress: "0xABC...",
};
```

## Fields

| Field                                    | Type                                     | Required                                 | Description                              | Example                                  |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `cardId`                                 | *string*                                 | :heavy_check_mark:                       | Card identifier (sx_...)                 | sx_a66a6666-1234-5678-9abc-def012345678  |
| `cardToken`                              | *string*                                 | :heavy_check_mark:                       | Card secret token (tok_...)              | tok_3b9fe670-abcd-efgh-ijkl-mnopqrstuvwx |
| `amount`                                 | *number*                                 | :heavy_check_mark:                       | Payment amount in USDC                   | 0.5                                      |
| `merchant`                               | *string*                                 | :heavy_minus_sign:                       | Merchant identifier                      | weather-api.com                          |
| `merchantAddress`                        | *string*                                 | :heavy_minus_sign:                       | Merchant wallet for settlement           | 0xABC...                                 |
| `mcc`                                    | *string*                                 | :heavy_minus_sign:                       | Merchant category code                   |                                          |
| `resourceUrl`                            | *string*                                 | :heavy_minus_sign:                       | URL being paid for                       |                                          |
| `network`                                | *string*                                 | :heavy_minus_sign:                       | N/A                                      |                                          |