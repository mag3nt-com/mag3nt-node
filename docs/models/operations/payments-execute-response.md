# PaymentsExecuteResponse

Payment successful

## Example Usage

```typescript
import { PaymentsExecuteResponse } from "@mag3nt/sdk/models/operations";

let value: PaymentsExecuteResponse = {};
```

## Fields

| Field                                                                                          | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `success`                                                                                      | *boolean*                                                                                      | :heavy_minus_sign:                                                                             | N/A                                                                                            |
| `transactionId`                                                                                | *string*                                                                                       | :heavy_minus_sign:                                                                             | N/A                                                                                            |
| `amountDebited`                                                                                | *number*                                                                                       | :heavy_minus_sign:                                                                             | N/A                                                                                            |
| `merchantAmount`                                                                               | *number*                                                                                       | :heavy_minus_sign:                                                                             | N/A                                                                                            |
| `platformFee`                                                                                  | *number*                                                                                       | :heavy_minus_sign:                                                                             | N/A                                                                                            |
| `token`                                                                                        | *string*                                                                                       | :heavy_minus_sign:                                                                             | N/A                                                                                            |
| `network`                                                                                      | *string*                                                                                       | :heavy_minus_sign:                                                                             | N/A                                                                                            |
| `protocol`                                                                                     | *string*                                                                                       | :heavy_minus_sign:                                                                             | N/A                                                                                            |
| `settlement`                                                                                   | [operations.PaymentsExecuteSettlement](../../models/operations/payments-execute-settlement.md) | :heavy_minus_sign:                                                                             | N/A                                                                                            |