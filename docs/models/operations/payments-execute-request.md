# PaymentsExecuteRequest

## Example Usage

```typescript
import { PaymentsExecuteRequest } from "@mag3nt/sdk/models/operations";

let value: PaymentsExecuteRequest = {
  cardId: "<id>",
  cardToken: "<value>",
  url: "https://unimportant-freckle.name/",
};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `cardId`                                                 | *string*                                                 | :heavy_check_mark:                                       | Card identifier (sx_...)                                 |
| `cardToken`                                              | *string*                                                 | :heavy_check_mark:                                       | Card secret token (tok_...)                              |
| `url`                                                    | *string*                                                 | :heavy_check_mark:                                       | The external payment-protected URL to pay                |
| `method`                                                 | *string*                                                 | :heavy_minus_sign:                                       | HTTP method to use when probing the URL                  |
| `body`                                                   | [operations.Body](../../models/operations/body.md)       | :heavy_minus_sign:                                       | JSON request body to trigger a priced challenge          |
| `headers`                                                | [operations.Headers](../../models/operations/headers.md) | :heavy_minus_sign:                                       | Optional headers for the probe request                   |