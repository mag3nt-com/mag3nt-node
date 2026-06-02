# Ap2SettleResponseBody1

Settlement complete

## Example Usage

```typescript
import { Ap2SettleResponseBody1 } from "@mag3nt/sdk/models/operations";

let value: Ap2SettleResponseBody1 = {
  status: "SETTLED",
  protocol: "ap2",
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       | Example                                           |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `status`                                          | *string*                                          | :heavy_minus_sign:                                | SETTLED, or ALREADY_SETTLED on idempotent replay. | SETTLED                                           |
| `protocol`                                        | *string*                                          | :heavy_minus_sign:                                | N/A                                               | ap2                                               |
| `settlementId`                                    | *string*                                          | :heavy_minus_sign:                                | N/A                                               |                                                   |
| `mandateId`                                       | *string*                                          | :heavy_minus_sign:                                | The mandate jti the settlement is keyed on.       |                                                   |
| `payLinkCode`                                     | *string*                                          | :heavy_minus_sign:                                | N/A                                               |                                                   |
| `amount`                                          | *operations.Ap2SettleAmount*                      | :heavy_minus_sign:                                | N/A                                               |                                                   |
| `fee`                                             | *operations.Fee*                                  | :heavy_minus_sign:                                | N/A                                               |                                                   |
| `netAmount`                                       | *operations.Ap2SettleNetAmount*                   | :heavy_minus_sign:                                | N/A                                               |                                                   |
| `txHash`                                          | *string*                                          | :heavy_minus_sign:                                | N/A                                               |                                                   |
| `payee`                                           | *string*                                          | :heavy_minus_sign:                                | N/A                                               |                                                   |