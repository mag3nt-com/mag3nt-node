# WithdrawalsCreateResponse

Withdrawal initiated

## Example Usage

```typescript
import { WithdrawalsCreateResponse } from "@mag3nt/sdk/models/operations";

let value: WithdrawalsCreateResponse = {
  status: "PROCESSING",
};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              | Example                                                  |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `success`                                                | *boolean*                                                | :heavy_minus_sign:                                       | N/A                                                      |                                                          |
| `withdrawalId`                                           | *string*                                                 | :heavy_minus_sign:                                       | N/A                                                      |                                                          |
| `amount`                                                 | *operations.WithdrawalsCreateAmountResponse*             | :heavy_minus_sign:                                       | Gross amount deducted from balance                       |                                                          |
| `withdrawalFee`                                          | *operations.WithdrawalFee*                               | :heavy_minus_sign:                                       | Flat network fee retained by platform                    |                                                          |
| `netAmount`                                              | *operations.WithdrawalsCreateNetAmount*                  | :heavy_minus_sign:                                       | Amount sent on-chain (amount - fee)                      |                                                          |
| `status`                                                 | *string*                                                 | :heavy_minus_sign:                                       | N/A                                                      | PROCESSING                                               |
| `balance`                                                | [components.Balance](../../models/components/balance.md) | :heavy_minus_sign:                                       | N/A                                                      |                                                          |