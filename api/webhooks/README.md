---
description: Webhooks & Events
---

# Webhooks

Webhooks can be setup in the LNPay.co dashboard.

## Events

| **Event Name**          | **Event Display Name** | **Note** |
| ----------------------- | ---------------------- | -------- |
| wallet\_created         | Wallet Create          |          |
| wallet\_send            | Wallet Send            |          |
| wallet\_receive         | Wallet Receive         |          |
| wallet\_transfer_\__in  | Wallet Transfer IN     |          |
| wallet\_transfer_\__out | Wallet Transfer Out    |          |

## [Payloads](wallet-payloads.md)

Every payload will follow the same format. an Event ID is provided to identify the event, along with an object of the type details. The `data` section will always contain an array of relevant objects to the event. The key of each object in the data object will match the object id: `"wal":".."` matches `wal_czDztN5eJ4r5sJ` for now this seems the easiest way to plan for future changes and additions.&#x20;

{% hint style="info" %}
Pay careful attention to `passThru` value. This is where context data that you have set previously, will be available throughout the journey of the wallet transaction.&#x20;

NOTE: there are some server parameters that are passed through in this field as well, so it is a good idea to prefix your variables with something e.g. `xyz_ticketId`
{% endhint %}

{% hint style="success" %}
Another way to send `passThru` data:

`https://paywall.link/to/03ccb?utm_source=telegram&myUrlParameter=specialVar`
{% endhint %}

## Special Headers

| Header              | Sample Format                    | Description                                                |
| ------------------- | -------------------------------- | ---------------------------------------------------------- |
| `X-LNPay-Event`     | `wallet_send`                    | an event from above                                        |
| `X-LNPay-HookId`    | `iwhr_TBYsAgdgeOkhfA1cb5a33szZ`  | a unique ID for this webhook request                       |
| `X-LNPay-Signature` | `aa46ae5d2d8367aef6693063e09...` | hmac\_sha256 signature of payload, if you provide a secret |
| `User-Agent`        | `LNPay-HookBot`                  | standard user agent                                        |
