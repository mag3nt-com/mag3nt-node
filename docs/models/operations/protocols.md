# Protocols

## Example Usage

```typescript
import { Protocols } from "@mag3nt/sdk/models/operations";

let value: Protocols = {
  x402: {
    spend: "/api/pay",
  },
  mpp: {
    spend: "/api/pay",
  },
};
```

## Fields

| Field                                                                              | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `x402`                                                                             | [operations.X402](../../models/operations/x402.md)                                 | :heavy_minus_sign:                                                                 | N/A                                                                                |
| `ap2`                                                                              | [operations.Ap2](../../models/operations/ap2.md)                                   | :heavy_minus_sign:                                                                 | N/A                                                                                |
| `mpp`                                                                              | [operations.Mpp](../../models/operations/mpp.md)                                   | :heavy_minus_sign:                                                                 | N/A                                                                                |
| `settlement`                                                                       | [operations.StatusGetSettlement](../../models/operations/status-get-settlement.md) | :heavy_minus_sign:                                                                 | N/A                                                                                |