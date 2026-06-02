# Ap2SettleRequest

## Example Usage

```typescript
import { Ap2SettleRequest } from "@mag3nt/sdk/models/operations";

let value: Ap2SettleRequest = {
  payerCardId: "<id>",
  payerCardToken: "<value>",
  receiverCardId: "<id>",
  amount: 9522.75,
};
```

## Fields

| Field                        | Type                         | Required                     | Description                  |
| ---------------------------- | ---------------------------- | ---------------------------- | ---------------------------- |
| `payerCardId`                | *string*                     | :heavy_check_mark:           | N/A                          |
| `payerCardToken`             | *string*                     | :heavy_check_mark:           | N/A                          |
| `receiverCardId`             | *string*                     | :heavy_check_mark:           | N/A                          |
| `amount`                     | *operations.Ap2SettleAmount* | :heavy_check_mark:           | N/A                          |
| `network`                    | *string*                     | :heavy_minus_sign:           | N/A                          |