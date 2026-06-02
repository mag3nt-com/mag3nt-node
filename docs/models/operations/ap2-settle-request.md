# Ap2SettleRequest

## Example Usage

```typescript
import { Ap2SettleRequest } from "@mag3nt/sdk/models/operations";

let value: Ap2SettleRequest = {
  payLinkCode: "pl_a1b2c3d4",
  closedMandate: "<value>",
  cardToken: "<value>",
};
```

## Fields

| Field                                                                         | Type                                                                          | Required                                                                      | Description                                                                   | Example                                                                       |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `payLinkCode`                                                                 | *string*                                                                      | :heavy_check_mark:                                                            | Code of the pay link being settled.                                           | pl_a1b2c3d4                                                                   |
| `closedMandate`                                                               | *string*                                                                      | :heavy_check_mark:                                                            | Closed AP2 Payment Mandate (mandate.payment.1) as an SD-JWT.                  |                                                                               |
| `openMandate`                                                                 | *string*                                                                      | :heavy_minus_sign:                                                            | Optional open AP2 mandate; when present the open→closed chain is re-verified. |                                                                               |
| `cardToken`                                                                   | *string*                                                                      | :heavy_check_mark:                                                            | Token of the payer card named by the mandate (authorizes the debit).          |                                                                               |