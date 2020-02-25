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
    },
    {
        "id": "wtx_mJO06R6XzkZf2cf680gEOgQF",
        "created_at": 1582462225,
        "num_satoshis": 20,
        "user_label": "Test invoice from Postman Collection",
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
            "name": "ln_deposit",
            "display_name": "LN Deposit"
        },
        "lnTx": {
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
            "payment_preimage": "fbf2e3e943991d7d3202d061fb1dbe7afedffb4d4f29a204c624a5366e7c5706",
            "settled": 1,
            "settled_at": 1582462225,
            "is_keysend": null,
            "custom_records": null
        },
        "passThru": []
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

{% hint style="warning" %}
`wtx['num_satoshis']` is _directional_ so there will be a negative value in the event of a debit

`lnTx['num_satoshis']` will always be a positive value
{% endhint %}

{% tabs %}
{% tab title="curl" %}
```text
$ curl -u pak_O0iUMxk8kK_qUzkT4YKFvp1ZsUtp: \
https://lnpay.co/v1/wallet/wakr_wIdkxqZqkRJd6MhWlsoH1yi/transactions
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

