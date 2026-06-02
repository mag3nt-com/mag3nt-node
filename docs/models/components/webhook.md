# Webhook

## Example Usage

```typescript
import { Webhook } from "@mag3nt/sdk/models/components";

let value: Webhook = {
  id: "wh_3b9fe670abcdef...",
  url: "https://api.acme.com/hooks/mag3nt",
  description: "Release API access on payment",
  status: "ACTIVE",
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   | Example                                                                                       |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `id`                                                                                          | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           | wh_3b9fe670abcdef...                                                                          |
| `url`                                                                                         | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           | https://api.acme.com/hooks/mag3nt                                                             |
| `description`                                                                                 | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           | Release API access on payment                                                                 |
| `status`                                                                                      | [components.WebhookStatus](../../models/components/webhook-status.md)                         | :heavy_minus_sign:                                                                            | N/A                                                                                           | ACTIVE                                                                                        |
| `createdAt`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           |                                                                                               |