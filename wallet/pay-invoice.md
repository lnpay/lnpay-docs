---
description: Generate an LN invoice from the specified wallet
---

# Pay Invoice

{% api-method method="post" host="https://lnpay.co/v1/wallet/" path=":access\_key/withdraw" %}
{% api-method-summary %}
PostWalletSend
{% endapi-method-summary %}

{% api-method-description %}
Pay an invoice from this wallet
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_access\_key" type="string" required=true %}
access key
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="payment\_request" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="lnPayParams" type="array" required=false %}
JSON array of custom data to pass thru
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Payment successfully executed
{% endapi-method-response-example-description %}

```
{
    "id": "wtx_FBNJHXvQFgI4u4oCjKndq2Tq",
    "created_at": 1582297179,
    "num_satoshis": -5,
    "user_label": "Postman Test",
    "wallet": {
        "id": "w_hkjS9r6mTYeABc",
        "created_at": 1577654988,
        "updated_at": 1582297179,
        "user_label": "DEFAULT WALLET",
        "balance": 3,
        "statusType": {
            "type": "wallet",
            "name": "active",
            "display_name": "Active"
        }
    },
    "walletTransactionType": {
        "layer": "ln",
        "name": "ln_withdrawal",
        "display_name": "LN Withdrawal"
    },
    "lnTx": {
        "id": "lntx_dH2HtFowzUjHp7ovsjG4m5U1",
        "created_at": 1582297179,
        "dest_pubkey": "02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff",
        "payment_request": "lnbc50n1p0yluznpp5u5txfgymgxkkrperkqa2wvt7qkmkg07duc90jvz67zm9weg2n8dqdq52phhxardv9hzq4r9wd6qxqyz5vqcqzyssp5ynfu54a6m8zccexu6mmm8y73kn8x2335l805dpu769rt9qmzq6nsrzjq2j9mmu6uq20m5nq8htsx0g4074r54d89vr2vwhz9m6xm8a0m3hg6ztt95qqtjgqqyqqqqqrqqqq8hsqyq9qy9qsq0kr0pnhlyzve2uqlznr6vglep3rzsml52c6tv5jz6yrvg3qnxrdy657cxxuxs3qetdu57kj7nscfz6f0z5p035g2ge6htpdca00480cq3qen60",
        "r_hash_decoded": "e51664a09b41ad618723b03aa7317e05b7643fcde60af9305af0b657650a99da",
        "memo": "Postman Test",
        "description_hash": null,
        "num_satoshis": 5,
        "expiry": 86400,
        "expires_at": 1582383579,
        "payment_preimage": "30754e742b63514174693476676e5975706f4769487a794d6166796472775361625372487a437773674e303d",
        "settled": 1,
        "settled_at": 1582297179,
        "is_keysend": null,
        "custom_records": null
    },
    "passThru": {
        "method": "api"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Response directly from node if node error
{% endapi-method-response-example-description %}

```
{
    "name":"Bad Request",
    "message":"invoice is already paid",
    "code":0,
    "status":400
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
-H "Content-Type: application/json" \
-X POST \
-d '{"payment_request":"lnbc50n1p0qjf84p..."}' \
https://lnpay.co/v1/wallet/wa_Opnn4kGOGBMnfCLFXtsDnjTb/withdraw

# Note we are using the "admin" access_key as denoted by "wa_"
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

let myWallet = new LNPayWallet('wa_Opnn4kGOGBMnfCLFXtsDnjTb');
let invoiceParams = {"payment_request":"lnbc1111..."};
myWallet.payInvoice(invoiceParams,
    function(result) {
      console.log(result);
    }
);
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp')
from lnpay_py.wallet import LNPayWallet

my_wallet = LNPayWallet('wa_Opnn4kGOGBMnfCLFXtsDnjTb')
invoice_params = {
    'payment_request': 'lnbc....'
}
pay_result = my_wallet.pay_invoice(invoice_params)
print(pay_result)
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
The `Content-Type: application/json` header is required for all `POST` request with a JSON body!
{% endhint %}

