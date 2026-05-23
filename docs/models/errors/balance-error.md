# BalanceError

## Example Usage

```typescript
import { BalanceError } from "@mag3nt/sdk/models/errors";

// No examples available for this model
```

## Fields

| Field                              | Type                               | Required                           | Description                        | Example                            |
| ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- |
| `error`                            | *string*                           | :heavy_check_mark:                 | N/A                                | Insufficient balance               |
| `available`                        | *components.BalanceErrorAvailable* | :heavy_check_mark:                 | N/A                                | 40                                 |
| `requested`                        | *components.Requested*             | :heavy_check_mark:                 | N/A                                | 50                                 |
| `network`                          | *string*                           | :heavy_minus_sign:                 | N/A                                | eip155:8453                        |
| `asset`                            | *string*                           | :heavy_minus_sign:                 | N/A                                | USDC                               |