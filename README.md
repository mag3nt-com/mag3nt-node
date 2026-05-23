# @mag3nt/sdk

Developer-friendly & type-safe Typescript SDK specifically catered to leverage *@mag3nt/sdk* API.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=@mag3nt/sdk&utm_campaign=typescript)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/mag3nt/mag3nt-com). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

mag3nt API: Payment infrastructure for AI agents. Issue virtual cards, pay for API access via x402/AP2/MPP protocols, and settle in USDC on Base.
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [@mag3nt/sdk](#mag3ntsdk)
  * [SDK Installation](#sdk-installation)
  * [Requirements](#requirements)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Standalone functions](#standalone-functions)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
  * [Debugging](#debugging)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed with either [npm](https://www.npmjs.com/), [pnpm](https://pnpm.io/), [bun](https://bun.sh/) or [yarn](https://classic.yarnpkg.com/en/) package managers.

### NPM

```bash
npm add @mag3nt/sdk
```

### PNPM

```bash
pnpm add @mag3nt/sdk
```

### Bun

```bash
bun add @mag3nt/sdk
```

### Yarn

```bash
yarn add @mag3nt/sdk
```

> [!NOTE]
> This package is published as an ES Module (ESM) only. For applications using
> CommonJS, use `await import("@mag3nt/sdk")` to import and use this package.
<!-- End SDK Installation [installation] -->

<!-- Start Requirements [requirements] -->
## Requirements

For supported JavaScript runtimes, please consult [RUNTIMES.md](RUNTIMES.md).
<!-- End Requirements [requirements] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.cards.cardsList();

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name         | Type   | Scheme  |
| ------------ | ------ | ------- |
| `apiKeyAuth` | apiKey | API key |

To authenticate with the API the `apiKeyAuth` parameter must be set when initializing the SDK client instance. For example:
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.cards.cardsList();

  console.log(result);
}

run();

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [Ap2](docs/sdks/ap2/README.md)

* [ap2GetAgentCard](docs/sdks/ap2/README.md#ap2getagentcard) - Get the default agent card for AP2 payments
* [ap2ListPaymentMethods](docs/sdks/ap2/README.md#ap2listpaymentmethods) - List available payment methods for AP2
* [ap2CreateMandate](docs/sdks/ap2/README.md#ap2createmandate) - Create a spending mandate for recurring AP2 payments
* [ap2Execute](docs/sdks/ap2/README.md#ap2execute) - Execute a payment against an AP2 mandate
* [ap2ListMandates](docs/sdks/ap2/README.md#ap2listmandates) - List mandates for a card

### [Cards](docs/sdks/cards/README.md)

* [cardsList](docs/sdks/cards/README.md#cardslist) - List all cards for the authenticated wallet
* [cardsCreate](docs/sdks/cards/README.md#cardscreate) - Issue a new virtual payment card
* [cardsBulkCreate](docs/sdks/cards/README.md#cardsbulkcreate) - Issue multiple cards in a single atomic request
* [cardsFreeze](docs/sdks/cards/README.md#cardsfreeze) - Freeze a card to block all transactions
* [cardsUnfreeze](docs/sdks/cards/README.md#cardsunfreeze) - Unfreeze a previously frozen card
* [cardsClaim](docs/sdks/cards/README.md#cardsclaim) - Claim a card using its token
* [cardsUpdateControls](docs/sdks/cards/README.md#cardsupdatecontrols) - Update card spending controls
* [cardsListTransactions](docs/sdks/cards/README.md#cardslisttransactions) - List transactions for a card

### [Funding](docs/sdks/funding/README.md)

* [fundingListTokens](docs/sdks/funding/README.md#fundinglisttokens) - List accepted tokens per network
* [fundingGetBalance](docs/sdks/funding/README.md#fundinggetbalance) - Get treasury balance for authenticated wallet

### [Keys](docs/sdks/keys/README.md)

* [keysCreate](docs/sdks/keys/README.md#keyscreate) - Generate a new API key
* [keysList](docs/sdks/keys/README.md#keyslist) - List all API keys for the authenticated wallet
* [keysRevoke](docs/sdks/keys/README.md#keysrevoke) - Revoke an API key
* [keysValidate](docs/sdks/keys/README.md#keysvalidate) - Validate an API key

### [Mpp](docs/sdks/mpp/README.md)

* [mppPay](docs/sdks/mpp/README.md#mpppay) - Make a micropayment via MPP protocol
* [mppCreateSession](docs/sdks/mpp/README.md#mppcreatesession) - Create an MPP payment session
* [mppDiscover](docs/sdks/mpp/README.md#mppdiscover) - Discover MPP capabilities for a URL
* [mppReceive](docs/sdks/mpp/README.md#mppreceive) - Verify and accept an MPP payment
* [mppStreamsOpen](docs/sdks/mpp/README.md#mppstreamsopen) - Open a payment stream for continuous micropayments
* [mppStreamsTick](docs/sdks/mpp/README.md#mppstreamstick) - Advance a payment stream by one tick
* [mppStreamsClose](docs/sdks/mpp/README.md#mppstreamsclose) - Close a payment stream
* [mppStreamsGet](docs/sdks/mpp/README.md#mppstreamsget) - Get payment stream details

### [PayLinks](docs/sdks/paylinks/README.md)

* [payLinksCreate](docs/sdks/paylinks/README.md#paylinkscreate) - Create a shareable payment link
* [payLinksList](docs/sdks/paylinks/README.md#paylinkslist) - List pay links for authenticated wallet
* [payLinksGet](docs/sdks/paylinks/README.md#paylinksget) - Get public pay link details
* [payLinksCancel](docs/sdks/paylinks/README.md#paylinkscancel) - Cancel a pay link
* [payLinksGetStatus](docs/sdks/paylinks/README.md#paylinksgetstatus) - Check pay link payment status
* [payLinksResolve](docs/sdks/paylinks/README.md#paylinksresolve) - Resolve a pay link for payment processing
* [payLinksPrepare](docs/sdks/paylinks/README.md#paylinksprepare) - Prepare payment intent for a pay link
* [payLinksSettle](docs/sdks/paylinks/README.md#paylinkssettle) - Settle a pay link payment

### [Settlement](docs/sdks/settlement/README.md)

* [settlementGetStatus](docs/sdks/settlement/README.md#settlementgetstatus) - Check settlement status for a transaction

### [Status](docs/sdks/status/README.md)

* [statusGet](docs/sdks/status/README.md#statusget) - Get platform status, supported protocols, and capabilities
* [statusGetConfig](docs/sdks/status/README.md#statusgetconfig) - Get treasury addresses and token registry

### [X402](docs/sdks/x402/README.md)

* [x402Pay](docs/sdks/x402/README.md#x402pay) - Pay for a service via x402 protocol
* [x402Discover](docs/sdks/x402/README.md#x402discover) - Discover x402 payment requirements for a URL
* [x402Receive](docs/sdks/x402/README.md#x402receive) - Verify and accept an x402 payment

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Standalone functions [standalone-funcs] -->
## Standalone functions

All the methods listed above are available as standalone functions. These
functions are ideal for use in applications running in the browser, serverless
runtimes or other environments where application bundle size is a primary
concern. When using a bundler to build your application, all unused
functionality will be either excluded from the final bundle or tree-shaken away.

To read more about standalone functions, check [FUNCTIONS.md](./FUNCTIONS.md).

<details>

<summary>Available standalone functions</summary>

- [`ap2Ap2CreateMandate`](docs/sdks/ap2/README.md#ap2createmandate) - Create a spending mandate for recurring AP2 payments
- [`ap2Ap2Execute`](docs/sdks/ap2/README.md#ap2execute) - Execute a payment against an AP2 mandate
- [`ap2Ap2GetAgentCard`](docs/sdks/ap2/README.md#ap2getagentcard) - Get the default agent card for AP2 payments
- [`ap2Ap2ListMandates`](docs/sdks/ap2/README.md#ap2listmandates) - List mandates for a card
- [`ap2Ap2ListPaymentMethods`](docs/sdks/ap2/README.md#ap2listpaymentmethods) - List available payment methods for AP2
- [`cardsCardsBulkCreate`](docs/sdks/cards/README.md#cardsbulkcreate) - Issue multiple cards in a single atomic request
- [`cardsCardsClaim`](docs/sdks/cards/README.md#cardsclaim) - Claim a card using its token
- [`cardsCardsCreate`](docs/sdks/cards/README.md#cardscreate) - Issue a new virtual payment card
- [`cardsCardsFreeze`](docs/sdks/cards/README.md#cardsfreeze) - Freeze a card to block all transactions
- [`cardsCardsList`](docs/sdks/cards/README.md#cardslist) - List all cards for the authenticated wallet
- [`cardsCardsListTransactions`](docs/sdks/cards/README.md#cardslisttransactions) - List transactions for a card
- [`cardsCardsUnfreeze`](docs/sdks/cards/README.md#cardsunfreeze) - Unfreeze a previously frozen card
- [`cardsCardsUpdateControls`](docs/sdks/cards/README.md#cardsupdatecontrols) - Update card spending controls
- [`fundingFundingGetBalance`](docs/sdks/funding/README.md#fundinggetbalance) - Get treasury balance for authenticated wallet
- [`fundingFundingListTokens`](docs/sdks/funding/README.md#fundinglisttokens) - List accepted tokens per network
- [`keysKeysCreate`](docs/sdks/keys/README.md#keyscreate) - Generate a new API key
- [`keysKeysList`](docs/sdks/keys/README.md#keyslist) - List all API keys for the authenticated wallet
- [`keysKeysRevoke`](docs/sdks/keys/README.md#keysrevoke) - Revoke an API key
- [`keysKeysValidate`](docs/sdks/keys/README.md#keysvalidate) - Validate an API key
- [`mppMPPCreateSession`](docs/sdks/mpp/README.md#mppcreatesession) - Create an MPP payment session
- [`mppMPPDiscover`](docs/sdks/mpp/README.md#mppdiscover) - Discover MPP capabilities for a URL
- [`mppMPPPay`](docs/sdks/mpp/README.md#mpppay) - Make a micropayment via MPP protocol
- [`mppMPPReceive`](docs/sdks/mpp/README.md#mppreceive) - Verify and accept an MPP payment
- [`mppMPPStreamsClose`](docs/sdks/mpp/README.md#mppstreamsclose) - Close a payment stream
- [`mppMPPStreamsGet`](docs/sdks/mpp/README.md#mppstreamsget) - Get payment stream details
- [`mppMPPStreamsOpen`](docs/sdks/mpp/README.md#mppstreamsopen) - Open a payment stream for continuous micropayments
- [`mppMPPStreamsTick`](docs/sdks/mpp/README.md#mppstreamstick) - Advance a payment stream by one tick
- [`payLinksPayLinksCancel`](docs/sdks/paylinks/README.md#paylinkscancel) - Cancel a pay link
- [`payLinksPayLinksCreate`](docs/sdks/paylinks/README.md#paylinkscreate) - Create a shareable payment link
- [`payLinksPayLinksGet`](docs/sdks/paylinks/README.md#paylinksget) - Get public pay link details
- [`payLinksPayLinksGetStatus`](docs/sdks/paylinks/README.md#paylinksgetstatus) - Check pay link payment status
- [`payLinksPayLinksList`](docs/sdks/paylinks/README.md#paylinkslist) - List pay links for authenticated wallet
- [`payLinksPayLinksPrepare`](docs/sdks/paylinks/README.md#paylinksprepare) - Prepare payment intent for a pay link
- [`payLinksPayLinksResolve`](docs/sdks/paylinks/README.md#paylinksresolve) - Resolve a pay link for payment processing
- [`payLinksPayLinksSettle`](docs/sdks/paylinks/README.md#paylinkssettle) - Settle a pay link payment
- [`settlementSettlementGetStatus`](docs/sdks/settlement/README.md#settlementgetstatus) - Check settlement status for a transaction
- [`statusStatusGet`](docs/sdks/status/README.md#statusget) - Get platform status, supported protocols, and capabilities
- [`statusStatusGetConfig`](docs/sdks/status/README.md#statusgetconfig) - Get treasury addresses and token registry
- [`x402X402Discover`](docs/sdks/x402/README.md#x402discover) - Discover x402 payment requirements for a URL
- [`x402X402Pay`](docs/sdks/x402/README.md#x402pay) - Pay for a service via x402 protocol
- [`x402X402Receive`](docs/sdks/x402/README.md#x402receive) - Verify and accept an x402 payment

</details>
<!-- End Standalone functions [standalone-funcs] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries.  If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API.  However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a retryConfig object to the call:
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.cards.cardsList({
    retries: {
      strategy: "backoff",
      backoff: {
        initialInterval: 1,
        maxInterval: 50,
        exponent: 1.1,
        maxElapsedTime: 100,
      },
      retryConnectionErrors: false,
    },
  });

  console.log(result);
}

run();

```

If you'd like to override the default retry strategy for all operations that support retries, you can provide a retryConfig at SDK initialization:
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  retryConfig: {
    strategy: "backoff",
    backoff: {
      initialInterval: 1,
      maxInterval: 50,
      exponent: 1.1,
      maxElapsedTime: 100,
    },
    retryConnectionErrors: false,
  },
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.cards.cardsList();

  console.log(result);
}

run();

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

[`Mag3ntError`](./src/models/errors/mag3nt-error.ts) is the base class for all HTTP error responses. It has the following properties:

| Property            | Type       | Description                                                                             |
| ------------------- | ---------- | --------------------------------------------------------------------------------------- |
| `error.message`     | `string`   | Error message                                                                           |
| `error.statusCode`  | `number`   | HTTP response status code eg `404`                                                      |
| `error.headers`     | `Headers`  | HTTP response headers                                                                   |
| `error.body`        | `string`   | HTTP body. Can be empty string if no body is returned.                                  |
| `error.rawResponse` | `Response` | Raw HTTP response                                                                       |
| `error.data$`       |            | Optional. Some errors may contain structured data. [See Error Classes](#error-classes). |

### Example
```typescript
import { Mag3nt } from "@mag3nt/sdk";
import * as errors from "@mag3nt/sdk/models/errors";

const mag3nt = new Mag3nt({
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  try {
    const result = await mag3nt.cards.cardsList();

    console.log(result);
  } catch (error) {
    // The base class for HTTP error responses
    if (error instanceof errors.Mag3ntError) {
      console.log(error.message);
      console.log(error.statusCode);
      console.log(error.body);
      console.log(error.headers);

      // Depending on the method different errors may be thrown
      if (error instanceof errors.ErrorT) {
        console.log(error.data$.error); // string
      }
    }
  }
}

run();

```

### Error Classes
**Primary error:**
* [`Mag3ntError`](./src/models/errors/mag3nt-error.ts): The base class for HTTP error responses.

<details><summary>Less common errors (9)</summary>

<br />

**Network errors:**
* [`ConnectionError`](./src/models/errors/http-client-errors.ts): HTTP client was unable to make a request to a server.
* [`RequestTimeoutError`](./src/models/errors/http-client-errors.ts): HTTP request timed out due to an AbortSignal signal.
* [`RequestAbortedError`](./src/models/errors/http-client-errors.ts): HTTP request was aborted by the client.
* [`InvalidRequestError`](./src/models/errors/http-client-errors.ts): Any input used to create a request is invalid.
* [`UnexpectedClientError`](./src/models/errors/http-client-errors.ts): Unrecognised or unexpected error.


**Inherit from [`Mag3ntError`](./src/models/errors/mag3nt-error.ts)**:
* [`ErrorT`](./src/models/errors/error-t.ts): Applicable to 4 of 41 methods.*
* [`BalanceError`](./src/models/errors/balance-error.ts): Insufficient balance. Status code `403`. Applicable to 2 of 41 methods.*
* [`GoneError`](./src/models/errors/gone-error.ts): Pay link has been used. Status code `410`. Applicable to 1 of 41 methods.*
* [`ResponseValidationError`](./src/models/errors/response-validation-error.ts): Type mismatch between the data returned from the server and the structure expected by the SDK. See `error.rawValue` for the raw value and `error.pretty()` for a nicely formatted multi-line string.

</details>

\* Check [the method documentation](#available-resources-and-operations) to see if the error is applicable.
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally by passing a URL to the `serverURL: string` optional parameter when initializing the SDK client instance. For example:
```typescript
import { Mag3nt } from "@mag3nt/sdk";

const mag3nt = new Mag3nt({
  serverURL: "https://mag3nt.com",
  apiKeyAuth: "<YOUR_API_KEY_HERE>",
});

async function run() {
  const result = await mag3nt.cards.cardsList();

  console.log(result);
}

run();

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The TypeScript SDK makes API calls using an `HTTPClient` that wraps the native
[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API). This
client is a thin wrapper around `fetch` and provides the ability to attach hooks
around the request lifecycle that can be used to modify the request or handle
errors and response.

The `HTTPClient` constructor takes an optional `fetcher` argument that can be
used to integrate a third-party HTTP client or when writing tests to mock out
the HTTP client and feed in fixtures.

The following example shows how to:
- route requests through a proxy server using [undici](https://www.npmjs.com/package/undici)'s ProxyAgent
- use the `"beforeRequest"` hook to add a custom header and a timeout to requests
- use the `"requestError"` hook to log errors

```typescript
import { Mag3nt } from "@mag3nt/sdk";
import { ProxyAgent } from "undici";
import { HTTPClient } from "@mag3nt/sdk/lib/http";

const dispatcher = new ProxyAgent("http://proxy.example.com:8080");

const httpClient = new HTTPClient({
  // 'fetcher' takes a function that has the same signature as native 'fetch'.
  fetcher: (input, init) =>
    // 'dispatcher' is specific to undici and not part of the standard Fetch API.
    fetch(input, { ...init, dispatcher } as RequestInit),
});

httpClient.addHook("beforeRequest", (request) => {
  const nextRequest = new Request(request, {
    signal: request.signal || AbortSignal.timeout(5000)
  });

  nextRequest.headers.set("x-custom-header", "custom value");

  return nextRequest;
});

httpClient.addHook("requestError", (error, request) => {
  console.group("Request Error");
  console.log("Reason:", `${error}`);
  console.log("Endpoint:", `${request.method} ${request.url}`);
  console.groupEnd();
});

const sdk = new Mag3nt({ httpClient: httpClient });
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass a logger that matches `console`'s interface as an SDK option.

> [!WARNING]
> Beware that debug logging will reveal secrets, like API tokens in headers, in log messages printed to a console or files. It's recommended to use this feature only during local development and not in production.

```typescript
import { Mag3nt } from "@mag3nt/sdk";

const sdk = new Mag3nt({ debugLogger: console });
```
<!-- End Debugging [debug] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=@mag3nt/sdk&utm_campaign=typescript)
