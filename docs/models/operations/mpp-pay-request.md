# MppPayRequest

## Example Usage

```typescript
import { MppPayRequest } from "@mag3nt/sdk/models/operations";

let value: MppPayRequest = {
  cardId: "<id>",
  cardToken: "<value>",
  amount: 918.77,
};
```

## Fields

| Field                     | Type                      | Required                  | Description               |
| ------------------------- | ------------------------- | ------------------------- | ------------------------- |
| `cardId`                  | *string*                  | :heavy_check_mark:        | N/A                       |
| `cardToken`               | *string*                  | :heavy_check_mark:        | N/A                       |
| `amount`                  | *operations.MppPayAmount* | :heavy_check_mark:        | N/A                       |
| `merchant`                | *string*                  | :heavy_minus_sign:        | N/A                       |
| `merchantAddress`         | *string*                  | :heavy_minus_sign:        | N/A                       |
| `network`                 | *string*                  | :heavy_minus_sign:        | N/A                       |