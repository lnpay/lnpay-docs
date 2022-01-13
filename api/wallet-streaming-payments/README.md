# Wallet Streaming Payments

## Keysend Payments

The Lightning Network keysend enables "spontaneous" payments - push realtime push payments.&#x20;

<details>

<summary>Successful Keysend Receive Object</summary>

```
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
```

</details>

<details>

<summary>Successful Keysend Send Object</summary>

```
{
    "id": "wtx_ErGDqbxxWrhhgddBMXVmXSS2",
    "created_at": 1642082176,
    "num_satoshis": -2,
    "user_label": "2 keysend to 03f7fd705022ef59521b360a20f598f2027abe7a5cc221c69ffb1d525dab2af4cb",
    "wallet_lnurlw_id": null,
    "wal": {
        "id": "wal_9B2BDCFGEOrpxv",
        "created_at": 1642013336,
        "updated_at": 1642082176,
        "user_label": "123",
        "balance": 97,
        "balance_msat": null,
        "statusType": {
            "type": "wallet",
            "name": "active",
            "display_name": "Active"
        },
        "walletType": {
            "name": "generic_wallet",
            "display_name": "Generic Wallet"
        },
        "defaultLnurlpay": {
            "id": "lnurlp_6Xh2hELFFqSlKEHCbF",
            "created_at": 1642013336,
            "updated_at": 1642013336,
            "user_label": "Base lnurl-pay link",
            "lnurl_encoded": "LNURL1DP68GUP69UHKCMNSV9UJUMR0VDSKCW3CXYCNZTMKXYHHWCTVD3JHGTMHV94KCUZLX3TXC7NYWF5KYN34VE2YZKR42E3KJ6E4V4XKCNP0D3H82UNVWQHKCMN4WFK8QHEKTP5RY6Z9F3RYVU2ND3952JZRVFRQWUZJNJ",
            "lnurl_decoded": "http://lnpay.local:8111/v1/wallet/waklp_4VlzdribN5fTAXuVcik5eMlL/lnurlp/lnurlp_6Xh2hELFFqSlKEHCbF",
            "lnurlp_minSendable_msat": 1000,
            "lnurlp_maxSendable_msat": 10000000,
            "lnurlp_short_desc": "LNURL PAY (via LNPay.co)",
            "statusType": {
                "type": "lnurl",
                "name": "lnurl_active",
                "display_name": "LNURL Active"
            }
        }
    },
    "wtxType": {
        "layer": "ln",
        "name": "ln_withdrawal",
        "display_name": "LN Withdrawal"
    },
    "lnTx": {
        "id": "lntx_XCQrUPoYprHuVJWCOuKv3pH",
        "created_at": 1642082176,
        "ln_node_id": "lnod_bkdaitqin2l54cbuvq",
        "dest_pubkey": "03f7fd705022ef59521b360a20f598f2027abe7a5cc221c69ffb1d525dab2af4cb",
        "payment_request": "03f7fd705022ef59521b360a20f598f2027abe7a5cc221c69ffb1d525dab2af4cb:2",
        "r_hash_decoded": "182959f9e8592faaa1214e3ccdbde2fe8d5e25efaaac2b8bad58828da4c8fdc6",
        "memo": "2 keysend to 03f7fd705022ef59521b360a20f598f2027abe7a5cc221c69ffb1d525dab2af4cb",
        "description_hash": null,
        "payment_addr": null,
        "num_satoshis": 2,
        "fee_msat": 1000,
        "expiry": 432000,
        "expires_at": null,
        "payment_preimage": "966646eb40238a0155d6f6779e0b43e48be4b8ef06a8d8626e53e67b9c7f90a6",
        "settled": 1,
        "settled_at": 1642082176,
        "is_keysend": 1,
        "is_amp": null,
        "custom_records": {
            "322223": "{\"test\":\"asdf\"}",
            "5482373484": "966646eb40238a0155d6f6779e0b43e48be4b8ef06a8d8626e53e67b9c7f90a6"
        }
    },
    "passThru": {
        "method": "api",
        "ticketId": "23",
        "outgoingChanId": "118747255865345"
    }
}
```

</details>

## Podcasting2.0 FAQ

<details>

<summary><code>FAILURE_REASON_NO_ROUTE</code></summary>

* There is no route because the `fee_limit_msat` is too low or the default 5% is too low (this is usually the issue)
* There is no route because the lightning node cannot find a path (sometimes this happens with private nodes, or new nodes)
* There is no route because the destination node (podcaster) does not have enough lightning network liquidity to receive.

Check the [QueryRoutes](../lightning-network-nodes/query-routes.md) endpoint for help in determining what the issue is.

</details>

