# MppStreamsOpenRequest

## Example Usage

```typescript
import { MppStreamsOpenRequest } from "@mag3nt/sdk/models/operations";

let value: MppStreamsOpenRequest = {
  cardId: "<id>",
  cardToken: "<value>",
  budget: "<value>",
  tickAmount: "<value>",
};
```

## Fields

| Field                               | Type                                | Required                            | Description                         |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `cardId`                            | *string*                            | :heavy_check_mark:                  | N/A                                 |
| `cardToken`                         | *string*                            | :heavy_check_mark:                  | N/A                                 |
| `budget`                            | *operations.BudgetRequest*          | :heavy_check_mark:                  | Total budget for the stream in USDC |
| `tickAmount`                        | *operations.TickAmountRequest*      | :heavy_check_mark:                  | Amount per tick                     |
| `receiverCardId`                    | *string*                            | :heavy_minus_sign:                  | N/A                                 |