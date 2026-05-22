# PayLinksListResponse

Pay links list

## Example Usage

```typescript
import { PayLinksListResponse } from "@mag3nt/sdk/models/operations";

let value: PayLinksListResponse = {
  payLinks: [
    {
      code: "PL_a1b2c3d4",
      url: "https://mag3nt.com/pay/PL_a1b2c3d4",
    },
  ],
};
```

## Fields

| Field                                                       | Type                                                        | Required                                                    | Description                                                 |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| `payLinks`                                                  | [components.PayLink](../../models/components/pay-link.md)[] | :heavy_minus_sign:                                          | N/A                                                         |