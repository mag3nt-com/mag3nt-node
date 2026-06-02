# X402

## Overview

HTTP 402 payment protocol

### Available Operations

* [~~x402Pay~~](#x402pay) - (Removed) Pay for a service via x402 protocol :warning: **Deprecated**
* [x402Discover](#x402discover) - Discover x402 payment requirements for a URL
* [x402Receive](#x402receive) - Verify and accept an x402 payment

## ~~x402Pay~~

This proprietary push endpoint has been removed. Use POST /api/pay with { card_id, card_token, url } instead. It automatically detects x402 and settles on-chain.


> :warning: **DEPRECATED**: This will be removed in a future release, please migrate away from it as soon as possible.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="x402Pay" method="post" path="/api/x402/pay" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  await mag3nt.x402.x402Pay();


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { x402X402Pay } from "@mag3nt/sdk/funcs/x402-x402-pay.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await x402X402Pay(mag3nt);
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("x402X402Pay failed:", res.error);
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

**Promise\<void\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.X402PayGoneError   | 410                       | application/json          |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## x402Discover

Discover x402 payment requirements for a URL

### Example Usage

<!-- UsageSnippet language="typescript" operationID="x402Discover" method="get" path="/api/x402/discover" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.x402.x402Discover("https://happy-fireplace.name/");

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { x402X402Discover } from "@mag3nt/sdk/funcs/x402-x402-discover.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await x402X402Discover(mag3nt, "https://happy-fireplace.name/");
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("x402X402Discover failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `url`                                                                                                                                                                          | *string*                                                                                                                                                                       | :heavy_check_mark:                                                                                                                                                             | N/A                                                                                                                                                                            |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.X402DiscoverResponse](../../models/operations/x402-discover-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## x402Receive

Verify and accept an x402 payment

### Example Usage

<!-- UsageSnippet language="typescript" operationID="x402Receive" method="post" path="/api/x402/receive" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.x402.x402Receive({});

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { x402X402Receive } from "@mag3nt/sdk/funcs/x402-x402-receive.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await x402X402Receive(mag3nt, {});
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("x402X402Receive failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.X402ReceiveRequest](../../models/operations/x402-receive-request.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.X402ReceiveResponse](../../models/operations/x402-receive-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |