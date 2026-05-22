# PaymentHeader

## Example Usage

```typescript
import { PaymentHeader } from "@mag3nt/sdk/models/components";

let value: PaymentHeader = {};
```

## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `xMag3ntTransaction`                                                             | *string*                                                                         | :heavy_minus_sign:                                                               | N/A                                                                              |
| `xMag3ntCard`                                                                    | *string*                                                                         | :heavy_minus_sign:                                                               | N/A                                                                              |
| `xMag3ntAmount`                                                                  | *string*                                                                         | :heavy_minus_sign:                                                               | N/A                                                                              |
| `xMag3ntProtocol`                                                                | *string*                                                                         | :heavy_minus_sign:                                                               | N/A                                                                              |
| `xMag3ntNetwork`                                                                 | *string*                                                                         | :heavy_minus_sign:                                                               | CAIP-2 network identifier                                                        |
| `xMag3ntEnvironment`                                                             | [components.XMag3ntEnvironment](../../models/components/x-mag3nt-environment.md) | :heavy_minus_sign:                                                               | 'sandbox' for testnet networks, 'production' for mainnet                         |