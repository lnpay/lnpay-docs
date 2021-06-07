---
description: This section describes how to transfer sats between wallets within LNPay
---

# Transfers Between Wallets

{% api-method method="post" host="https://api.lnpay.co/v1/wallet" path="/:wallet\_access\_key/transfer" %}
{% api-method-summary %}
PostWalletTransfer
{% endapi-method-summary %}

{% api-method-description %}
Transfer satoshis from source wallet to destination wallet
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="wallet\_access\_key" type="string" required=true %}
Source wallet key for the transfer. Must be admin key
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="dest\_wallet\_id" type="string" required=true %}
destination wallet access key \(WAK\) or wallet\_id
{% endapi-method-parameter %}

{% api-method-parameter name="num\_satoshis" type="number" required=true %}
sats for this transfer
{% endapi-method-parameter %}

{% api-method-parameter name="memo" type="string" required=false %}
memo note for this transfer
{% endapi-method-parameter %}

{% api-method-parameter name="lnPayParams" type="array" required=false %}
JSON array of custom data to pass thru
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Transfer executed
{% endapi-method-response-example-description %}

```
{
    "wtx_transfer_in": {
        "id": "wtx_D2MOU88MTPpOytfdflCoGSs8",
        "created_at": 1582297599,
        "num_satoshis": 1,
        "user_label": "Test transfer from Postman Collection",
        "wallet": {
            "id": "w_n743yizWqe43Oz",
            "created_at": 1579001314,
            "updated_at": 1582297599,
            "user_label": "Paywall Wallet",
            "balance": 4,
            "statusType": {
                "type": "wallet",
                "name": "active",
                "display_name": "Active"
            }
        },
        "walletTransactionType": {
            "layer": "ln",
            "name": "ln_transfer_in",
            "display_name": "Transfer In"
        },
        "lnTx": null,
        "passThru": {
            "lnPayParams": null,
            "dest_wallet_id": "w_n743yizWqe43Oz",
            "source_wallet_id": "w_hkjS9r6mTYeABc"
        }
    },
    "wtx_transfer_out": {
        "id": "wtx_LiAIfLI6x1T9sepE80aMYnlw",
        "created_at": 1582297599,
        "num_satoshis": -1,
        "user_label": "Test transfer from Postman Collection",
        "wallet": {
            "id": "w_hkjS9r6mTYeABc",
            "created_at": 1577654988,
            "updated_at": 1582297599,
            "user_label": "DEFAULT WALLET",
            "balance": 2,
            "statusType": {
                "type": "wallet",
                "name": "active",
                "display_name": "Active"
            }
        },
        "walletTransactionType": {
            "layer": "ln",
            "name": "ln_transfer_out",
            "display_name": "Transfer Out"
        },
        "lnTx": null,
        "passThru": {
            "lnPayParams": null,
            "dest_wallet_id": "w_n743yizWqe43Oz",
            "source_wallet_id": "w_hkjS9r6mTYeABc"
        }
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Error reported
{% endapi-method-response-example-description %}

```
{
    "name":"Bad Request",
    "message":"insufficient funds",
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
$ curl -u sak_XXXXXXX: \
-H "Content-Type: application/json" \
-X POST \
-d '{"dest_wallet_id":"w_n743yizWqe43Oz","num_satoshis":1,"memo":"Test transfer"}' \
https://api.lnpay.co/v1/wallet/waka_XXXXXXX/transfer
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp');

let myWallet = new LNPayWallet('wa_Opnn4kGOGBMnfCLFXtsDnjTb');
let transferParams = {"dest_wallet_id":"wa_xxxxx","num_satoshis":22,"memo":"Transfer Memo"};
myWallet.internalTransfer(transferParams,
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
transfer_params = {
    'dest_wallet_id': 'w_XXX',
    'num_satoshis': 1,
    'memo': 'Transfer Memo'
}
transfer_result = my_wallet.internal_transfer(transfer_params)
print(transfer_result)
```
{% endtab %}
{% endtabs %}

