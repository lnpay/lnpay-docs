---
description: Welcome to the LNPay API docs!
---

# Introduction

## Client SDKs

The libraries below are wrappers to help you work with the LNPay API. How to install:

{% tabs %}
{% tab title="Node.js" %}
{% embed url="https://github.com/MiguelMedeiros/lnpay" %}

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
[https://github.com/lnpay/lnpay-go](https://github.com/lnpay/lnpay-go)

```text
go get github.com/lnpay/lnpay-go
```
{% endtab %}

{% tab title="PHP" %}
[https://github.com/lnpay/lnpay-php](https://github.com/lnpay/lnpay-php)

```text
composer require lnpay/lnpay-php
```
{% endtab %}

{% tab title="JavaScript" %}
{% hint style="info" %}
This used client side - use the `pak_` everywhere.
{% endhint %}

{% embed url="https://github.com/lnpay/lnpay-js" %}

```javascript
<script src="https://unpkg.com/lnpay-js@^0.1/dist/lnpay.min.js"></script>
```
{% endtab %}
{% endtabs %}

## Initializing the SDK

{% tabs %}
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

{% tab title="Go" %}
```
lnpaySecretKey := lnpay.TEST_KEY
// use your key here: "sak_..."

client := lnpay.NewClient(lnpaySecretKey)
```
{% endtab %}

{% tab title="PHP" %}
```
// Load the autoload file from composer's vendor directory
require '../vendor/autoload.php';

use LNPay\LNPayClient;

// Creating Client object
$lnPayClient = new LNPayClient(
        'sak_KEY'
    );
    
$lnPayClient->wallet->setWalletAccessKey('wal_KEY');
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_XXXXXXX');
```
{% endtab %}
{% endtabs %}

## Postman Collection

#### [https://www.getpostman.com/collections/fc4f2351a12b3446841c](https://www.getpostman.com/collections/fc4f2351a12b3446841c)

