---
description: Pay an lnurlpay bech32 encoded paylink
---

# Pay to lnurlpay

{% swagger method="post" path="/v1/wallet/:wallet_key/lnurlp/pay" baseUrl="https://api.lnpay.co" summary="Send payment to an lnurlpay paylink" %}
{% swagger-description %}
Should be used in conjunction with the lnurlpay 

[probe](probe.md)

 endpoint
{% endswagger-description %}

{% swagger-parameter in="body" name="lnurlpay_encoded" required="true" type="String" %}
e.g. lnurl1dp69eireddf...
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amt_msat" type="Integer" required="true" %}
Amount to pay in milisats e.g. 10000
{% endswagger-parameter %}

{% swagger-parameter in="body" name="passThru" type="Object" %}
metadata to accompany this request
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="wtx object" %}
```javascript
{
    "num_satoshis": -2,
    "user_label": null,
    "created_at": 1643036160,
    "id": "wtx_BPtKiTOxRTEGGk7qAPDFEqO",
    "wal": {
        "id": "wal_ZOBHtYmXdJzVTY",
        "created_at": 1642003748,
        "updated_at": 1643036160,
        "user_label": "Test wallet",
        "balance": 93,
        "balance_msat": null,
        "default_lnurlpay_id": "lnurlp_24zScIej6hbZv99xJB",
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
        "name": "ln_lnurl_pay_outbound",
        "display_name": "LNURL Pay Outbound"
    },
    "lnTx": {
        "id": "lntx_diw0bVWawL83GdLP2bhHlyKp",
        "created_at": 1643036160,
        "ln_node_id": "lnod_bkdaitqin2l54cbuvq",
        "dest_pubkey": "028e74f2598db804d8ae1319a5140679bd1df10811a33cbb82a183035110343760",
        "payment_request": "lnbcrt20n1ps7a00lpp53wgg23acnz3d3mecd6ckesqmpvz7jwh3ej2xwsmlssx83m6v6lqshp5nwcng97n3wtc2q89t3nk4fyflqh2r0s35jvzd7rlh9whqz40cmvscqzpgxqyd9uqsp53ugy72d0me2ftqg0ft9awhpzpxv7q62n5ye9zlfuwr5uzcut40qs9qyyssqtsdqrh43a9edmzumlnwpx34tucr4vva2hjqzcdkjd0l5fam8k5unc6803c2fsajhchxcqdrvsjtmdymylftl4626cf6f77gr24gqazcpj45nea",
        "r_hash_decoded": "8b908547b898a2d8ef386eb16cc01b0b05e93af1cc9467437f840c78ef4cd7c1",
        "memo": null,
        "description_hash": null,
        "payment_addr": null,
        "num_satoshis": 2,
        "fee_msat": 1000,
        "expiry": 432000,
        "expires_at": 1643468160,
        "payment_preimage": "c8282a307bcd812c5358376ab66a487ee5626222f6f9ee799bb237de252a07cc",
        "settled": 1,
        "settled_at": 1643036160,
        "is_keysend": null,
        "is_amp": null,
        "custom_records": null
    },
    "passThru": {
        "method": "lnurlpay",
        "tick": "tock",
        "outgoingChannelId": "118747255865345"
    }
}
```
{% endswagger-response %}
{% endswagger %}
