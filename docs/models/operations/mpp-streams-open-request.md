# MppStreamsOpenRequest

## Example Usage

```typescript
import { MppStreamsOpenRequest } from "@mag3nt/sdk/models/operations";

let value: MppStreamsOpenRequest = {
  cardId: "<id>",
  cardToken: "<value>",
  budget: 5319.59,
  tickAmount: 7184.46,
};
```

## Fields

| Field                               | Type                                | Required                            | Description                         |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `cardId`                            | *string*                            | :heavy_check_mark:                  | N/A                                 |
| `cardToken`                         | *string*                            | :heavy_check_mark:                  | N/A                                 |
| `budget`                            | *number*                            | :heavy_check_mark:                  | Total budget for the stream in USDC |
| `tickAmount`                        | *number*                            | :heavy_check_mark:                  | Amount per tick                     |
| `receiverCardId`                    | *string*                            | :heavy_minus_sign:                  | N/A                                 |