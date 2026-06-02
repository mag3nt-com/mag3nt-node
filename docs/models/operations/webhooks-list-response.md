# WebhooksListResponse

Webhooks list

## Example Usage

```typescript
import { WebhooksListResponse } from "@mag3nt/sdk/models/operations";

let value: WebhooksListResponse = {
  webhooks: [
    {
      id: "wh_3b9fe670abcdef...",
      url: "https://api.acme.com/hooks/mag3nt",
      description: "Release API access on payment",
      status: "ACTIVE",
    },
  ],
};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `webhooks`                                                 | [components.Webhook](../../models/components/webhook.md)[] | :heavy_minus_sign:                                         | N/A                                                        |