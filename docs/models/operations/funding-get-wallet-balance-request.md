# FundingGetWalletBalanceRequest

## Example Usage

```typescript
import { FundingGetWalletBalanceRequest } from "@mag3nt/sdk/models/operations";

let value: FundingGetWalletBalanceRequest = {
  network: "eip155:8453",
  asset: "USDC",
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       | Example                                           |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `network`                                         | *string*                                          | :heavy_check_mark:                                | N/A                                               | eip155:8453                                       |
| `asset`                                           | *string*                                          | :heavy_check_mark:                                | N/A                                               | USDC                                              |
| `address`                                         | *string*                                          | :heavy_minus_sign:                                | Wallet address (defaults to authenticated wallet) |                                                   |