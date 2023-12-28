---
description: >-
  The Generate Invoice endpoint is unique in that it returns an LnTx object vs a
  wtx object. The LnTx object in this case represents an unpaid invoice. To
  check the status of this - use the /lntx
---

# Generate Invoice

{% swagger baseUrl="https://<yourdomain>/" path="v1/wallet/:wallet_key/invoice" method="post" summary="PostWalletInvoice" %}
{% swagger-description %}
Creating an invoice returns the LNPay representation of a BOLT11 invoice - the LnTx object
{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_key" type="string" %}
wal\_ for server side\
waki\_ for client side
{% endswagger-parameter %}

{% swagger-parameter in="body" name="passThru" type="object" %}
JSON object. you can reference these parameters later via webhooks, etc. Good for ticket # or a certain ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description_hash" type="string" %}
base64 encoded hash of payment. If this is provided, memo will be ignored.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="memo" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="expiry" type="integer" %}
seconds, defaults to 86400 (1 day)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="num_satoshis" type="integer" %}

{% endswagger-parameter %}

{% swagger-response status="201" description="This returns an LnTx object " %}
{% code title="# LnTx Object" %}
```
{
    "id": "lntx_ztkK7XxfqCq3ihmhJiUhnR",
    "created_at": 1582462172,
    "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
    "payment_request": "lnbc200n1p09yaxupp5r7ckx99n00d2a7g8xtr8wup57w82t827kkeujsdgjyn45cjmym7sdp623jhxapqd9h8vmmfvdjjqenjdakjq5r0wd6x6ctwyppk7mrvv43hg6t0dccqzpgxqyz5vqsp5gyfwnrqnkyvxxgpww0vwsl8tfe524ggr5kngr8n8fn4vt9xl5ggs9qy9qsq42vwx9dh2n3ggrlgwqqxqq77detywruhv2s558uk3vfrumgmjfhs3y8hwtgxe7cx6svg4pr87qzfg8mgawsveqe6wn0te9d3h02fm4spxtzy5s",
    "r_hash_decoded": "1fb16314b37bdaaef90732c6777034f38ea59d5eb5b3c941a891275a625b26fd",
    "memo": "Test invoice from Postman Collection",
    "description_hash": null,
    "num_satoshis": 20,
    "expiry": 86400,
    "expires_at": 1582548572,
    "payment_preimage": null,
    "settled": 0,
    "settled_at": null,
    "is_keysend": null,
    "custom_records": null,
    "passThru": {
        "wallet_id": "wal_czDztN5eJ4r5sJ",
        "userDefined": {
            "ticketId": "556"
        }
    }
}
```
{% endcode %}
{% endswagger-response %}
{% endswagger %}

{% hint style="success" %}
To check if an invoice has been paid or not use the [LnTx endpoint ](../lntx/retrieve.md)
{% endhint %}

{% tabs %}
{% tab title="cURL" %}
```
curl -u sak_XXXXXXX: \
-H "Content-Type: application/json" \
-X POST \
-d '{"num_satoshis":5, "memo":"Test invoice from the docs","passThru":" {\"ticketId\":\"556\"} "}' \
https://<yourdomain>/v1/wallet/wal_XXXX/invoice
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
const lnpay = LNPay({
  secretKey: 'sak_XXXXX',
  walletAccessKey: 'wal_XXXXX',
});

const invoice = await lnpay.generateInvoice({
  num_satoshis: 100,
  passTru: {
    order_id: '100',
  },
  description_hash: 'MTIzNDY1Nzg5N...',
  memo: 'Invoice memo.',
  expiry: 86400, // 1 day
});
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('sak_XXXXXXX')
from lnpay_py.wallet import LNPayWallet

my_wallet = LNPayWallet('wal_XXXXX')
invoice_params = {
    'num_satoshis': 2,
    'memo': 'Tester'
}
invoice = my_wallet.create_invoice(invoice_params)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_XXXXXXX');

let myWallet = new LNPayWallet('waki_XXXXXX');
let invoiceParams = {"num_satoshis":2,"memo":"Tester"};
myWallet.createInvoice(invoiceParams,
    function(result) {
      console.log(result);
    }
);
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
See the [Access Keys](../get-started/access-keys.md#permission-breakdown) section on how to define `wallet_key`
{% endhint %}
