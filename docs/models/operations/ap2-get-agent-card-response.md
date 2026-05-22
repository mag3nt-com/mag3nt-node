# Ap2GetAgentCardResponse

Agent card

## Example Usage

```typescript
import { Ap2GetAgentCardResponse } from "@mag3nt/sdk/models/operations";

let value: Ap2GetAgentCardResponse = {
  agentCard: {
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
};
```

## Fields

| Field                                              | Type                                               | Required                                           | Description                                        |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `agentCard`                                        | [components.Card](../../models/components/card.md) | :heavy_minus_sign:                                 | N/A                                                |