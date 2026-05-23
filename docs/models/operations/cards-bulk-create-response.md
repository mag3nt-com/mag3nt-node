# CardsBulkCreateResponse

Cards created

## Example Usage

```typescript
import { CardsBulkCreateResponse } from "@mag3nt/sdk/models/operations";

let value: CardsBulkCreateResponse = {
  cards: [
    {
      id: "sx_a66a6666-1234-5678-9abc-def012345678",
      token: "tok_3b9fe670-abcd-efgh-ijkl-mnopqrstuvwx",
      purpose: "Research Agent",
      limitAmount: 50,
      status: "ACTIVE",
      mccLocks: "",
      singleUse: 0,
      fundingNetwork: "eip155:8453",
      fundingAsset: "USDC",
      walletAddress: "0x1234...abcd",
      balance: 0,
      remaining: 50,
    },
  ],
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `success`                                            | *boolean*                                            | :heavy_minus_sign:                                   | N/A                                                  |
| `cards`                                              | [components.Card](../../models/components/card.md)[] | :heavy_minus_sign:                                   | N/A                                                  |
| `totalAllocated`                                     | *operations.TotalAllocated*                          | :heavy_minus_sign:                                   | N/A                                                  |