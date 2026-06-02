# Webhooks

## Overview

Signed payment.settled notifications for sellers

### Available Operations

* [webhooksCreate](#webhookscreate) - Register a webhook endpoint
* [webhooksList](#webhookslist) - List registered webhooks
* [webhooksDelete](#webhooksdelete) - Delete a webhook endpoint

## webhooksCreate

Register an HTTPS endpoint to receive signed `payment.settled` events when your pay links settle. The signing secret is returned ONCE in this response and cannot be retrieved again. Use it to verify the X-mag3nt-Signature header on each delivery. Max 5 active webhooks per wallet. URLs must be https and may not target private/loopback hosts.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="webhooksCreate" method="post" path="/api/webhooks" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.webhooks.webhooksCreate({
    url: "https://api.acme.com/hooks/mag3nt",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { webhooksWebhooksCreate } from "@mag3nt/sdk/funcs/webhooks-webhooks-create.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await webhooksWebhooksCreate(mag3nt, {
    url: "https://api.acme.com/hooks/mag3nt",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("webhooksWebhooksCreate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.WebhooksCreateRequest](../../models/operations/webhooks-create-request.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.WebhookSecret](../../models/components/webhook-secret.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401                  | application/json          |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## webhooksList

Returns all webhooks for the authenticated wallet. Secrets are never returned.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="webhooksList" method="get" path="/api/webhooks" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.webhooks.webhooksList();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { webhooksWebhooksList } from "@mag3nt/sdk/funcs/webhooks-webhooks-list.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await webhooksWebhooksList(mag3nt);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("webhooksWebhooksList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.WebhooksListResponse](../../models/operations/webhooks-list-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401                       | application/json          |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## webhooksDelete

Delete a webhook endpoint

### Example Usage

<!-- UsageSnippet language="typescript" operationID="webhooksDelete" method="delete" path="/api/webhooks/{id}" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.webhooks.webhooksDelete("<id>");

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { webhooksWebhooksDelete } from "@mag3nt/sdk/funcs/webhooks-webhooks-delete.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await webhooksWebhooksDelete(mag3nt, "<id>");
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("webhooksWebhooksDelete failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `id`                                                                                                                                                                           | *string*                                                                                                                                                                       | :heavy_check_mark:                                                                                                                                                             | N/A                                                                                                                                                                            |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.WebhooksDeleteResponse](../../models/operations/webhooks-delete-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 403, 404                  | application/json          |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |