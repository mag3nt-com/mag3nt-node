# Ap2ExecuteRequest

## Example Usage

```typescript
import { Ap2ExecuteRequest } from "@mag3nt/sdk/models/operations";

let value: Ap2ExecuteRequest = {
  cardId: "<id>",
  cardToken: "<value>",
  amount: 3943.32,
};
```

## Fields

| Field                         | Type                          | Required                      | Description                   |
| ----------------------------- | ----------------------------- | ----------------------------- | ----------------------------- |
| `cardId`                      | *string*                      | :heavy_check_mark:            | N/A                           |
| `cardToken`                   | *string*                      | :heavy_check_mark:            | N/A                           |
| `amount`                      | *operations.Ap2ExecuteAmount* | :heavy_check_mark:            | N/A                           |
| `mandateId`                   | *string*                      | :heavy_minus_sign:            | N/A                           |