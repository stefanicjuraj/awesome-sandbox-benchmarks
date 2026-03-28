# Sandbox Benchmarks

A curated collection of sandbox providers, benchmarks, tools, and resources.

## Sandbox Providers

Sandbox providers handle the infrastructure, provisioning, and management of sandboxes.

- Blaxel ([Website](https://blaxel.ai/) • [Docs](https://docs.blaxel.ai/) • [GitHub](https://github.com/blaxel-ai))
- Bunnyshell (HopX) ([Website](https://hopx.ai/) • [Docs](https://docs.hopx.ai/) • [GitHub](https://github.com/bunnyshell))
- Cloudflare ([Website](https://sandbox.cloudflare.com/) • [Docs](https://developers.cloudflare.com/sandbox/) • [GitHub](https://github.com/cloudflare/sandbox-sdk))
- CodeSandbox ([Website](https://codesandbox.io/) • [Docs](https://codesandbox.io/docs) • [GitHub](https://github.com/codesandbox/codesandbox-client))
- Daytona ([Website](https://www.daytona.io/) • [Docs](https://www.daytona.io/docs) • [GitHub](https://github.com/daytonaio/daytona))
- E2B ([Website](https://e2b.dev/) • [Docs](https://e2b.dev/docs) • [GitHub](https://github.com/e2b-dev))
- Modal ([Website](https://modal.com/) • [Docs](https://modal.com/docs) • [GitHub](https://github.com/modal-labs))
- Namespace ([Website](https://namespace.so/) • [Docs](https://namespace.so/docs) • [GitHub](https://github.com/namespacelabs))
- Runloop ([Website](https://runloop.ai/) • [Docs](https://docs.runloop.ai/docs) • [GitHub](https://github.com/runloopai))
- Vercel ([Website](https://vercel.com/sandbox) • [Docs](https://vercel.com/docs/vercel-sandbox) • [GitHub](https://github.com/vercel/sandbox))

## Sandbox Benchmarks

Sandbox benchmarks compare providers by measuring how quickly a sandbox is created and provisioned: how quickly the sandbox environment becomes responsive after a sandbox is created.

### Sequential Benchmark

Sandboxes are created one at a time with no concurrency. Each sandbox is provisioned before the next starts.

| Provider    | Median TTI | P95 TTI | P99 TTI | Success Rate |
| :---------- | :--------- | :------ | :------ | :----------- |
| Daytona     | 133 ms     | 310 ms  | 314 ms  | 100%         |
| E2B         | 386 ms     | 590 ms  | 622 ms  | 100%         |
| Bunnyshell  | 1010 ms    | 1149 ms | 1324 ms | 100%         |
| Blaxel      | 1095 ms    | 1188 ms | 1272 ms | 100%         |
| Cloudflare  | 1725 ms    | 2353 ms | 2937 ms | 100%         |
| Vercel      | 1735 ms    | 1913 ms | 2047 ms | 100%         |
| Namespace   | 1867 ms    | 2070 ms | 2518 ms | 100%         |
| Runloop     | 1896 ms    | 2695 ms | 4395 ms | 100%         |
| Modal       | 2423 ms    | 3640 ms | 5780 ms | 100%         |
| CodeSandbox | 2462 ms    | 2654 ms | 2686 ms | 100%         |

> Source: _[computesdk.com/benchmarks](https://www.computesdk.com/benchmarks/)_

### Burst Benchmark

Sandboxes are created concurrently.

| Provider    | Median TTI | P95 TTI  | P99 TTI  | Success Rate |
| :---------- | :--------- | :------- | :------- | :----------- |
| Daytona     | 286 ms     | 425 ms   | 460 ms   | 100%         |
| E2B         | 640 ms     | 834 ms   | 899 ms   | 100%         |
| Blaxel      | 1678 ms    | 1728 ms  | 1801 ms  | 23%          |
| Cloudflare  | 1938 ms    | 2671 ms  | 2955 ms  | 100%         |
| Vercel      | 1974 ms    | 2191 ms  | 2305 ms  | 100%         |
| Runloop     | 2242 ms    | 3388 ms  | 5092 ms  | 100%         |
| Namespace   | 2442 ms    | 2683 ms  | 2762 ms  | 100%         |
| Modal       | 2588 ms    | 8009 ms  | 8462 ms  | 100%         |
| CodeSandbox | 6447 ms    | 9059 ms  | 9569 ms  | 100%         |
| Bunnyshell  | 15038 ms   | 15711 ms | 15786 ms | 98%          |

> Source: _[computesdk.com/benchmarks](https://www.computesdk.com/benchmarks/)_

### Staggered Benchmark

Sandboxes are created with a 200 ms delay between each provision.

| Provider    | Median TTI | P95 TTI | P99 TTI | Success Rate |
| :---------- | :--------- | :------ | :------ | :----------- |
| Daytona     | 129 ms     | 307 ms  | 311 ms  | 100%         |
| E2B         | 354 ms     | 566 ms  | 702 ms  | 100%         |
| Bunnyshell  | 1067 ms    | 2204 ms | 2231 ms | 98%          |
| Blaxel      | 1126 ms    | 1201 ms | 1223 ms | 100%         |
| Vercel      | 1702 ms    | 1912 ms | 1949 ms | 100%         |
| Runloop     | 1892 ms    | 2002 ms | 2677 ms | 100%         |
| Cloudflare  | 1899 ms    | 2701 ms | 2800 ms | 100%         |
| Namespace   | 1954 ms    | 2222 ms | 2341 ms | 100%         |
| Modal       | 2319 ms    | 5017 ms | 7459 ms | 100%         |
| CodeSandbox | 2682 ms    | 3180 ms | 3552 ms | 100%         |

> Source: _[computesdk.com/benchmarks](https://www.computesdk.com/benchmarks/)_

### NPM Registry Downloads

The number of sandbox package downloads from the NPM registry in the last week.

| Provider          | Package                                                                  | Weekly Downloads |
| :---------------- | :----------------------------------------------------------------------- | :--------------- |
| E2B               | [e2b](https://www.npmjs.com/package/e2b)                                 | 413,554          |
| Vercel            | [@vercel/sandbox](https://www.npmjs.com/package/@vercel/sandbox)         | 406,401          |
| Daytona           | [@daytonaio/sdk](https://www.npmjs.com/package/@daytonaio/sdk)           | 142,458          |
| Modal             | [modal](https://www.npmjs.com/package/modal)                             | 94,827           |
| Cloudflare        | [@cloudflare/sandbox](https://www.npmjs.com/package/@cloudflare/sandbox) | 44,931           |
| Blaxel            | [@blaxel/core](https://www.npmjs.com/package/@blaxel/core)               | 32,561           |
| CodeSandbox       | [@codesandbox/sdk](https://www.npmjs.com/package/@codesandbox/sdk)       | 20,297           |
| Runloop           | [@runloop/api-client](https://www.npmjs.com/package/@runloop/api-client) | 10,718           |
| Bunnyshell (HopX) | [@hopx-ai/sdk](https://www.npmjs.com/package/@hopx-ai/sdk)               | 1,131            |
