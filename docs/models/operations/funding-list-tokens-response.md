# FundingListTokensResponse

Token registry

## Example Usage

```typescript
import { FundingListTokensResponse } from "@mag3nt/sdk/models/operations";

let value: FundingListTokensResponse = {
  registry: {
    "eip155:8453": [
      {
        symbol: "USDC",
        type: "erc20",
        decimals: 6,
        contract: "0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913",
      },
    ],
  },
};
```

## Fields

| Field                                                                                                                                 | Type                                                                                                                                  | Required                                                                                                                              | Description                                                                                                                           | Example                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `registry`                                                                                                                            | Record<string, [operations.Registry](../../models/operations/registry.md)[]>                                                          | :heavy_minus_sign:                                                                                                                    | Map of CAIP-2 network IDs to supported tokens                                                                                         | {<br/>"eip155:8453": [<br/>{<br/>"symbol": "USDC",<br/>"type": "erc20",<br/>"decimals": 6,<br/>"contract": "0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913"<br/>}<br/>]<br/>} |