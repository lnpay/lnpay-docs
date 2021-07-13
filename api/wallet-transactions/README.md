---
description: All WalletTransaction objects are prefixed with wtx_
---

# Wallet Send / Receive

## The Wallet Transaction Object

Any Wallet interaction with the Lightning Network that results in a _**settled**_ transaction creates a WalletTransaction object. Here are some examples of them below

{% tabs %}
{% tab title="Keysend Receive" %}
```text
[
    {
        "id": "wtx_JReJMmtQCxsFx3JReJMmtQCxsFx3",
        "created_at": 1625968441,
        "num_satoshis": 18,
        "user_label": "keysend: custom record [112111100] [wal_JReJMmtQCxsFx3]",
        "wal": {
            "id": "wal_JReJMmtQCxsFx3",
            "created_at": 1623200380,
            "updated_at": 1625968441,
            "user_label": "PC20TestWallet",
            "balance": 168,
            "balance_msat": null,
            "statusType": {
                "type": "wallet",
                "name": "active",
                "display_name": "Active"
            },
            "walletType": {
                "name": "generic_wallet",
                "display_name": "Generic Wallet"
            }
        },
        "wtxType": {
            "layer": "ln",
            "name": "ln_deposit",
            "display_name": "LN Deposit"
        },
        "lnTx": {
            "id": "lntx_JReJMmtQCxsFx3JReJMmtQCxsFx3",
            "created_at": 1625968441,
            "ln_node_id": "lnod_2s4yfYA",
            "dest_pubkey": "033868c219bdb51a33560d854d500fe7d3898a1ad9e05dd89d0007e11313588500",
            "payment_request": "keysend",
            "r_hash_decoded": "785279554b7a2b72496c6d486a3937496f57322f685170682f6b4a384d676e46335649414b4435505859673d",
            "memo": "keysend: custom record [112111100] [wal_JReJMmtQCxsFx3]",
            "description_hash": null,
            "num_satoshis": 18,
            "fee_msat": 0,
            "expiry": 432000,
            "expires_at": null,
            "payment_preimage": "871df9c3fc54102fb695ba2a4c7e6a3a97f3140f146b5de675178103c64cf9e0",
            "settled": 1,
            "settled_at": 1625968441,
            "is_keysend": 1,
            "custom_records": {
                "7629169": {
                    "time": "00:35:57",
                    "action": "stream",
                    "feedID": "920666",
                    "episode": "Episode 45: Pressin' The Flesh and Kissin' Babies",
                    "podcast": "Podcasting 2.0"
                },
                "7629171": "LNPayTesting",
                "112111100": "wal_JReJMmtQCxsFx3",
                "5482373484": "68783335772f785545432b326c626f71544835714f70667a464138556131336d6452654241385a4d2b65413d"
            }
        },
        "passThru": {
            "wallet_id": "wal_JReJMmtQCxsFx3",
            "custom_records": {
                "7629169": {
                    "time": "00:35:57",
                    "action": "stream",
                    "feedID": "920666",
                    "episode": "Episode 45: Pressin' The Flesh and Kissin' Babies",
                    "podcast": "Podcasting 2.0"
                },
                "7629171": "LNPayTesting",
                "112111100": "wal_JReJMmtQCxsFx3",
                "5482373484": "68783335772f785545432b326c626f71544835714f70667a464138556131336d6452654241385a4d2b65413d"
            }
        }
    }
]
```
{% endtab %}

{% tab title="Keysend Send" %}
```

```
{% endtab %}

{% tab title="Wallet Pay Invoice" %}
```

```
{% endtab %}

{% tab title="Wallet Receive" %}
```

```
{% endtab %}
{% endtabs %}

