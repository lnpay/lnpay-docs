---
description: This section describes how to transfer sats between wallets within LNPay
---

# Transfers Between Wallets

{% swagger baseUrl="https://api.lnpay.co/" path="v1/wallet/:wallet_key/transfer" method="post" summary="PostWalletTransfer" %}
{% swagger-description %}
Transfer satoshis from source wallet to destination wallet
{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_key" type="string" %}
wal_ for server side

\


waka_ for client side
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dest_wallet_id" type="string" %}
destination wallet_id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="num_satoshis" type="number" %}
sats for this transfer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="memo" type="string" %}
memo note for this transfer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lnPayParams" type="array" %}
JSON array of custom data to pass thru
{% endswagger-parameter %}

{% swagger-response status="200" description="Transfer executed" %}
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
{% endswagger-response %}

{% swagger-response status="400" description="Error reported" %}
```
{
    "name":"Bad Request",
    "message":"insufficient funds",
    "code":0,
    "status":400
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```
curl -u sak_XXXXXXX: \
-H "Content-Type: application/json" \
-X POST \
-d '{"dest_wallet_id":"wal_XXXX","num_satoshis":1,"memo":"Test transfer"}' \
https://api.lnpay.co/v1/wallet/wal_XXXXX/transfer
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
const lnpay = LNPay({
  secretKey: 'sak_XXXXX',
  walletAccessKey: 'wal_XXXXX',
});

const transfer = await lnpay.transfer({
  dest_wallet_id: 'wal_XXXXX',
  num_satoshis: 1,
  memo: 'Transfer Memo',
  lnPayParams: {
    order_id: '100',
  },
});
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('pak_XXXX')
from lnpay_py.wallet import LNPayWallet

my_wallet = LNPayWallet('wal_XXX')
transfer_params = {
    'dest_wallet_id': 'w_XXX',
    'num_satoshis': 1,
    'memo': 'Transfer Memo'
}
transfer_result = my_wallet.internal_transfer(transfer_params)
print(transfer_result)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
LNPay.Initialize('pak_XXXXX');

let myWallet = new LNPayWallet('waka_XXXXX');
let transferParams = {"dest_wallet_id":"wal_xxxxx","num_satoshis":22,"memo":"Transfer Memo"};
myWallet.internalTransfer(transferParams,
    function(result) {
      console.log(result);
    }
);
```
{% endtab %}
{% endtabs %}
