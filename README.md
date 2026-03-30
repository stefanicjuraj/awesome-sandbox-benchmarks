# Sandbox Benchmarks

A curated collection of sandbox providers, benchmarks, tools, and resources.

- [Sandbox Providers](#sandbox-providers)
- [Sandbox Benchmarks](#sandbox-benchmarks)
  - [Sandbox Creation Benchmark](#sandbox-creation-benchmark)
    - [Sequential Benchmark](#sequential-benchmark)
    - [Burst Benchmark](#burst-benchmark)
    - [Staggered Benchmark](#staggered-benchmark)
  - [NPM Registry Downloads](#npm-registry-downloads)
  - [Agent Evaluation](#agent-evaluation)
  - [Pricing](#pricing)
    - [CPU](#cpu)
    - [Memory](#memory)
    - [Storage](#storage)
  - [Isolation](#isolation)
  - [Security](#security)

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

### Sandbox Creation Benchmark

#### Sequential Benchmark

Sandboxes are created one at a time with no concurrency. Each sandbox is provisioned before the next starts.

| Provider    | Median TTI | P95 TTI | P99 TTI | Success Rate |
| :---------- | :--------- | :------ | :------ | :----------- |
| Daytona     | 113 ms     | 198 ms  | 296 ms  | 100%         |
| E2B         | 373 ms     | 567 ms  | 728 ms  | 100%         |
| Bunnyshell  | 1061 ms    | 1324 ms | 1346 ms | 100%         |
| Blaxel      | 1114 ms    | 1180 ms | 1203 ms | 100%         |
| Cloudflare  | 1584 ms    | 2084 ms | 2439 ms | 100%         |
| Vercel      | 1710 ms    | 1828 ms | 1890 ms | 100%         |
| Namespace   | 1752 ms    | 1925 ms | 2013 ms | 100%         |
| Runloop     | 1887 ms    | 1979 ms | 1993 ms | 100%         |
| Modal       | 2096 ms    | 2743 ms | 3182 ms | 98%          |
| CodeSandbox | 2356 ms    | 2576 ms | 2710 ms | 100%         |

> Source: _[computesdk.com/benchmarks](https://www.computesdk.com/benchmarks/)_

#### Burst Benchmark

Sandboxes are created concurrently.

| Provider    | Median TTI | P95 TTI  | P99 TTI  | Success Rate |
| :---------- | :--------- | :------- | :------- | :----------- |
| Daytona     | 279 ms     | 424 ms   | 455 ms   | 100%         |
| E2B         | 594 ms     | 998 ms   | 1124 ms  | 100%         |
| Blaxel      | 1620 ms    | 2511 ms  | 2563 ms  | 43%          |
| Cloudflare  | 1852 ms    | 2501 ms  | 2735 ms  | 100%         |
| Vercel      | 1947 ms    | 2142 ms  | 2177 ms  | 100%         |
| Namespace   | 2028 ms    | 2237 ms  | 2311 ms  | 100%         |
| Modal       | 2342 ms    | 3122 ms  | 3269 ms  | 100%         |
| Runloop     | 2375 ms    | 2924 ms  | 3041 ms  | 100%         |
| CodeSandbox | 6658 ms    | 9213 ms  | 9389 ms  | 100%         |
| Bunnyshell  | 16938 ms   | 17456 ms | 17574 ms | 91%          |

> Source: _[computesdk.com/benchmarks](https://www.computesdk.com/benchmarks/)_

#### Staggered Benchmark

Sandboxes are created with a 200 ms delay between each provision.

| Provider    | Median TTI | P95 TTI | P99 TTI | Success Rate |
| :---------- | :--------- | :------ | :------ | :----------- |
| Daytona     | 117 ms     | 290 ms  | 302 ms  | 100%         |
| E2B         | 364 ms     | 574 ms  | 662 ms  | 100%         |
| Blaxel      | 1221 ms    | 1333 ms | 1355 ms | 100%         |
| Bunnyshell  | 1221 ms    | 2297 ms | 2485 ms | 99%          |
| Vercel      | 1656 ms    | 1810 ms | 1836 ms | 100%         |
| Namespace   | 1742 ms    | 1871 ms | 1922 ms | 100%         |
| Cloudflare  | 1750 ms    | 2275 ms | 2524 ms | 100%         |
| Runloop     | 1895 ms    | 1990 ms | 1999 ms | 100%         |
| Modal       | 2102 ms    | 2828 ms | 3075 ms | 100%         |
| CodeSandbox | 2552 ms    | 2841 ms | 2904 ms | 100%         |

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

> Source: _[npmjs.com](https://www.npmjs.com/)_ • _[npmtrends.com](https://npmtrends.com/@blaxel/core-vs-@cloudflare/sandbox-vs-@codesandbox/sdk-vs-@daytonaio/sdk-vs-@hopx-ai/sdk-vs-@runloop/api-client-vs-@vercel/sandbox-vs-e2b-vs-modal)_

### Agent Evaluation

Evaluation of how easily AI agents can get started with sandboxes — fully autonomously.

| Provider    | Time   | Tool Calls | Friction | Errors | Cost  | Docs  | Grade |
| :---------- | :----- | :--------- | :------- | :----- | :---- | :---- | :---- |
| E2B         | 43s    | 13         | 1        | 0      | $0.47 | 4/5   | 88 B  |
| Vercel      | 1m 37s | 19         | 1        | 0      | $1.23 | 4/5   | 81 B  |
| Daytona     | 2m 8s  | 19         | 1        | 1      | $0.52 | 4/5   | 75 B  |
| Freestyle   | 2m 33s | 22         | 1        | 0      | $0.96 | 4.5/5 | 75 B  |
| Cloudflare  | 5m 5s  | 29         | 0        | 1      | $1.66 | 3.5/5 | 69 C  |
| Blaxel      | 3m 46s | 34         | 1        | 1      | $1.01 | 5/5   | 66 C  |
| Modal       | 2m 50s | 31         | 1        | 2      | $0.63 | 4/5   | 66 C  |
| CodeSandbox | 3m 25s | 32         | 2        | 1      | $2.11 | 4/5   | 62 C  |

> Source: _[2027.dev/arena/sandboxes](https://2027.dev/arena/sandboxes)_

### Pricing

The pricing model, estimated hourly cost, and available plans for each sandbox provider.

| Provider    | Pricing model                   | 1 vCPU + 2 GB / hr | Plans                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| :---------- | :------------------------------ | :----------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Blaxel      | Per second (vCPU + memory)      | $0.0828            | **Pay As You Go**<br>No monthly fee · 200 credits · No CC<br>**Enterprise**<br>CC required                                                                                                                                                                                                                                                                                                                                                     |
| Bunnyshell  | Per second (vCPU + memory)      | $0.0828            | **Pay As You Go**<br>No monthly fee · 200 credits · No CC                                                                                                                                                                                                                                                                                                                                                                                      |
| Cloudflare  | Active CPU (10 ms) + memory     | $0.09              | **Workers Free**<br>No monthly fee · No sandboxes on plan · Sandboxes require Workers Paid.<br>**Workers Paid**<br>$5/mo · Included memory (GB-hr): 25 · Included disk (GB-hr): 200 · Included vCPU-min: 375 · Sandboxes on plan                                                                                                                                                                                                               |
| CodeSandbox | VM credits per hour             | $0.0743            | **Build**<br>No monthly fee · Max concurrent VMs: 10 · Max members: 5 · VM credits (hr/mo): 40 · Max VM spec: 4 vCPU + 8 GB · Max SDK sandboxes/hr: 20<br>**Scale**<br>$170/mo · Max concurrent VMs: 250 · Max members: 20 · VM credits (hr/mo): 160 · On-demand ($/hr): 0.1486 · Max VM spec: 16 vCPU + 32 GB · Max SDK sandboxes/hr: 1000<br>**Enterprise**<br>Max VM spec: 64 vCPU + 128 GB · Up to 50% off bulk VM credits. SOC 2 Type II. |
| Daytona     | Per second (vCPU + memory)      | $0.0828            | **Pay As You Go**<br>No monthly fee · 200 credits · No CC · Startup credits ($): 50000                                                                                                                                                                                                                                                                                                                                                         |
| E2B         | Per second (vCPU + memory)      | $0.0828            | **Hobby**<br>No monthly fee · 100 credits · No CC · One-time credit · Max session (hr): 1 · Max concurrent sandboxes: 20<br>**Pro**<br>$150/mo · No credits · CC required · Max session (hr): 24 · Max concurrent sandboxes: 100<br>**Enterprise**<br>CC required                                                                                                                                                                              |
| Modal       | Per second (vCPU + memory)      | $0.1191            | **Starter**<br>No monthly fee · 30 credits · No CC · Max containers: 100 · Max GPU concurrency: 10<br>**Team**<br>$250/mo · 100 credits · CC required · Max containers: 1000 · Max GPU concurrency: 50<br>**Enterprise**<br>CC required                                                                                                                                                                                                        |
| Namespace   | Per minute (bundled unit)       | $0.06              | **Developer**<br>No monthly fee · Billing: pay as you go<br>**Team**<br>$100/mo · Unit-minutes included: 100000 · Docker builds included: 1000<br>**Business**<br>$250/mo · Unit-minutes included: 250000 · Docker builds included: 2500<br>**Enterprise**                                                                                                                                                                                     |
| Runloop     | Per second (vCPU + memory)      | $0.1584            | **Basic**<br>No monthly fee · 25 credits · Storage included (GB): 100<br>**Pro**<br>$250/mo · Storage included (GB): 1000<br>**Enterprise**                                                                                                                                                                                                                                                                                                    |
| Vercel      | Active CPU + provisioned memory | $0.1492            | **Hobby**<br>No monthly fee · No CC · Max session (hr): 0.75 · Max concurrent sandboxes: 10 · Included CPU (hr): 5 · Included memory (GB-hr): 420 · Included network (GB): 20 · Included creations: 5000<br>**Pro**<br>$20/mo · 20 credits · CC required · Max session (hr): 5 · Max concurrent sandboxes: 2000<br>**Enterprise**<br>CC required · Max session (hr): 5 · Max concurrent sandboxes: 2000                                        |

> Source: _[github.com/computesdk/benchmarks](https://github.com/computesdk/benchmarks)_

#### CPU

The CPU pricing rate and billing unit for each sandbox provider.

| Provider    | CPU rate       | CPU unit      |
| :---------- | :------------- | :------------ |
| Blaxel      | -              | -             |
| Bunnyshell  | 0.000014       | vCPU-sec      |
| Cloudflare  | 0.00002        | vCPU-sec      |
| CodeSandbox | -              | -             |
| Daytona     | 0.000014       | vCPU-sec      |
| E2B         | 0.000014       | vCPU-sec      |
| Modal       | 0.00003942     | core-sec      |
| Namespace   | 0.001 / 0.0015 | unit-min      |
| Runloop     | 0.00003        | CPU-sec       |
| Vercel      | 0.128          | active-CPU-hr |

> Source: _[github.com/computesdk/benchmarks](https://github.com/computesdk/benchmarks)_

#### Memory

The memory pricing rate and billing unit for each sandbox provider.

| Provider    | Memory rate | Memory unit |
| :---------- | :---------- | :---------- |
| Blaxel      | 0.0000115   | GB-sec      |
| Bunnyshell  | 0.0000045   | GiB-sec     |
| Cloudflare  | 0.0000025   | GiB-sec     |
| CodeSandbox | -           | -           |
| Daytona     | 0.0000045   | GiB-sec     |
| E2B         | 0.0000045   | GiB-sec     |
| Modal       | 0.00000672  | GiB-sec     |
| Namespace   | -           | -           |
| Runloop     | 0.000007    | GB-sec      |
| Vercel      | 0.0106      | GB-hr       |

> Source: _[github.com/computesdk/benchmarks](https://github.com/computesdk/benchmarks)_

#### Storage

The storage pricing structure and included capacity for each sandbox provider.

| Provider    | Storage plans                                                                                  |
| :---------- | :--------------------------------------------------------------------------------------------- |
| Blaxel      | Images: 0.045/GB-month<br>Snapshots: 0.2/GB-month<br>Volumes: 0.12/GB-month                    |
| Bunnyshell  | Disk: 0.00000003/GiB-sec                                                                       |
| Cloudflare  | Free: 200 GB-hr/mo<br>Disk: 0.00000007/GB-sec<br>Billing: provisioned<br>Persistent: no        |
| CodeSandbox | Included: 20 GB (per VM)                                                                       |
| Daytona     | Free: 5 GiB<br>Disk: 0.00000003/GiB-sec                                                        |
| E2B         | Included: 10 GB                                                                                |
| Modal       | Overage: 0/GB-month                                                                            |
| Namespace   | Cache snapshot: 0.002/GB-hr<br>Cache volume: 0.0048/GB-day<br>Container registry: 0.2/GB-month |
| Runloop     | Free: 100 GB<br>Active: 0.00034236/GB-hr<br>Snapshots: 0.000072/GB-hr                          |
| Vercel      | Included: 15 GB<br>Overage: 0.08/GB-month                                                      |

> Source: _[github.com/computesdk/benchmarks](https://github.com/computesdk/benchmarks)_

### Isolation

The virtualization technology and infrastructure each provider uses to isolate sandbox environments.

| Provider    | Isolation           |
| :---------- | :------------------ |
| Blaxel      | microvm             |
| Bunnyshell  | firecracker microvm |
| Cloudflare  | container           |
| CodeSandbox | microvm             |
| Daytona     | docker oci          |
| E2B         | firecracker microvm |
| Modal       | gvisor              |
| Namespace   | vm                  |
| Runloop     | microvm             |
| Vercel      | firecracker microvm |

> Source: _[github.com/computesdk/benchmarks](https://github.com/computesdk/benchmarks)_

### Security

The security of the sandbox provider's package and its dependencies.

| Provider    | Package                                                               | Quality | Malware | Licenses | Vulnerabilities |
| :---------- | :-------------------------------------------------------------------- | :------ | :------ | :------- | :-------------- |
| Blaxel      | [@blaxel/core](https://npm.js.com/package/@blaxel/core)               | `PASS`  | `PASS`  | `PASS`   | 0 `PASS`        |
| Bunnyshell  | [@hopx-ai/sdk](https://npm.js.com/package/@hopx-ai/sdk)               | `FAIL`  | `PASS`  | `PASS`   | 3 `FAIL`        |
| Cloudflare  | [@cloudflare/sandbox](https://npm.js.com/package/@cloudflare/sandbox) | `PASS`  | `PASS`  | `PASS`   | 0 `PASS`        |
| CodeSandbox | [@codesandbox/sdk](https://npm.js.com/package/@codesandbox/sdk)       | `FAIL`  | `PASS`  | `PASS`   | 3 `FAIL`        |
| Daytona     | [@daytonaio/sdk](https://npm.js.com/package/@daytonaio/sdk)           | `PASS`  | `PASS`  | `PASS`   | 0 `PASS`        |
| E2B         | [e2b](https://npm.js.com/package/e2b)                                 | `PASS`  | `PASS`  | `PASS`   | 0 `PASS`        |
| Modal       | [modal](https://npm.js.com/package/modal)                             | `PASS`  | `PASS`  | `PASS`   | 0 `PASS`        |
| Runloop     | [@runloop/api-client](https://npm.js.com/package/@runloop/api-client) | `PASS`  | `PASS`  | `PASS`   | 0 `PASS`        |
| Vercel      | [@vercel/sandbox](https://npm.js.com/package/@vercel/sandbox)         | `PASS`  | `PASS`  | `PASS`   | 0 `PASS`        |

> Source: _[secure.software](https://secure.software/)_
