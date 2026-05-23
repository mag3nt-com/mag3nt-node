# PayLinksCreateRequest

## Example Usage

```typescript
import { PayLinksCreateRequest } from "@mag3nt/sdk/models/operations";

let value: PayLinksCreateRequest = {
  cardId: "<id>",
};
```

## Fields

| Field                                                                             | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `cardId`                                                                          | *string*                                                                          | :heavy_check_mark:                                                                | N/A                                                                               |
| `amount`                                                                          | *operations.PayLinksCreateAmount*                                                 | :heavy_minus_sign:                                                                | Fixed amount (null for open-amount)                                               |
| `memo`                                                                            | *string*                                                                          | :heavy_minus_sign:                                                                | N/A                                                                               |
| `acceptedProtocols`                                                               | *string*[]                                                                        | :heavy_minus_sign:                                                                | N/A                                                                               |
| `type`                                                                            | [operations.PayLinksCreateType](../../models/operations/pay-links-create-type.md) | :heavy_minus_sign:                                                                | SINGLE for one-time, RECURRING for multi-use                                      |
| `maxUses`                                                                         | *number*                                                                          | :heavy_minus_sign:                                                                | N/A                                                                               |
| `expiresIn`                                                                       | *number*                                                                          | :heavy_minus_sign:                                                                | Hours until expiry                                                                |