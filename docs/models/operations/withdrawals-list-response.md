# WithdrawalsListResponse

Withdrawals list

## Example Usage

```typescript
import { WithdrawalsListResponse } from "@mag3nt/sdk/models/operations";

let value: WithdrawalsListResponse = {
  withdrawals: [
    {
      id: "wd_a1b2c3d4-...",
      asset: "USDC",
      network: "eip155:8453",
    },
  ],
};
```

## Fields

| Field                                                            | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `withdrawals`                                                    | [components.Withdrawal](../../models/components/withdrawal.md)[] | :heavy_minus_sign:                                               | N/A                                                              |