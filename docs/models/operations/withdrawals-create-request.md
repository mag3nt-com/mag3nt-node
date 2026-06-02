# WithdrawalsCreateRequest

## Example Usage

```typescript
import { WithdrawalsCreateRequest } from "@mag3nt/sdk/models/operations";

let value: WithdrawalsCreateRequest = {
  amount: 50,
  network: "eip155:8453",
  asset: "USDC",
};
```

## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   | Example                                                       |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `amount`                                                      | *operations.WithdrawalsCreateAmountRequest*                   | :heavy_check_mark:                                            | Gross amount to withdraw (fee is deducted from this)          | 50                                                            |
| `network`                                                     | *string*                                                      | :heavy_check_mark:                                            | CAIP-2 network to withdraw on                                 | eip155:8453                                                   |
| `asset`                                                       | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           | USDC                                                          |
| `toAddress`                                                   | *string*                                                      | :heavy_minus_sign:                                            | Destination wallet address (defaults to authenticated wallet) |                                                               |