# FundingGetWalletBalanceResponse

On-chain balance

## Example Usage

```typescript
import { FundingGetWalletBalanceResponse } from "@mag3nt/sdk/models/operations";

let value: FundingGetWalletBalanceResponse = {};
```

## Fields

| Field                                           | Type                                            | Required                                        | Description                                     |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| `network`                                       | *string*                                        | :heavy_minus_sign:                              | N/A                                             |
| `asset`                                         | *string*                                        | :heavy_minus_sign:                              | N/A                                             |
| `address`                                       | *string*                                        | :heavy_minus_sign:                              | N/A                                             |
| `balance`                                       | *number*                                        | :heavy_minus_sign:                              | Token balance in human units (e.g., 42.50 USDC) |