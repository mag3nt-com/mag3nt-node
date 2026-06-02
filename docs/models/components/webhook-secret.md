# WebhookSecret

Returned ONLY when a webhook is created. The secret is used to verify the X-mag3nt-Signature header on delivered events and cannot be retrieved again.


## Example Usage

```typescript
import { WebhookSecret } from "@mag3nt/sdk/models/components";

let value: WebhookSecret = {
  id: "wh_3b9fe670abcdef...",
  status: "ACTIVE",
  secret: "whsec_1a2b3c4d5e6f...",
};
```

## Fields

| Field                                                        | Type                                                         | Required                                                     | Description                                                  | Example                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *string*                                                     | :heavy_minus_sign:                                           | N/A                                                          | wh_3b9fe670abcdef...                                         |
| `url`                                                        | *string*                                                     | :heavy_minus_sign:                                           | N/A                                                          |                                                              |
| `description`                                                | *string*                                                     | :heavy_minus_sign:                                           | N/A                                                          |                                                              |
| `status`                                                     | *string*                                                     | :heavy_minus_sign:                                           | N/A                                                          | ACTIVE                                                       |
| `secret`                                                     | *string*                                                     | :heavy_minus_sign:                                           | HMAC signing secret (whsec_...). Store securely; shown once. | whsec_1a2b3c4d5e6f...                                        |
| `note`                                                       | *string*                                                     | :heavy_minus_sign:                                           | N/A                                                          |                                                              |