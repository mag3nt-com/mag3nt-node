# PaymentSettledEvent

Body POSTed to a registered webhook when a pay link settles. Signed via the X-mag3nt-Signature header (t=<unix>,v1=<hex hmac-sha256 of `${t}.${rawBody}`>). Verify with your webhook secret before acting.


## Example Usage

```typescript
import { PaymentSettledEvent } from "@mag3nt/sdk/models/components";

let value: PaymentSettledEvent = {
  id: "evt_9f8e7d...",
  type: "payment.settled",
  created: 1780319099,
  data: {
    asset: "USDC",
    network: "eip155:8453",
  },
};
```

## Fields

| Field                                              | Type                                               | Required                                           | Description                                        | Example                                            |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `id`                                               | *string*                                           | :heavy_minus_sign:                                 | N/A                                                | evt_9f8e7d...                                      |
| `type`                                             | [components.Type](../../models/components/type.md) | :heavy_minus_sign:                                 | N/A                                                | payment.settled                                    |
| `created`                                          | *number*                                           | :heavy_minus_sign:                                 | Unix timestamp (seconds)                           | 1780319099                                         |
| `data`                                             | [components.Data](../../models/components/data.md) | :heavy_minus_sign:                                 | N/A                                                |                                                    |