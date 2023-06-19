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
| [![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=ffffff&style=flat-square "GitHub")](https://github.com/hugoalh-studio/send-ifttt-webhook-deno/releases) ![GitHub Total Downloads](https://img.shields.io/github/downloads/hugoalh-studio/send-ifttt-webhook-deno/total?label=&style=flat-square "GitHub Total Downloads") | ![GitHub Latest Release Version](https://img.shields.io/github/release/hugoalh-studio/send-ifttt-webhook-deno?sort=semver&label=&style=flat-square "GitHub Latest Release Version") | ![GitHub Latest Pre-Release Version](https://img.shields.io/github/release/hugoalh-studio/send-ifttt-webhook-deno?include_prereleases&sort=semver&label=&style=flat-square "GitHub Latest Pre-Release Version") |

## 📝 Description

A Deno module to send IFTTT webhook.

> **🔗 Other Edition:**
>
> - [GitHub Action](https://github.com/hugoalh/send-ifttt-webhook-ghaction)
> - [NodeJS](https://github.com/hugoalh-studio/send-ifttt-webhook-nodejs)

## 📚 Documentation

### Getting Started

- Deno >= v1.34.0

```ts
/* Either */
import { ... } from "<URL>";// Named Import
import * as sendIFTTTWebhook from "<URL>";// Namespace Import
import IFTTTWebhook from "<URL>";// Default Import (Class `IFTTTWebhook`)
```

| **Domain / Registry** | **URL** |
|:-:|:--|
| [Deno Land](https://deno.land/x/send_ifttt_webhook) | `https://deno.land/x/send_ifttt_webhook[@<Tag>]/mod.ts` |
| DenoPKG | `https://denopkg.com/hugoalh-studio/send-ifttt-webhook-deno[@<Tag>]/mod.ts` |
| GitHub Raw **\*** | `https://raw.githubusercontent.com/hugoalh-studio/send-ifttt-webhook-deno/<Tag>/mod.ts` |
| Pax | `https://pax.deno.dev/hugoalh-studio/send-ifttt-webhook-deno[@<Tag>]/mod.ts` |

**\*:** Must provide a tag.

### API

#### Class

- ```ts
  new IFTTTWebhook(key: string): IFTTTWebhook;
    .send(eventName: string, payload: IFTTTWebhookStandardPayload = {}): Promise<Response>;
    .sendArbitrary(eventName: string, payload: object = {}): Promise<Response>;

  IFTTTWebhook.send(key: string, eventName: string, payload: IFTTTWebhookStandardPayload = {}): Promise<Response>;
  IFTTTWebhook.sendArbitrary(key: string, eventName: string, payload: object = {}): Promise<Response>;
  ```

#### Function

- ```ts
  sendIFTTTWebhook(key: string, eventName: string, payload: IFTTTWebhookStandardPayload = {}): Promise<Response>;
  ```
- ```ts
  sendIFTTTWebhookArbitrary(key: string, eventName: string, payload: object = {}): Promise<Response>;
  ```

#### Interface / Type

- ```ts
  interface IFTTTWebhookStandardPayload {
    value1?: string;
    value2?: string;
    value3?: string;
  }
  ```

### Example

```js
new IFTTTWebhook("my-ifttt-webhook-key").sendArbitrary("test", { message: "Hello, world!" });
```
