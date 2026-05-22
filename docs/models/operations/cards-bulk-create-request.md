# CardsBulkCreateRequest

## Example Usage

```typescript
import { CardsBulkCreateRequest } from "@mag3nt/sdk/models/operations";

let value: CardsBulkCreateRequest = {
  body: {
    cards: [],
  },
};
```

## Fields

| Field                                                                                              | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `idempotencyKey`                                                                                   | *string*                                                                                           | :heavy_minus_sign:                                                                                 | Unique key to prevent duplicate bulk operations                                                    |
| `body`                                                                                             | [operations.CardsBulkCreateRequestBody](../../models/operations/cards-bulk-create-request-body.md) | :heavy_check_mark:                                                                                 | N/A                                                                                                |