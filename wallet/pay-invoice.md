---
description: Generate an LN invoice from the specified wallet
---

# Pay Invoice

{% api-method method="post" host="https://api.lnpay.co/v1/wallet/" path=":access\_key/withdraw" %}
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
{% api-method-parameter name="fee\_limit\_msat" type="number" required=false %}
max fee e.g. 1000 \(1 sat\) LNPay default fee limit is 5% of payment amount
{% endapi-method-parameter %}

{% api-method-parameter name="payment\_request" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="passThru" type="object" required=false %}
JSON object of custom data to pass thru
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Payment successfully executed
{% endapi-method-response-example-description %}

```
# WTX OBJECT

{
    "id": "wtx_dYeWXmMTrP1VH8XZMOhXdE1",
    "created_at": 1582462278,
    "num_satoshis": -1,
    "user_label": "Test for DOCS",
    "wal": {
        "id": "wal_czDztN5eJ4r5sJ",
        "created_at": 1582461859,
        "updated_at": 1582462278,
        "user_label": "My Postman Collection Wallet",
        "balance": 19,
        "statusType": {
            "type": "wallet",
            "name": "active",
            "display_name": "Active"
        }
    },
    "wtxType": {
        "layer": "ln",
        "name": "ln_withdrawal",
        "display_name": "LN Withdrawal"
    },
    "lnTx": {
        "id": "lntx_aB5lHY5ebFtei4SOByEQ8bnP",
        "created_at": 1582462278,
        "dest_pubkey": "02c16cca44562b590dd279c942200bdccfd4f990c3a69fad620c10ef2f8228eaff",
        "payment_request": "lnbc10n1p09yafzpp5ens55wl8pfm6n2222pyyxjhx9rwcj4zl8pcyhsr2qzlklke4qfvsdq423jhxapqvehhygzyfap4xxqyz5vqcqzyssp52vyh6djmjt644fygwr54cs9vv82d2zc67tmkeun3c40ypzrvqe4srzjqt0pr36g7ke9elfvaqq3wmfey6laun0z8v0lg0nf9fdhdncxsp0y5zxkp5qqnsgqqqqqqqqqqqqq05qqrc9qy9qsqq3a4p9tvmy3sf7h2mlfpd5rcdldsyaksf8e0rk09yxtzvhcyzjrsg2janexechmzaqmnz9c7de04et7jkhmvkkjdnzn3txnz2a204ucplr595s",
        "r_hash_decoded": "cce14a3be70a77a9a94a5048434ae628dd89545f38704bc06a00bf6fdb350259",
        "memo": "Test for DOCS",
        "description_hash": null,
        "num_satoshis": 1,
        "expiry": 86400,
        "expires_at": 1582548678,
        "payment_preimage": "6239646b2f326757664d37562b34383070347475665a4d65416c504f6f622b444933314c4e6246593554553d",
        "settled": 1,
        "settled_at": 1582462278,
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

{% hint style="info" %}
`FAILURE_REASON_NO_ROUTE` is a common error that means one of two things

* There is no route because the `fee_limit_msat` is too low or the default 5% is too low \(this is usually the issue\)
* There is no route because the lightning node cannot find a path \(sometimes this happens with private nodes, or new nodes\)

Check the [QueryRoutes](../node/queryroutes.md) endpoint for help in determining what the issue is.
{% endhint %}

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
-H "Content-Type: application/json" \
-X POST \
-d '{"payment_request":"lnbc50n1p0qjf84p..."}' \
https://api.lnpay.co/v1/wallet/waka_kqvaiFFl4Tjq4rgAXlwsu6/withdraw

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

