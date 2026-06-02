# FundingVerifyResponse

Funding verified or pending

## Example Usage

```typescript
import { FundingVerifyResponse } from "@mag3nt/sdk/models/operations";

let value: FundingVerifyResponse = {};
```

## Fields

| Field                                                                              | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `success`                                                                          | *boolean*                                                                          | :heavy_minus_sign:                                                                 | N/A                                                                                |
| `status`                                                                           | [operations.FundingVerifyStatus](../../models/operations/funding-verify-status.md) | :heavy_minus_sign:                                                                 | N/A                                                                                |
| `funded`                                                                           | *operations.Funded*                                                                | :heavy_minus_sign:                                                                 | Amount credited from this transaction                                              |
| `balance`                                                                          | [components.Balance](../../models/components/balance.md)                           | :heavy_minus_sign:                                                                 | N/A                                                                                |