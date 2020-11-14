# `workers-eapi-template`

> EAPI for Edge API, or Extremelly Awesome Programation Interface, you decide

A template for kick starting a TypeScript Cloudflare worker project with all the bells and whistles.

- Inspired by [`worker-typescript-template`](https://github.com/cloudflare/worker-typescript-template) & [Express](https://expressjs.com/)
- Includes:
  - [`tiny-request-router`](https://github.com/berstend/tiny-request-router) for routing your requests
  - And a Middleware setup to help with code reuse accross enpoints
  - Some useful Middlewares to get you started
  - A number of type definitions to help you code with confidence
  - A test setup with Jest & all the polyfills & mock you need

## 🔋 Getting Started

This template is meant to be used with [Wrangler](https://github.com/cloudflare/wrangler). If you are not already familiar with the tool, I recommend that you install the tool and configure it to work with your [Cloudflare account](https://dash.cloudflare.com). Documentation can be found [here](https://developers.cloudflare.com/workers/tooling/wrangler/).

To generate using Wrangler, run this command:

```bash
wrangler generate my-ts-project https://github.com/p-j/worker-ts-api-template
```

### 👩 💻 Developing

[`src/types.js`](./src/types.ts) contains some usefull interfaces to help you code new `Middlewares` and `RequestHandler` with confidence

[`src/index.js`](./src/index.ts) setup the fetchEventHandler with the appropriate router instance and default middlewares

[`src/router.js`](./src/router.ts) define the routes, the middlewares and handlers for your application

[`src/middlwares`](./src/middlwares) contains usefull middlewares to get you started

[`src/handlers`](./src/handlers) contains a demo handler

[`src/helpers`](./src/helpers) contains generic helpers

[`__tests__/handlers.ts`](./__tests__/handlers.ts) contains a functional test for the demo

### 🧪 Testing

This template comes with jest tests which simply test that the request handler will perform as expected.

### ✏️ Formatting

This template uses [`prettier`](https://prettier.io/) to format the project. To invoke, run `yarn format`.

### 👀 Previewing and Publishing

For information on how to preview and publish your worker, please see the [Wrangler docs](https://developers.cloudflare.com/workers/tooling/wrangler/commands/#publish).

## 🤢 Issues

If you run into issues with this specific project, please feel free to file an issue [here](https://github.com/cloudflare/workers-typescript-template/issues). If the problem is with Wrangler, please file an issue [here](https://github.com/cloudflare/wrangler/issues).

## ⚠️ Caveats

The `service-worker-mock` used by the tests is not a perfect representation of the Cloudflare Workers runtime. It is a general approximation. We recommend that you test end to end with `wrangler dev` in addition to a [staging environment](https://developers.cloudflare.com/workers/tooling/wrangler/configuration/environments/) to test things before deploying.