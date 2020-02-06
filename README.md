---
description: >-
  The goal of the LNPay API is to create a toolkit interface for interaction
  between nodes and external services. See below some examples / applications.
---

# Getting Started

## Client SDKs

The libraries below are wrappers to help you work with the LNPay API. How to install:

{% tabs %}
{% tab title="JavaScript" %}
[https://github.com/lnpay/lnpay-js](https://github.com/lnpay/lnpay-js)

```javascript
<script src="https://unpkg.com/lnpay-js@^0.1/dist/lnpay.min.js"></script>
```
{% endtab %}

{% tab title="Node.js" %}
```bash
npm install lnpay-js --save
```
{% endtab %}
{% endtabs %}

## Initializing the SDK

{% tabs %}
{% tab title="JavaScript" %}
```javascript
//Use your Public API Key found  - this one here is presented as test
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
//Use your Public API Key found  - this one here is presented as test
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');
```
{% endtab %}
{% endtabs %}

## In the Wild

#### [LNPay M5StackSats](https://github.com/arcbtc/M5StackSats/tree/master/M5StackSatsLNPAY)

The LNPay implementation of [@BTCSocialist](https://www.twitter.com/@BTCSocialist) [M5StackSats](https://github.com/arcbtc/M5StackSats) is a cheap and easy to use lightweight PoS system. 



