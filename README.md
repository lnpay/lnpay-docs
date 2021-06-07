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
{% embed url="https://github.com/lnpay/lnpay-js" %}

```javascript
<script src="https://unpkg.com/lnpay-js@^0.1/dist/lnpay.min.js"></script>
```
{% endtab %}

{% tab title="Node.js" %}
```bash
npm install lnpay
```
{% endtab %}

{% tab title="Python" %}
{% embed url="https://github.com/lnpay/lnpay-py" %}



```
pip install lnpay-py
```
{% endtab %}

{% tab title="Go" %}
{% embed url="https://github.com/fiatjaf/lnpay-go" %}

```text
go get github.com/fiatjaf/lnpay
```
{% endtab %}
{% endtabs %}

## Initializing the SDK

{% tabs %}
{% tab title="JavaScript" %}
```javascript
//Use your Public API Key found  - this one here is presented as test
LNPay.Initialize('sak_XXXXXXX');
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
import LNPay from 'lnpay';

const lnpay = LNPay({
  secretKey: 'sak_XXXXXXX',
  walletAccessKey: 'waka_XXXXXXX',
});
```
{% endtab %}

{% tab title="Python" %}
```
import lnpay_py

# init lnpay
lnpay_py.initialize(lnpay_api_key)
```
{% endtab %}
{% endtabs %}

## Postman Collection

#### [https://www.getpostman.com/collections/fc4f2351a12b3446841c](https://www.getpostman.com/collections/fc4f2351a12b3446841c)



