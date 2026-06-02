# WithdrawalsListRequest

## Example Usage

```typescript
import { WithdrawalsListRequest } from "@mag3nt/sdk/models/operations";

let value: WithdrawalsListRequest = {};
```

## Fields

| Field                                                                                  | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `id`                                                                                   | *string*                                                                               | :heavy_minus_sign:                                                                     | Look up a single withdrawal by ID                                                      |
| `status`                                                                               | [operations.WithdrawalsListStatus](../../models/operations/withdrawals-list-status.md) | :heavy_minus_sign:                                                                     | Filter by status                                                                       |