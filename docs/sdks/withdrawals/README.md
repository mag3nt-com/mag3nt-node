# Withdrawals

## Overview

Withdraw unspent funds back to wallet

### Available Operations

* [withdrawalsCreate](#withdrawalscreate) - Withdraw unspent funds back to your wallet
* [withdrawalsList](#withdrawalslist) - List withdrawal history

## withdrawalsCreate

Initiates a withdrawal of USDC from your treasury balance to an on-chain wallet address. A flat network fee is deducted from the requested amount. The net amount is sent on-chain via CDP; the fee is retained as platform revenue. Withdrawals are processed asynchronously: check status via GET /api/withdrawals.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="withdrawalsCreate" method="post" path="/api/withdraw" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.withdrawals.withdrawalsCreate({
    amount: 50,
    network: "eip155:8453",
    asset: "USDC",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { withdrawalsWithdrawalsCreate } from "@mag3nt/sdk/funcs/withdrawals-withdrawals-create.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await withdrawalsWithdrawalsCreate(mag3nt, {
    amount: 50,
    network: "eip155:8453",
    asset: "USDC",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("withdrawalsWithdrawalsCreate failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.WithdrawalsCreateRequest](../../models/operations/withdrawals-create-request.md)                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.WithdrawalsCreateResponse](../../models/operations/withdrawals-create-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.BadRequestError    | 400                       | application/json          |
| errors.ForbiddenError     | 403                       | application/json          |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |

## withdrawalsList

Returns up to 50 most recent withdrawals for the authenticated wallet.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="withdrawalsList" method="get" path="/api/withdrawals" -->
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.withdrawals.withdrawalsList();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { Mag3ntCore } from "@mag3nt/sdk/core.js";
import { withdrawalsWithdrawalsList } from "@mag3nt/sdk/funcs/withdrawals-withdrawals-list.js";

// Use `Mag3ntCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const mag3nt = new Mag3ntCore({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const res = await withdrawalsWithdrawalsList(mag3nt);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("withdrawalsWithdrawalsList failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `id`                                                                                                                                                                           | *string*                                                                                                                                                                       | :heavy_minus_sign:                                                                                                                                                             | Look up a single withdrawal by ID                                                                                                                                              |
| `status`                                                                                                                                                                       | [operations.WithdrawalsListStatus](../../models/operations/withdrawals-list-status.md)                                                                                         | :heavy_minus_sign:                                                                                                                                                             | Filter by status                                                                                                                                                               |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.WithdrawalsListResponse](../../models/operations/withdrawals-list-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.Mag3ntDefaultError | 4XX, 5XX                  | \*/\*                     |