---
description: >-
  Get a list of wallet transactions that have been SETTLED. This includes only
  transactions that have an impact on wallet balance. These DO NOT include
  unsettled/unpaid invoices.
---

# Get Transactions

{% api-method method="get" host="https://lnpay.co/v1/wallet/" path=":wallet\_access\_key/transactions" %}
{% api-method-summary %}
GetWalletTransactions
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_access\_key" type="string" required=true %}
Wallet Access Key \(WAK\)
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Array of transactions successfully retrieved, sorted by time created descending
{% endapi-method-response-example-description %}

```
# WalletTransaction objects

[
    {
        "id": "wtx_OXWNFNYYY0NsGLwLx7AtcPM",
        "created_at": 1580475159,
        "wallet_id": "w_ALMWRQrSoSf4Qh",
        "num_satoshis": 158,
        "user_label": "asdf",
        "lnTx": {
            "id": "lntx_hlLn7xArPmew8KKSjqJqy6Vo",
            "created_at": 1580129586,
            "updated_at": 1580129586,
            "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
            "payment_request": "",
            "r_hash_decoded": "7e13af679b551d8b0b804c3f0c74b43352c2d4c332ead6d693a8ea0aa6b6beec",
            "memo": "",
            "description_hash": "",
            "num_satoshis": 2,
            "expiry": 0,
            "expires_at": null,
            "payment_preimage": "323550597244415037724d6a436765567a72735875667438626e66754d385547",
            "settled": 1,
            "settled_at": 1580129586
        },
        "wtxType": {
            "id": 30,
            "layer": "ln",
            "name": "ln_transfer_in",
            "display_name": "Transfer In"
        }
    }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
the `lntx` field will be `null` if the transaction is a transfer
{% endhint %}

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
https://lnpay.co/v1/wallet/wr_3YgsKHplFSyhzBKNVr8tohO/transactions
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

let myWallet = new LNPayWallet(walletAccessKey);
let queryParams = {};
myWallet.getTransactions(queryParams,
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

my_wallet = LNPayWallet('wi_skllxCQI7yurKi0NCCTc0wwO')
transactions = my_wallet.get_transactions()
print(transactions)
```
{% endtab %}
{% endtabs %}

