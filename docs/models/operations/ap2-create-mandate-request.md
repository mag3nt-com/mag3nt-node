# Ap2CreateMandateRequest

## Example Usage

```typescript
import { Ap2CreateMandateRequest } from "@mag3nt/sdk/models/operations";

let value: Ap2CreateMandateRequest = {
  cardId: "<id>",
  cardToken: "<value>",
  amount: "852.40",
  merchant: "<value>",
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `cardId`                                                                                      | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `cardToken`                                                                                   | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `amount`                                                                                      | *operations.Ap2CreateMandateAmount*                                                           | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `merchant`                                                                                    | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `maxAmount`                                                                                   | *operations.MaxAmount*                                                                        | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `expiresAt`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           |