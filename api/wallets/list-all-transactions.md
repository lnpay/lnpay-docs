---
description: Get a list of all transactions across all wallets
---

# List All Transactions

{% hint style="info" %}
This endpoint is only available to the **Secret Access Key (`sak_`)**
{% endhint %}

{% swagger baseUrl="https://api.lnpay.co/" path="v1/wallet-transactions" method="get" summary="ListTransactions" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="wallet_id" type="string" %}
e.g. wal_
{% endswagger-parameter %}

{% swagger-response status="200" description="Array of transactions successfully retrieved, sorted by time created descending" %}
```
# WalletTransaction objects

[
    {
        "id": "wtx_7FbT8Cz3vXXvpcQchY9CU0",
        "created_at": 1625051064,
        "num_satoshis": 1337,
        "user_label": "Paywall Payment: cd47a",
        "wal": {
            "id": "w_jhnRR8uSQUZfPM",
            "created_at": 1579000807,
            "updated_at": 1625051064,
            "user_label": "Paywall Wallet",
            "balance": 46457,
            "balance_msat": null,
            "statusType": {
                "type": "wallet",
                "name": "active",
                "display_name": "Active"
            },
            "walletType": {
                "name": "paywall_wallet",
                "display_name": "Paywall Wallet"
            }
        },
        "wtxType": {
            "layer": "ln",
            "name": "ln_deposit",
            "display_name": "LN Deposit"
        },
        "lnTx": {
            "id": "lntx_rceJSehSR4vGhdi6Krztgyr",
            "created_at": 1625051037,
            "ln_node_id": "lnod_2s4yfYA",
            "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
            "payment_request": "lnbc13370n1psdcnuapp5ce6s05xxe2wa6pervyvsqhp434ewn2aug3pvfdf54nv6vh7zqj8qdzyf3hhgueqdanzqen0dajzqer4wf5kueeqf4sku6tvvysyyatfd3jzq3rp0ysryvp38ysscqzpgxqyz5vqsp5y7t4jxcskf3mnupnvsa26e3ycr7jv08j6cx86g5pfvfa53gm8vhq9qyyssq9heux79sqmfjftejf0vm62d8l6tval9xdhu7tah96xv486htlac3gr5ufs426qrucm3j4txtx0k4ca7uxlvh2a9qm304rpuyum9znygp7xdmn3",
            "r_hash_decoded": "c67507d0c6ca9ddd07236119005c358d72e9abbc4442c4b534acd9a65fc2048e",
            "memo": "Lots of food during Manila Build Day 2019!",
            "description_hash": null,
            "num_satoshis": 1337,
            "fee_msat": 0,
            "expiry": 86400,
            "expires_at": 1625137437,
            "payment_preimage": "66856d7ea44e6433f1a035bccc1183b1949bb86d9c211eccf18c43c286da0a93",
            "settled": 1,
            "settled_at": 1625051064,
            "is_keysend": null,
            "custom_records": null
        },
        "passThru": {
            "pywl_id": "pywl_fpwcBP5E1q5DZn",
            "secondary_type": 50
        }
    },
    {
        "id": "wtx_Vhze97LOVie0OLWRuAq10D",
        "created_at": 1622506440,
        "num_satoshis": 1000,
        "user_label": "Paywall Payment: 51d9e",
        "wal": {
            "id": "w_jhnRR8uSQUZfPM",
            "created_at": 1579000807,
            "updated_at": 1625051064,
            "user_label": "Paywall Wallet",
            "balance": 46457,
            "balance_msat": null,
            "statusType": {
                "type": "wallet",
                "name": "active",
                "display_name": "Active"
            },
            "walletType": {
                "name": "paywall_wallet",
                "display_name": "Paywall Wallet"
            }
        },
        "wtxType": {
            "layer": "ln",
            "name": "ln_deposit",
            "display_name": "LN Deposit"
        },
        "lnTx": {
            "id": "lntx_ygm3rDhBP1lhFlhGOzmWxGPk",
            "created_at": 1622506427,
            "ln_node_id": "lnod_2s4yfYA",
            "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
            "payment_request": "lnbc10u1pst27a6pp525ju9s6zhvxtfzcled7vpwj4yjvtn6qw42ytq3zg9q9gqnf2k7rqdpqgahk2ueqw3hhwctjvssxsmmnw35kueeqcqzpgxqyz5vqsp5q5km4q3yuun4kwn4ky4w63gyhm67xr4c3t86wph8z9js5qfnj03s9qy9qsqk5qvk3mahaqtwhmrmeqyhks2f95h3n68tm37phxqu9wkczwd6fs8pmpdpaw4eyj6fkaacvdlsdwl4v45y6ddyn8hr5mrdcgz6aqm3yqp037sqy",
            "r_hash_decoded": "5525c2c342bb0cb48b1fcb7cc0ba552498b9e80eaa88b04448280a804d2ab786",
            "memo": "Goes toward hosting ",
            "description_hash": null,
            "num_satoshis": 1000,
            "fee_msat": 0,
            "expiry": 86400,
            "expires_at": 1622592827,
            "payment_preimage": "ecefd05735fd42aa7382a43d0037bf8ef58f3299e97d18d2c43b4a0601c85e1a",
            "settled": 1,
            "settled_at": 1622506440,
            "is_keysend": null,
            "custom_records": null
        },
        "passThru": {
            "pywl_id": "pywl_fNglEOvTT3futq",
            "secondary_type": 50
        }
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
the `lntx` field will be `null` if the transaction is a transfer
{% endhint %}

{% hint style="warning" %}
`wtx['num_satoshis']` is _directional_ so there will be a negative value in the event of a debit

`lnTx['num_satoshis']` will always be a positive value
{% endhint %}

{% tabs %}
{% tab title="cURL" %}
```
curl -u sak_XXXXXXX: \
https://api.lnpay.co/v1/wallet-transactions
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
const lnpay = LNPay({
  secretKey: 'sak_XXXXX',
  walletAccessKey: 'wal_XXXXX',
});

const transactions = await lnpay.getTransactions({
  page: 1,
});
```
{% endtab %}

{% tab title="Python" %}
```python
lnpay_py.initialize('sak_XXXXXXX')
from lnpay_py.wallet import LNPayWallet

my_wallet = LNPayWallet('waki_XXXXXX')
transactions = my_wallet.get_transactions()
print(transactions)
```
{% endtab %}
{% endtabs %}
