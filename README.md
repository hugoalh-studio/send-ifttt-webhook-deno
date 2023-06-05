# Send IFTTT Webhook (Deno)

![License](https://img.shields.io/static/v1?label=License&message=MIT&style=flat-square "License")
[![GitHub Repository](https://img.shields.io/badge/Repository-181717?logo=github&logoColor=ffffff&style=flat-square "GitHub Repository")](https://github.com/hugoalh-studio/send-ifttt-webhook-deno)
[![GitHub Stars](https://img.shields.io/github/stars/hugoalh-studio/send-ifttt-webhook-deno?label=Stars&logo=github&logoColor=ffffff&style=flat-square "GitHub Stars")](https://github.com/hugoalh-studio/send-ifttt-webhook-deno/stargazers)
[![GitHub Contributors](https://img.shields.io/github/contributors/hugoalh-studio/send-ifttt-webhook-deno?label=Contributors&logo=github&logoColor=ffffff&style=flat-square "GitHub Contributors")](https://github.com/hugoalh-studio/send-ifttt-webhook-deno/graphs/contributors)
[![GitHub Issues](https://img.shields.io/github/issues-raw/hugoalh-studio/send-ifttt-webhook-deno?label=Issues&logo=github&logoColor=ffffff&style=flat-square "GitHub Issues")](https://github.com/hugoalh-studio/send-ifttt-webhook-deno/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr-raw/hugoalh-studio/send-ifttt-webhook-deno?label=Pull%20Requests&logo=github&logoColor=ffffff&style=flat-square "GitHub Pull Requests")](https://github.com/hugoalh-studio/send-ifttt-webhook-deno/pulls)
[![GitHub Discussions](https://img.shields.io/github/discussions/hugoalh-studio/send-ifttt-webhook-deno?label=Discussions&logo=github&logoColor=ffffff&style=flat-square "GitHub Discussions")](https://github.com/hugoalh-studio/send-ifttt-webhook-deno/discussions)
[![CodeFactor Grade](https://img.shields.io/codefactor/grade/github/hugoalh-studio/send-ifttt-webhook-deno?label=Grade&logo=codefactor&logoColor=ffffff&style=flat-square "CodeFactor Grade")](https://www.codefactor.io/repository/github/hugoalh-studio/send-ifttt-webhook-deno)

| **Releases** | **Latest** (![GitHub Latest Release Date](https://img.shields.io/github/release-date/hugoalh-studio/send-ifttt-webhook-deno?label=&style=flat-square "GitHub Latest Release Date")) | **Pre** (![GitHub Latest Pre-Release Date](https://img.shields.io/github/release-date-pre/hugoalh-studio/send-ifttt-webhook-deno?label=&style=flat-square "GitHub Latest Pre-Release Date")) |
|:-:|:-:|:-:|
| [![Deno Land](https://img.shields.io/badge/Deno%20Land-000000?logo=deno&logoColor=ffffff&style=flat-square "Deno Land")](https://deno.land/x/send_ifttt_webhook) |  |  |
| [![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=ffffff&style=flat-square "GitHub")](https://github.com/hugoalh-studio/send-ifttt-webhook-deno/releases) ![GitHub Total Downloads](https://img.shields.io/github/downloads/hugoalh-studio/send-ifttt-webhook-deno/total?label=&style=flat-square "GitHub Total Downloads") | ![GitHub Latest Release Version](https://img.shields.io/github/release/hugoalh-studio/send-ifttt-webhook-deno?sort=semver&label=&style=flat-square "GitHub Latest Release Version") | ![GitHub Latest Pre-Release Version](https://img.shields.io/github/release/hugoalh-studio/send-ifttt-webhook-deno?include_prereleases&sort=semver&label=&style=flat-square "GitHub Latest Pre-Release Version") |

## 📝 Description

A Deno module to send IFTTT webhook.

> **🔗 Other Edition:**
>
> - [NodeJS](https://github.com/hugoalh-studio/send-ifttt-webhook-nodejs)

## 📚 Documentation

### Getting Started

- Deno >= v1.34.0

```ts
/* Either */
import { ... } from "https://deno.land/x/send_ifttt_webhook/mod.ts";// Named Import
import * as iftttWebhook from "https://deno.land/x/send_ifttt_webhook/mod.ts";// Namespace Import
import IFTTTWebhook from "https://deno.land/x/send_ifttt_webhook/mod.ts";// Default Import (Class `IFTTTWebhook`)
```

### API

#### Class

- ```ts
  new IFTTTWebhook(key: string, options: IFTTTWebhookConstructorOptions = {}): IFTTTWebhook;
    .send(options: IFTTTWebhookSendOptions = {}): Promise<Response>;
    .sendArbitrary(options: Omit<IFTTTWebhookSendOptions, "arbitrary"> = {}): Promise<Response>;

  IFTTTWebhook.send(key: string, eventName: string, options: Omit<IFTTTWebhookSendOptions, "eventName"> = {}): Promise<Response>;
  IFTTTWebhook.sendArbitrary(key: string, eventName: string, options: Omit<IFTTTWebhookSendOptions, "arbitrary" | "eventName"> = {}): Promise<Response>;
  ```

#### Function

- ```ts
  send(key: string, eventName: string, options: Omit<IFTTTWebhookSendOptions, "eventName"> = {}): Promise<Response>;
  ```
- ```ts
  sendArbitrary(key: string, eventName: string, options: Omit<IFTTTWebhookSendOptions, "arbitrary" | "eventName"> = {}): Promise<Response>;
  ```

#### Interface / Type

- ```ts
  interface IFTTTWebhookConstructorOptions {
    /* Define a default value of whether to trigger with an arbitrary payload. */
    arbitraryDefault: boolean = false;
    /* Define a default value of the event name. */
    eventNameDefault?: string;
  }
  ```
- ```ts
  interface IFTTTWebhookSendOptions {
    /* Whether to trigger with an arbitrary payload. */
    arbitrary: boolean = arbitraryDefault;
    /* Event name. */
    eventName: string = eventNameDefault;
    /* Payload. */
    payload: object = {};
  }
  ```

### Example

```js
new IFTTTWebhook("my-ifttt-webhook-key", { eventNameDefault: "test" }).sendArbitrary({ payload: { message: "Hello, world!" } })
```
