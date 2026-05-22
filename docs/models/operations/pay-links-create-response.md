# PayLinksCreateResponse

Pay link created

## Example Usage

```typescript
import { PayLinksCreateResponse } from "@mag3nt/sdk/models/operations";

let value: PayLinksCreateResponse = {
  payLink: {
    code: "PL_a1b2c3d4",
    url: "https://mag3nt.com/pay/PL_a1b2c3d4",
  },
};
```

## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `success`                                                 | *boolean*                                                 | :heavy_minus_sign:                                        | N/A                                                       |
| `payLink`                                                 | [components.PayLink](../../models/components/pay-link.md) | :heavy_minus_sign:                                        | N/A                                                       |