# WebhooksCreateRequest

## Example Usage

```typescript
import { WebhooksCreateRequest } from "@mag3nt/sdk/models/operations";

let value: WebhooksCreateRequest = {
  url: "https://api.acme.com/hooks/mag3nt",
};
```

## Fields

| Field                                   | Type                                    | Required                                | Description                             | Example                                 |
| --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- |
| `url`                                   | *string*                                | :heavy_check_mark:                      | HTTPS endpoint that will receive events | https://api.acme.com/hooks/mag3nt       |
| `description`                           | *string*                                | :heavy_minus_sign:                      | Optional label for this webhook         |                                         |