# FundingVerifyRequest

## Example Usage

```typescript
import { FundingVerifyRequest } from "@mag3nt/sdk/models/operations";

let value: FundingVerifyRequest = {
  txHash: "<value>",
};
```

## Fields

| Field                               | Type                                | Required                            | Description                         |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `txHash`                            | *string*                            | :heavy_check_mark:                  | On-chain transaction hash to verify |
| `network`                           | *string*                            | :heavy_minus_sign:                  | N/A                                 |
| `asset`                             | *string*                            | :heavy_minus_sign:                  | N/A                                 |