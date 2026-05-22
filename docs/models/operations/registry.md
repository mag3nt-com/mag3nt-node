# Registry

## Example Usage

```typescript
import { Registry } from "@mag3nt/sdk/models/operations";

let value: Registry = {
  symbol: "USDC",
  type: "erc20",
  decimals: 6,
  contract: "0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913",
};
```

## Fields

| Field                                      | Type                                       | Required                                   | Description                                | Example                                    |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `symbol`                                   | *string*                                   | :heavy_minus_sign:                         | N/A                                        | USDC                                       |
| `type`                                     | *string*                                   | :heavy_minus_sign:                         | N/A                                        | erc20                                      |
| `decimals`                                 | *number*                                   | :heavy_minus_sign:                         | N/A                                        | 6                                          |
| `contract`                                 | *string*                                   | :heavy_minus_sign:                         | N/A                                        | 0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913 |