# StatusGetResponse

Platform status and protocol manifest

## Example Usage

```typescript
import { StatusGetResponse } from "@mag3nt/sdk/models/operations";

let value: StatusGetResponse = {
  platform: "mag3nt",
  version: "0.5.0",
  model: "bidirectional",
  protocols: {
    x402: {
      spend: "/api/pay",
    },
    mpp: {
      spend: "/api/pay",
    },
  },
};
```

## Fields

| Field                                                               | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `platform`                                                          | *string*                                                            | :heavy_minus_sign:                                                  | N/A                                                                 | mag3nt                                                              |
| `version`                                                           | *string*                                                            | :heavy_minus_sign:                                                  | N/A                                                                 | 0.5.0                                                               |
| `model`                                                             | *string*                                                            | :heavy_minus_sign:                                                  | N/A                                                                 | bidirectional                                                       |
| `protocols`                                                         | [operations.Protocols](../../models/operations/protocols.md)        | :heavy_minus_sign:                                                  | N/A                                                                 |                                                                     |
| `cardControls`                                                      | [operations.CardControls](../../models/operations/card-controls.md) | :heavy_minus_sign:                                                  | N/A                                                                 |                                                                     |