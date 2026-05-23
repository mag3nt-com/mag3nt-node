# CardsCreateRequest

## Example Usage

```typescript
import { CardsCreateRequest } from "@mag3nt/sdk/models/operations";

let value: CardsCreateRequest = {
  purpose: "Research Agent",
  limitAmount: 50,
};
```

## Fields

| Field                                        | Type                                         | Required                                     | Description                                  | Example                                      |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `purpose`                                    | *string*                                     | :heavy_check_mark:                           | Human-readable label for the card            | Research Agent                               |
| `limitAmount`                                | *operations.CardsCreateLimitAmount*          | :heavy_check_mark:                           | Maximum spend in USDC                        | 50                                           |
| `network`                                    | *string*                                     | :heavy_minus_sign:                           | N/A                                          |                                              |
| `asset`                                      | *string*                                     | :heavy_minus_sign:                           | N/A                                          |                                              |
| `txHash`                                     | *string*                                     | :heavy_minus_sign:                           | On-chain funding transaction hash (optional) |                                              |
| `mccLocks`                                   | *string*                                     | :heavy_minus_sign:                           | Comma-separated merchant category codes      |                                              |
| `singleUse`                                  | *boolean*                                    | :heavy_minus_sign:                           | N/A                                          |                                              |
| `expiresIn`                                  | *number*                                     | :heavy_minus_sign:                           | Hours until expiry (0 = never)               |                                              |